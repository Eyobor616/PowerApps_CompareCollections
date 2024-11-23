# PowerApps_CompareCollections

In Powerapps, I have two collections, the IDs of collection B are all in collection A, I would like to filter collection A where the ID does not match that of B



Filter(
        CollectionA,
        Not(
            ID in CollectionB.ID
        )
    )

![WhatsApp Image 2024-10-22 at 21 28 15_478fec74](https://github.com/user-attachments/assets/e94e1f2c-5528-4faa-bf35-f7c6bed62a87)


![WhatsApp Image 2024-10-22 at 21 31 01_cf41b95c](https://github.com/user-attachments/assets/507c37a8-b4fd-47f2-992c-6e624ff93610)


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
