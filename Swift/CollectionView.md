```
It’s not recommended that you change the registration information after dequeueing one or more items. It is better to register your cells and views once and be done with it.
```
[CollectionView Apple](https://developer.apple.com/library/ios/documentation/WindowsViews/Conceptual/CollectionViewPGforIOS/CreatingCellsandViews/CreatingCellsandViews.html)

```ruby
override func preferredLayoutAttributesFittingAttributes(layoutAttributes: UICollectionViewLayoutAttributes) -> UICollectionViewLayoutAttributes {
    return layoutAttributes
}
```
it reduce a lots performance **important**

*cannot* dequeue anywhere except cellForRowAtIndexPath

- it runs sizeForCell even if we declared estimatedSize

- set size manually is better than use estimatedSize

- it isn't a problem of set models

 wrap dequeue or cellForRowAtIndexPath inside `dispatch_async(dispatch_get_main_queue()) { () -> Void }` may create something

 we don't need to call dequeue to create a cell, we can use nib or class to create it

 SVGKit make UICollectionView laggy


 Miss aligned image can cause the CollectionView become lagger, decrease the rendering effect
 
