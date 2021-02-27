# ViewModel-vs-AndroidViewModel

## Why ViewModel
- The purpose of a ViewModel is to have a single object to render, lightening the need for UI logic code in the view that would otherwise be necessary.
- Leads to more easily maintainable and testable code

## ViewModel
```kotlin
class MainViewModel() : ViewModel() {
    ...
}
```

## Memory leak
For Android Architecture Components View Model, It's not a good practice to pass your Activity Context to the Activity's ViewModel as it's a memory leak. Consequently, to get the context in your ViewModel, the ViewModel class should extend the AndroidViewModel Class.

## AndroidViewModel
```kotlin
class MainViewModel2(val app: Application) : AndroidViewModel(app) {
    ...
}
```


