---
title: Veri getirme | Microsoft Docs
ms.custom: ''
ms.date: 10/19/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- data [C++], fetching
- rowsets [C++], fetching
- fetching
- OLE DB consumer templates [C++], fetching data
ms.assetid: b07f747f-9855-4f27-a03d-b1d5b10fa284
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4f0467d322242bb222e5365b45a57e1aa2fe2943
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49807477"
---
# <a name="fetching-data"></a>Veri Getirme

Veri kaynağı, oturum ve rowset nesneleri açtıktan sonra veri getirebilir. Kullanmakta olduğunuz erişimci türüne bağlı olarak, sütunların bağlama gerekebilir.

## <a name="to-fetch-data"></a>Verileri getirmek için

1. Uygun kullanarak satır açın **açık** komutu.

1. Kullanıyorsanız `CManualAccessor`, zaten yapmadıysanız, çıktı sütunlarını bağlayın. Aşağıdaki örnek runbook'undan [DBVIEWER](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/dbviewer) örnek. Sütunları bağlamak için çağrı `GetColumnInfo`, aşağıdaki örnekte gösterildiği gibi bir erişimci bağlamalarla sonra oluşturun:

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

1. Yazma bir **sırada** verileri almak üzere döngü. Döngüde çağrı `MoveNext` imleç geçin ve aşağıdaki örnekte gösterildiği gibi S_OK dönüş değerini test etmek için:

    ```cpp
    while (rs.MoveNext() == S_OK)
    {
        // Add code to fetch data here
        // If you are not using an auto accessor, call rs.GetData()
    }
    ```

1. İçinde **sırada** döngüsü, erişimci türüne göre veri getirebilirsiniz.

   - Kullanırsanız [CAccessor](../../data/oledb/caccessor-class.md) sınıfı veri üyelerini içeren bir kullanıcı kaydı olmalıdır. Aşağıdaki örnekte gösterildiği gibi bu veri üyelerini kullanarak verilerinize erişebilirsiniz:

        ```cpp
        while (rs.MoveNext() == S_OK)
        {
            // Use the data members directly. In this case, m_nFooID
            // is declared in a user record that derives from
            // CAccessor
            wsprintf_s("%d", rs.m_nFooID);
        }
        ```

   - Kullanırsanız `CDynamicAccessor` veya `CDynamicParameterAccessor` sınıfı erişim işlevlerini kullanarak veri getirebilirsiniz `GetValue` ve `GetColumn`, aşağıdaki örnekte gösterildiği gibi. Veri türünü belirlemek istiyorsanız kullanmakta olduğunuz, kullanın `GetType`.

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

   - Kullanırsanız `CManualAccessor`, kendi veri üyeleri belirtin, bunları bağlamak ve gerekir aşağıdaki örnekte gösterildiği gibi doğrudan erişim:

        ```cpp
        while (rs.MoveNext() == S_OK)
        {
            // Use the data members you specified in the calls to
            // AddBindEntry.

            wsprintf_s("%s", szFoo);
        }
        ```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-consumer-templates.md)
