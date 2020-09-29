---
title: Sağlayıcınızdaki Sütunları Dinamik Olarak Bağlama
ms.date: 11/04/2016
helpviewer_keywords:
- columns [C++], dynamic column binding
- dynamic column binding
- providers [C++], dynamic column binding
ms.assetid: 45e811e3-f5a7-4627-98cc-bf817c4e556e
ms.openlocfilehash: 3eee52004e1418b3e756a78c8c2a04040d0bd7ff
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91501850"
---
# <a name="dynamically-binding-columns-in-your-provider"></a>Sağlayıcınızdaki Sütunları Dinamik Olarak Bağlama

Dinamik sütun bağlamaya gerçekten ihtiyacınız olduğundan emin olun. Bunun nedeni şunlar olabilir:

- Satır kümesi sütunlarınız derleme zamanında tanımlı değil.

- Sütunları ekleyen yer işareti gibi bir öğeyi destekleyebilirsiniz.

## <a name="to-implement-dynamic-column-binding"></a>Dinamik sütun bağlamayı uygulamak için

1. `PROVIDER_COLUMN_MAP`Kodınızdan her türlü öğeleri kaldırın.

1. Kullanıcı kaydında (yapınızı) aşağıdaki bildirimi ekleyin:

    ```cpp
    static ATLCOLUMNINFO* GetColumnInfo(void* pThis, ULONG* pcCols);
    ```

1. İşlevini uygulayın `GetColumnInfo` . Bu işlev, bilgilerin nasıl depolandığını yerleştirir. Bu işlev için özellikleri veya diğer bilgileri almanız gerekebilir. Kendi bilgilerinizi eklemek için [COLUMN_ENTRY](./macros-and-global-functions-for-ole-db-consumer-templates.md#column_entry) makroya benzer bir makro oluşturmak isteyebilirsiniz.

   Aşağıdaki örnek bir işlevi gösterir `GetColumnInfo` .

    ```cpp
    // Check the property flag for bookmarks, if it is set, set the zero
    // ordinal entry in the column map with the bookmark information.
    CAgentRowset* pRowset = (CAgentRowset*) pThis;
    CComQIPtr<IRowsetInfo, &IID_IRowsetInfo> spRowsetProps = pRowset;

    CDBPropIDSet set(DBPROPSET_ROWSET);
    set.AddPropertyID(DBPROP_BOOKMARKS);
    DBPROPSET* pPropSet = NULL;
    ULONG ulPropSet = 0;
    HRESULT hr;

    if (spRowsetProps)
       hr = spRowsetProps->GetProperties(1, &set, &ulPropSet, &pPropSet);

    if (pPropSet)
    {
       CComVariant var = pPropSet->rgProperties[0].vValue;
       CoTaskMemFree(pPropSet->rgProperties);
       CoTaskMemFree(pPropSet);

       if (SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE))
       {
          ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD), DBTYPE_BYTES,
             0, 0, GUID_NULL, CAgentMan, dwBookmark, DBCOLUMNFLAGS_ISBOOKMARK)
          ulCols++;
       }
    }

    // Next, set up the other columns.
    ADD_COLUMN_ENTRY(ulCols, OLESTR("Command"), 1, 256, DBTYPE_STR, 0xFF, 0xFF,
       GUID_NULL, CAgentMan, szCommand)
    ulCols++;
    ADD_COLUMN_ENTRY(ulCols, OLESTR("Text"), 2, 256, DBTYPE_STR, 0xFF, 0xFF,
       GUID_NULL, CAgentMan, szText)
    ulCols++;

    ADD_COLUMN_ENTRY(ulCols, OLESTR("Command2"), 3, 256, DBTYPE_STR, 0xFF, 0xFF,
       GUID_NULL, CAgentMan, szCommand2)
    ulCols++;
    ADD_COLUMN_ENTRY(ulCols, OLESTR("Text2"), 4, 256, DBTYPE_STR, 0xFF, 0xFF,
       GUID_NULL, CAgentMan, szText2)
    ulCols++;

    if (pcCols != NULL)
       *pcCols = ulCols;

    return _rgColumns;
    }
    ```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonlarıyla çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)
