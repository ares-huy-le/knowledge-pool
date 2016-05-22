1. Failable Initializer

```swift
init?(from: IssueTransitionObject) {
    guard let objToStatus = from.toStatus, status = IssueStatusState(from: objToStatus) else {
        return nil
    }
}
```
