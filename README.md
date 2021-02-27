# ViewModel-vs-AndroidViewModel-Contexts

## Why ViewModel
- The purpose of a ViewModel is to have a single object to render, lightening the need for UI logic code in the view that would otherwise be necessary.
- Leads to more easily maintainable and testable code

## ViewModel
```kotlin
class MainViewModel() : ViewModel() {
    ...
}
```
## Memory leak | Activity Context
For Android Architecture Components View Model, It's not a good practice to pass your Activity Context to the Activity's ViewModel as it's a memory leak. Consequently, to get the context in your ViewModel, the ViewModel class should extend the AndroidViewModel Class.

## Why does it cause memory leaks?
Activities get destroyed more often than their ViewModel, such as when the screen is rotated. Unfortunately, the memory won't be released by the garbage collection because the ViewModel still references it.

## AndroidViewModel
```kotlin
class MainViewModel(val app: Application) : AndroidViewModel(app) {
    ...
}
```
**val app: Application** this variable can be used to access resources where you would normally use the Activity context.


