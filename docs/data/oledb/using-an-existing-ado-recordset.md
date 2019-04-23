---
title: Varolan ADO Kayıt Kümesini Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- ADO recordsets [C++]
- OLE DB consumer templates, ADO recordsets
- recordsets [C++], using in OLE DB
ms.assetid: a9b1de8a-d379-49b1-a26e-578741e9f6a8
ms.openlocfilehash: eb558bb319bb5ddb61d0383846099d708f99c627
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59030500"
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

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)