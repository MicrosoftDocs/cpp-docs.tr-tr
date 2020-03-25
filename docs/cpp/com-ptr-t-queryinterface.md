---
title: _com_ptr_t::QueryInterface
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
helpviewer_keywords:
- QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
ms.openlocfilehash: 26dda2dff83ff0adbb7ef05c5e75f64b44138bd8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170677"
---
# <a name="_com_ptr_tqueryinterface"></a>_com_ptr_t::QueryInterface

**Microsoft 'a özgü**

Kapsüllenmiş arabirim İşaretçisinde `IUnknown` **QueryInterface** üye işlevini çağırır.

## <a name="syntax"></a>Sözdizimi

```
template<typename _InterfaceType> HRESULT QueryInterface (
   const IID& iid,
   _InterfaceType*& p
) throw ( );
template<typename _InterfaceType> HRESULT QueryInterface (
   const IID& iid,
   _InterfaceType** p
) throw( );
```

#### <a name="parameters"></a>Parametreler

*'si*<br/>
bir arabirim işaretçisinin `IID`.

*Lama*<br/>
Ham arabirim işaretçisi.

## <a name="remarks"></a>Açıklamalar

Kapsüllenmiş arabirim İşaretçisinde belirtilen `IID` sahip `IUnknown::QueryInterface` çağırır ve sonuç olarak *p*'deki ham arabirim işaretçisini döndürür. Bu yordam, başarılı veya başarısız olduğunu göstermek için HRESULT döndürür.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)
