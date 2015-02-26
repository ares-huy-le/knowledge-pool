```ruby
static func notify(title: String = "", message: String, style: UIAlertControllerStyle = .Alert, on viewController: UIViewController) -> UIAlertController {
...
}
```
```ruby
extension UIAlertController {
    func willCancel(cancelButtonText: String = "Cancel", closure: (UIAlertAction) -> ()) {
    ...
    // Deal with localization too  
    }
}
```
