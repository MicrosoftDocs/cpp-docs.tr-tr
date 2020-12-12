---
description: 'Daha fazla bilgi edinin: MixIn Yapısı'
title: MixIn Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::MixIn
helpviewer_keywords:
- MixIn structure
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
ms.openlocfilehash: a438fb6846ae6ba88aaaa968d7b94e8d6636c4aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209392"
---
# <a name="mixin-structure"></a>MixIn Yapısı

Çalışma zamanı sınıfının, varsa ve klasik COM arabirimlerinden Windows Çalışma Zamanı arabirimlerinden türemesini sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template<
    typename Derived,
    typename MixInType,
    bool hasImplements = __is_base_of(Details::ImplementsBase, MixInType)
>
struct MixIn;
```

### <a name="parameters"></a>Parametreler

*Türetilmiş*<br/>
[Uygulayan](implements-structure.md) yapıdan türetilmiş bir tür.

*MixInType*<br/>
Temel tür.

*hasImplements*<br/>
**`true`***Mixintype* , geçerli uygulamadan türetildiyse, temel tür; **`false`** Aksi takdirde.

## <a name="remarks"></a>Açıklamalar

Bir sınıf hem Windows Çalışma Zamanı hem de sınıf COM arabirimlerinden türetildiyse, sınıf bildirim listesi öncelikle tüm Windows Çalışma Zamanı arabirimlerini ve ardından klasik tüm COM arabirimlerini listemelidir. **Mixin** , arabirimlerin doğru sırada belirtilmesini sağlar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`MixIn`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL ad alanı](microsoft-wrl-namespace.md)
