---
description: 'Hakkında daha fazla bilgi edinin: _com_ptr_t:: QueryInterface'
title: _com_ptr_t::QueryInterface
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
helpviewer_keywords:
- QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
ms.openlocfilehash: 6c6ff19227c920aade762af295942d8058a17ad3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295347"
---
# <a name="_com_ptr_tqueryinterface"></a>_com_ptr_t::QueryInterface

**Microsoft'a Özgü**

Kapsüllenmiş arabirim  İşaretçisinde ' ın QueryInterface üye işlevini çağırır `IUnknown` .

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
`IID` bir arabirim işaretçisi.

*Lama*<br/>
Ham arabirim işaretçisi.

## <a name="remarks"></a>Açıklamalar

`IUnknown::QueryInterface`Kapsüllenmiş arabirim İşaretçisinde belirtilen `IID` ' i çağırır ve sonuç olarak *p* içindeki ham arabirim işaretçisini döndürür. Bu yordam, başarılı veya başarısız olduğunu göstermek için HRESULT döndürür.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t sınıfı](../cpp/com-ptr-t-class.md)
