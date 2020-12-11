---
description: 'Hakkında daha fazla bilgi edinin: var olan bir ADO kayıt kümesini kullanma'
title: Varolan ADO Kayıt Kümesini Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- ADO recordsets [C++]
- OLE DB consumer templates, ADO recordsets
- recordsets [C++], using in OLE DB
ms.assetid: a9b1de8a-d379-49b1-a26e-578741e9f6a8
ms.openlocfilehash: 4b5c3b5f621f3cbdba6f2d42fd95436495a5661e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160954"
---
# <a name="using-an-existing-ado-recordset"></a>Varolan ADO Kayıt Kümesini Kullanma

OLE DB tüketici şablonları ve etkin veri nesneleri (ADO) karıştırmak için, bir kayıt kümesi açmak üzere ADO kullanın (OLE DB tüketici şablonlarındaki bir satır kümesine karşılık gelir). Bir kayıt kümeniz olduğunda, OLE DB bir satır kümesine bağlanmak için aşağıdakileri yapın:

1. `QueryInterface` `IRowset` Ve işaretçileri için çağrı `IAccessor` .

    ```cpp
    IRowset* lpRowset = NULL;
    IAccessor* lpAccessor = NULL;
    lpUnk->QueryInterface(IID_IRowset, (void**)&lpRowset);
    lpUnk->QueryInterface(IID_IAccessor, (void**)&lpAccessor);
    ```

    > [!NOTE]
    > *lpUnk* , `IUnknown` ADO kayıt kümesinin nesnesine işaret eder.

1. Erişimci ve satır kümesini uygun OLE DB Tüketici şablonu sınıflarına iliştirin.

    ```cpp
    CRowset rs;
    CAccessor accessor;

    accessor.AddAccessorInfo(0ul);      // 0 is the ordinal of an ADO accessor
    rs.m_spRowset.Attach(lpRowset);      // use the Attach method of CComPtr<>
    rs.SetAccessor(accessor);
    ```

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri kullanma](../../data/oledb/using-accessors.md)
