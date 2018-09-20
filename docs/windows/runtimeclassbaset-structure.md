---
title: RuntimeClassBaseT yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT
dev_langs:
- C++
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bcfce810dff7862c60fca853b216eeb05d09dd0f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46414907"
---
# <a name="runtimeclassbaset-structure"></a>RuntimeClassBaseT Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   unsigned int RuntimeClassTypeT
>
friend struct Details::RuntimeClassBaseT;
```

### <a name="parameters"></a>Parametreler

*RuntimeClassTypeT*<br/>
Bir veya daha fazla belirten bayraklar alanı [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) numaralandırıcılar.

## <a name="remarks"></a>Açıklamalar

İçin yardımcı yöntemleri sağlar `QueryInterface` işlemler ve başlangıç arabirim kimliği.

## <a name="members"></a>Üyeler

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`RuntimeClassBaseT`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)