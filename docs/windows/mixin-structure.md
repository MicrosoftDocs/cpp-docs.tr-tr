---
title: Mixın yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::MixIn
dev_langs:
- C++
helpviewer_keywords:
- MixIn structure
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1b6aa9b8e27aa4eaf3e581db59f2c9d2c7201d39
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386806"
---
# <a name="mixin-structure"></a>MixIn Yapısı

Bir çalışma zamanı sınıf varsa Windows çalışma zamanı arabirimleri ve ardından klasik COM arabirimleri türetilen sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template<
   typename Derived,
   typename MixInType,
   bool hasImplements = __is_base_of(Details::ImplementsBase,
   MixInType)  
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