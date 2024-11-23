# PowerApps_CompareCollections

In Powerapps, I have two collections, the IDs of collection B are all in collection A, I would like to filter collection A where the ID does not match that of B



Filter(
        CollectionA,
        Not(
            ID in CollectionB.ID
        )
    )



    ========


    Sort(
Switch(TabList2_1.Selected.Value,
"Member",

        Filter(colDistributionList_Group,
        id in colMemberGroups.Value, 
        IsBlank(txtSearchDistirbutionListName_1.Value) || StartsWith(displayName,txtSearchDistirbutionListName_1.Value),
        IsBlank(txtSearchDistirbutionListMail_1.Value) || StartsWith(mail,txtSearchDistirbutionListMail_1.Value)),

"Non Member",

        Filter(colDistributionList_Group,
        Not ( id in colMemberGroups.Value),
        IsBlank(txtSearchDistirbutionListName_1.Value) || StartsWith(displayName,txtSearchDistirbutionListName_1.Value),
        IsBlank(txtSearchDistirbutionListMail_1.Value) || StartsWith(mail,txtSearchDistirbutionListMail_1.Value))

), displayName, SortOrder.Ascending)
