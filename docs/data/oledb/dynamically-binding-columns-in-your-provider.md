---
title: Sütunları dinamik olarak bağlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- columns [C++], dynamic column binding
- dynamic column binding
- providers [C++], dynamic column binding
ms.assetid: 45e811e3-f5a7-4627-98cc-bf817c4e556e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: de3c278ece6b53528ce0f013f35780e60fda9531
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50057679"
---
# <a name="dynamically-binding-columns-in-your-provider"></a>Sağlayıcınızdaki Sütunları Dinamik Olarak Bağlama

Dinamik sütun bağlama ihtiyacınız olduğundan emin olun. Çünkü gerekebilir:

- Derleme zamanında, satır kümesi sütunlarının tanımlı değil.

- Yer işaretleri gibi sütunları ekler bir öğenin desteklediğiniz.

## <a name="to-implement-dynamic-column-binding"></a>Dinamik sütun bağlama uygulamak için

1. Kaldırmak `PROVIDER_COLUMN_MAP`kodunuzdan s.

1. Kullanıcı kaydı (yapınızı), aşağıdaki bildirimi ekleyin:

    ```cpp
    static ATLCOLUMNINFO* GetColumnInfo(void* pThis, ULONG* pcCols);
    ```

1. Uygulama `GetColumnInfo` işlevi. Bu işlev, bilgilerin nasıl depolandığını yerleştirir. Özellikleri veya bu işlevi diğer bilgilerini almak gerekebilir. Benzer bir makro oluşturmak isteyebilirsiniz [COLUMN_ENTRY](../../data/oledb/column-entry.md) kendi bilgilerini eklemek için makro.

   Aşağıdaki örnekte gösterildiği bir `GetColumnInfo` işlevi.

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

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)