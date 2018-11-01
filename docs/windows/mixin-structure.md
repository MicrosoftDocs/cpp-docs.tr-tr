---
title: MixIn Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::MixIn
helpviewer_keywords:
- MixIn structure
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
ms.openlocfilehash: e6c4fb2abd6c27f8feec4357e17ef71b385cb7a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50464941"
---
# <a name="mixin-structure"></a>MixIn Yapısı

Bir çalışma zamanı sınıf varsa Windows çalışma zamanı arabirimleri ve ardından klasik COM arabirimleri türetilen sağlar.

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
Türetilmiş bir tür [uygular](../windows/implements-structure.md) yapısı.

*MixInType*<br/>
Bir taban türü.

*hasImplements*<br/>
**doğru** varsa *MixInType* olan geçerli uygulamasından türetilmiş temel tür; **false** Aksi takdirde.

## <a name="remarks"></a>Açıklamalar

Windows çalışma zamanı hem sınıf COM arabirimleri türetilmiş bir sınıf, sınıf bildirimi listesi Windows çalışma zamanı arabirimlerden önce listelemesi gerekir ve ardından tüm klasik COM arabirimleri. **MixIn** arabirimler doğru sırada belirtilir sağlar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`MixIn`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)