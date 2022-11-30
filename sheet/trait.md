# Trait
https://doc.rust-lang.org/book/ch10-02-traits.html

> Traits are similar to a feature often called interfaces in other languages, although with some differences.

## Defining a Trait
``` rust
pub trait Summary {
  fn summarize(&self) -> String;
}
```

## Implementing a Trait on a Type
``` rust
pub struct Tweet {
  pub username: String,
  pub content: String,
  pub reply: bool,
  pub retweet: bool,
}

impl Summary for Tweet {
  fn summarize(&self) -> String {
    format!("{}: {}", self.username, self.content)
  }
}
```

## Traits as Parameters
``` rust
fn notify(item: &impl Summary) {
  println!("Breaking news! {}", item.summarize());
}
```
is same with:
``` rust
pub fn notify<T: Summary>(item: &T) {
  println!("Breaking news! {}", item.summarize());
}
```

## Specifying Multiple Trait Bounds with the + Syntax
``` rust
pub fn notify(item: &(impl Summary + Display)) {

pub fn notify<T: Summary + Display>(item: &T) {
```

## Clearer Trait Bounds with where Clauses
``` rust
fn some_function<T: Display + Clone, U: Clone + Debug>(t: &T, u: &U) -> i32 {

fn some_function<T, U>(t: &T, u: &U) -> i32
where
    T: Display + Clone,
    U: Clone + Debug,
{
```
