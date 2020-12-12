---
description: 'Daha fazla bilgi edinin: RemoveIUnknown Sınıfı'
title: RemoveIUnknown Sınıfı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::RemoveIUnknown
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
ms.openlocfilehash: 0ef00ee9859a27252550aaeec6fb9b4f9ef2d5b8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278733"
---
# <a name="removeiunknown-class"></a>RemoveIUnknown Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T>
struct RemoveIUnknown;

template <typename T>
class RemoveIUnknown : public T;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Bir sınıf.

## <a name="remarks"></a>Açıklamalar

, `IUnknown` Tabanlı bir türe eşdeğer, ancak sanal olmayan `QueryInterface` , `AddRef` ve üye işlevlere sahip bir tür yapar `Release` .

Varsayılan olarak, COM yöntemleri sanal `QueryInterface` , `AddRef` ve yöntemleri sağlar `Release` . Ancak, `ComPtr` Sanal yöntemlerin ek yükünü gerektirmez. `RemoveIUnknown` Özel, sanal olmayan `QueryInterface` , ve yöntemleri sağlayarak bu ek yükü ortadan kaldırır `AddRef` `Release` .

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`ReturnType`|Şablon parametresi *T* , ancak sanal olmayan üyelere denk gelen bir tür için eş anlamlı `IUnknown` .|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`T`

`RemoveIUnknown`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Client. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL::D euçlar ad alanı](microsoft-wrl-details-namespace.md)
