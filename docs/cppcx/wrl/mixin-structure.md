---
title: MixIn Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::MixIn
helpviewer_keywords:
- MixIn structure
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
ms.openlocfilehash: cfa03706bc6030b337009f7228466a26e242aa6b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221542"
---
# <a name="mixin-structure"></a>MixIn Yapısı

Çalışma zamanı sınıfının, varsa ve klasik COM arabirimlerinden Windows Çalışma Zamanı arabirimlerinden türemesini sağlar.

## <a name="syntax"></a>Söz dizimi

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
