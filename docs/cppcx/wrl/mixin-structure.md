---
title: MixIn Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::MixIn
helpviewer_keywords:
- MixIn structure
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
ms.openlocfilehash: d0306f4c497dd26e782b1ef2c012cb7d348db07f
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787873"
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
Türetilmiş bir tür [uygular](implements-structure.md) yapısı.

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

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)