```swift

    func performUpdate(onSection section: Int, insertAnimation: UITableViewRowAnimation = .Left, deleteAnimation: UITableViewRowAnimation = .Right, loadingAnimation: UITableViewRowAnimation = .None, @noescape updateDataSource: VoidClosure) {
        guard let dataSource = dataSource else { return }
        let numberOfRowInSection = dataSource.tableView(self, numberOfRowsInSection: section)
        updateDataSource()

        let numberOfRowInSectionAfterUpdate = dataSource.tableView(self, numberOfRowsInSection: section)
        let differentIndexes = differentIndexesBetween(numberOfRowInSection, and: numberOfRowInSectionAfterUpdate)
        let insertedIndexPath = differentIndexes.inserts.map { NSIndexPath(forRow: $0, inSection: section) }
        let changedIndexPath = differentIndexes.changes.map { NSIndexPath(forRow: $0, inSection: section) }
        let deletedIndexPath = differentIndexes.deletes.map { NSIndexPath(forRow: $0, inSection: section) }
        precondition(insertedIndexPath.count + changedIndexPath.count + deletedIndexPath.count == numberOfRowInSectionAfterUpdate)
        beginUpdates()
        deleteRowsAtIndexPaths(deletedIndexPath, withRowAnimation: deleteAnimation)
        insertRowsAtIndexPaths(insertedIndexPath, withRowAnimation: insertAnimation)
        reloadRowsAtIndexPaths(changedIndexPath, withRowAnimation: loadingAnimation)
        endUpdates()
    }

    func differentIndexesBetween(before: Int,and after: Int) -> (inserts: [Int], deletes: [Int], changes: [Int]) {

        let reloadedIndexSet = Array(0..<min(before, after))
        var insertedIndexSet = [Int]()
        var deletedIndexSet = [Int]()

        if before < after {
            insertedIndexSet = Array(before..<after)
        } else if after < before {
            deletedIndexSet = Array(after..<before)
        }

        return (insertedIndexSet, deletedIndexSet, reloadedIndexSet)
    }

```
