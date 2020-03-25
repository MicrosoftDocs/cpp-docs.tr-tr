---
title: Varolan ADO Kayıt Kümesini Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- ADO recordsets [C++]
- OLE DB consumer templates, ADO recordsets
- recordsets [C++], using in OLE DB
ms.assetid: a9b1de8a-d379-49b1-a26e-578741e9f6a8
ms.openlocfilehash: 48f6eb3bac34b37f495b9492e19b4197ed69cca3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209358"
---
# <a name="using-an-existing-ado-recordset"></a>Varolan ADO Kayıt Kümesini Kullanma

OLE DB tüketici şablonları ve etkin veri nesneleri (ADO) karıştırmak için, bir kayıt kümesi açmak üzere ADO kullanın (OLE DB tüketici şablonlarındaki bir satır kümesine karşılık gelir). Bir kayıt kümeniz olduğunda, OLE DB bir satır kümesine bağlanmak için aşağıdakileri yapın:

1. `IRowset` ve `IAccessor` işaretçileri için `QueryInterface` çağırın.

    ```cpp
    IRowset* lpRowset = NULL;
    IAccessor* lpAccessor = NULL;
    lpUnk->QueryInterface(IID_IRowset, (void**)&lpRowset);
    lpUnk->QueryInterface(IID_IAccessor, (void**)&lpAccessor);
    ```

    > [!NOTE]
    > *lpUnk* , ADO kayıt kümesinin `IUnknown` nesnesine işaret eder.

1. Erişimci ve satır kümesini uygun OLE DB Tüketici şablonu sınıflarına iliştirin.

    ```cpp
    CRowset rs;
    CAccessor accessor;

    accessor.AddAccessorInfo(0ul);      // 0 is the ordinal of an ADO accessor
    rs.m_spRowset.Attach(lpRowset);      // use the Attach method of CComPtr<>
    rs.SetAccessor(accessor);
    ```

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)
