---
title: RemoveIUnknown Sınıfı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::RemoveIUnknown
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
ms.openlocfilehash: 06b3ec86874bcf7968483eb4557b6b6b247ecdfe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50556357"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)