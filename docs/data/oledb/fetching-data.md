---
title: Veri Getirme
ms.date: 10/19/2018
helpviewer_keywords:
- data [C++], fetching
- rowsets [C++], fetching
- fetching
- OLE DB consumer templates [C++], fetching data
ms.assetid: b07f747f-9855-4f27-a03d-b1d5b10fa284
ms.openlocfilehash: 919eb059f5d3f29d491bf7a6598b0c77163bd783
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87184650"
---
# <a name="fetching-data"></a>Veri Getirme

Veri kaynağını, oturumu ve satır kümesi nesnelerini açtıktan sonra verileri getirebilirsiniz. Kullanmakta olduğunuz erişimcinin türüne bağlı olarak, sütunları bağlamanız gerekebilir.

## <a name="to-fetch-data"></a>Veri getirmek için

1. Uygun **Aç** komutunu kullanarak satır kümesini açın.

1. Kullanıyorsanız `CManualAccessor` , daha önce yapmadıysanız çıkış sütunlarını bağlayın. Aşağıdaki örnek [DBViewer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/dbviewer) örneğinden alınmıştır. Sütunları bağlamak için `GetColumnInfo` Aşağıdaki örnekte gösterildiği gibi, öğesini çağırın ve bağlamalarla bir erişimci oluşturun:

    ```cpp
    // From the DBViewer Sample CDBTreeView::OnQueryEdit
    // Get the column information
    ULONG ulColumns       = 0;
    DBCOLUMNINFO* pColumnInfo  = NULL;
    LPOLESTR pStrings      = NULL;
    if (rs.GetColumnInfo(&ulColumns, &pColumnInfo, &pStrings) != S_OK)
        ThrowMyOLEDBException(rs.m_pRowset, IID_IColumnsInfo);
    struct MYBIND* pBind = new MYBIND[ulColumns];
    rs.CreateAccessor(ulColumns, &pBind[0], sizeof(MYBIND)*ulColumns);
    for (ULONG l=0; l<ulColumns; l++)
    rs.AddBindEntry(l+1, DBTYPE_STR, sizeof(TCHAR)*40, &pBind[l].szValue, NULL, &pBind[l].dwStatus);
    rs.Bind();
    ```

1. **`while`** Verileri almak için bir döngü yazın. Döngüsünde, `MoveNext` Aşağıdaki örnekte gösterildiği gibi imleci ilerletmek ve döndürülen değeri S_OK karşı test etmek için çağırın:

    ```cpp
    while (rs.MoveNext() == S_OK)
    {
        // Add code to fetch data here
        // If you are not using an auto accessor, call rs.GetData()
    }
    ```

1. Döngü içinde **`while`** , erişimci türüne göre verileri getirebilirsiniz.

   - [CAccessor](../../data/oledb/caccessor-class.md) sınıfını kullanıyorsanız, veri üyeleri içeren bir kullanıcı kaydınız olmalıdır. Aşağıdaki örnekte gösterildiği gibi, bu veri üyelerini kullanarak verilerinize erişebilirsiniz:

        ```cpp
        while (rs.MoveNext() == S_OK)
        {
            // Use the data members directly. In this case, m_nFooID
            // is declared in a user record that derives from
            // CAccessor
            wsprintf_s("%d", rs.m_nFooID);
        }
        ```

   - `CDynamicAccessor`Veya `CDynamicParameterAccessor` sınıfını kullanırsanız, `GetValue` `GetColumn` Aşağıdaki örnekte gösterildiği gibi, erişim işlevlerini kullanarak verileri getirebilirsiniz. Kullanmakta olduğunuz veri türünü öğrenmek istiyorsanız kullanın `GetType` .

        ```cpp
        while (rs.MoveNext() == S_OK)
        {
            // Use the dynamic accessor functions to retrieve your data.

            ULONG ulColumns = rs.GetColumnCount();
            for (ULONG i=0; i<ulColumns; i++)
            {
                rs.GetValue(i);
            }
        }
        ```

   - Kullanıyorsanız `CManualAccessor` , aşağıdaki örnekte gösterildiği gibi kendi veri üyelerinizi belirtmeniz, kendiniz bağlamanız ve bunlara doğrudan erişmeniz gerekir:

        ```cpp
        while (rs.MoveNext() == S_OK)
        {
            // Use the data members you specified in the calls to
            // AddBindEntry.

            wsprintf_s("%s", szFoo);
        }
        ```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonlarıyla çalışma](../../data/oledb/working-with-ole-db-consumer-templates.md)
