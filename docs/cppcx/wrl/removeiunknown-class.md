---
title: RemoveIUnknown Sınıfı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::RemoveIUnknown
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
ms.openlocfilehash: cfcdefbb8d7cd12d2ebf99710f595fdd2fc16f76
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213622"
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

*Şı*<br/>
Bir sınıf.

## <a name="remarks"></a>Açıklamalar

`IUnknown`tabanlı bir türe eşdeğer, ancak sanal olmayan `QueryInterface`, `AddRef`ve `Release` üye işlevleri içeren bir tür yapar.

Varsayılan olarak, COM yöntemleri sanal `QueryInterface`, `AddRef`ve `Release` yöntemler sağlar. Ancak, `ComPtr` Sanal yöntemlerin ek yükünü gerektirmez. `RemoveIUnknown`, özel, sanal olmayan `QueryInterface`, `AddRef`ve `Release` yöntemleri sunarak bu ek yükü ortadan kaldırır.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`ReturnType`|Şablon parametresi *T* , ancak sanal olmayan `IUnknown` üyelerine denk gelen bir tür için eş anlamlı.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`T`

`RemoveIUnknown`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Client. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL::Details Ad Alanı](microsoft-wrl-details-namespace.md)
