---
title: Varolan ADO kayıt kümesini kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ADO recordsets [C++]
- OLE DB consumer templates, ADO recordsets
- recordsets [C++], using in OLE DB
ms.assetid: a9b1de8a-d379-49b1-a26e-578741e9f6a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1433b51a6dfe6f558b98360812e694d42ebfb9f5
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50051959"
---
# <a name="using-an-existing-ado-recordset"></a>Varolan ADO Kayıt Kümesini Kullanma

OLE DB Tüketici Şablonları ve etkin Data Objects (ADO) karıştırmak için bir kayıt kümesi (OLE DB Tüketici Şablonları bir satır kümesinde karşılık gelen) açmak için ADO kullanın. Bir kayıt varsa, bir OLE DB satır kümesine bağlanmak için aşağıdakileri yapın:

1. Çağrı `QueryInterface` için `IRowset` ve `IAccessor` işaretçileri.

    ```cpp
    IRowset* lpRowset = NULL;
    IAccessor* lpAccessor = NULL;
    lpUnk->QueryInterface(IID_IRowset, (void**)&lpRowset);
    lpUnk->QueryInterface(IID_IAccessor, (void**)&lpAccessor);
    ```

    > [!NOTE]
    > *lpUnk* işaret `IUnknown` ADO kayıt kümesini nesne.

1. Kendi uygun OLE DB tüketici şablonu sınıfları için erişimci ve satır kümesi ekleyin.

    ```cpp
    CRowset rs;
    CAccessor accessor;

    accessor.AddAccessorInfo(0ul);      // 0 is the ordinal of an ADO accessor
    rs.m_spRowset.Attach(lpRowset);      // use the Attach method of CComPtr<>
    rs.SetAccessor(accessor);
    ```

## <a name="see-also"></a>Ayrıca Bkz.

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)