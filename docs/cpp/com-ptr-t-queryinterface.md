---
title: _com_ptr_t::QueryInterface | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e0add1d8f3fc73f78cee3e10642d7b5a12968a6a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106882"
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