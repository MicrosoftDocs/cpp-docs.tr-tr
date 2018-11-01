---
title: _com_ptr_t::QueryInterface
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
helpviewer_keywords:
- QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
ms.openlocfilehash: 42953c92e4cf31b5ccd02dd51811fc1fdeedbcaf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543838"
---
# <a name="comptrtqueryinterface"></a>_com_ptr_t::QueryInterface

**Microsoft'a özgü**

Çağrıları **QueryInterface** üye işlevinin `IUnknown` kapsüllenmiş arabirim işaretçisini üzerinde.

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

*IID*<br/>
`IID` bir arabirim işaretçisi.

*p*<br/>
Ham arabirim işaretçisi.

## <a name="remarks"></a>Açıklamalar

Çağrıları `IUnknown::QueryInterface` kapsüllenmiş arabirim işaretçisini belirli üzerinde `IID` ve içinde elde edilen ham arabirim işaretçisi döndüren *p*. Bu yordam, başarıyı veya başarısızlığı göstermek için HRESULT döndürür.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)