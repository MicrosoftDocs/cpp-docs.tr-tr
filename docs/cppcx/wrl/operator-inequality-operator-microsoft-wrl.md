---
description: 'Daha fazla bilgi edinin: operator! = Işleci (Microsoft:: WRL)'
title: operator!= İşleç (Microsoft::WRL)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::operator!=
ms.assetid: 785435da-87a6-4454-9bce-9d288a96dc26
ms.openlocfilehash: 69385c81ee401e7fdd47077b21fbc5342eaa091a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330788"
---
# <a name="operator-operator-microsoftwrl"></a>operator!= İşleç (Microsoft::WRL)

[ComPtr](comptr-class.md) ve [ComPtrRef](comptrref-class.md) nesneleri için eşitsizlik işleci.

## <a name="syntax"></a>Sözdizimi

```cpp
WRL_NOTHROW bool operator!=(
   const ComPtr<T>& a,
   const ComPtr<U>& b
);
WRL_NOTHROW bool operator!=(
   const ComPtr<T>& a,
   decltype(__nullptr)
);
WRL_NOTHROW bool operator!=(
   decltype(__nullptr),
   const ComPtr<T>& a
);
WRL_NOTHROW bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   const Details::ComPtrRef<ComPtr<U>>& b
);
WRL_NOTHROW bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   decltype(__nullptr)
);
WRL_NOTHROW bool operator!=(
   decltype(__nullptr),
   const Details::ComPtrRef<ComPtr<T>>& a
);
WRL_NOTHROW bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   void* b
);
WRL_NOTHROW bool operator!=(
   void* b,
   const Details::ComPtrRef<ComPtr<T>>& a
);
```

### <a name="parameters"></a>Parametreler

*a*<br/>
Sol nesne.

*kenarı*<br/>
Doğru nesne.

## <a name="return-value"></a>Dönüş Değeri

**`true`** nesneler eşitse; Aksi takdirde, **`false`** .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Client. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL ad alanı](microsoft-wrl-namespace.md)
