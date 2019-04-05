---
title: RemoveIUnknown Sınıfı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::RemoveIUnknown
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
ms.openlocfilehash: 3b54f6a3072d82d40db4ac698503f0939e745472
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59036779"
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

Eşdeğer olan bir tür yapar bir `IUnknown`-tabanlı ancak türünde sanal olmayan `QueryInterface`, `AddRef`, ve `Release` üye işlevleri.

Varsayılan olarak, COM yöntemleri sanal sağlamak `QueryInterface`, `AddRef`, ve `Release` yöntemleri. Ancak, `ComPtr` sanal yöntemler getirdiği ek yüke gerek kalmaz. `RemoveIUnknown` özel, sanal olmayan sağlayarak bu ek yükü ortadan kalkar `QueryInterface`, `AddRef`, ve `Release` yöntemleri.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`ReturnType`|Şablon parametresine eşdeğerdir bir türe ilişkin bir eşanlam *T* ancak sanal olmayan `IUnknown` üyeleri.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`T`

`RemoveIUnknown`

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL::Details Ad Alanı](microsoft-wrl-details-namespace.md)