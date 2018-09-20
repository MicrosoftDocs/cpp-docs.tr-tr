---
title: EventTargetArray::Begin yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::Begin
dev_langs:
- C++
helpviewer_keywords:
- Begin method
ms.assetid: 1cc7fdfd-a2c4-4b28-93cf-1c82842294ba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b818595d8ad32295dbce1498161898b215e1885f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433783"
---
# <a name="eventtargetarraybegin-method"></a>EventTargetArray::Begin Yöntemi

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
ComPtr<IUnknown>* Begin();
```

## <a name="return-value"></a>Dönüş Değeri

Olay işleyicileri iç dizideki ilk öğe adresi.

## <a name="remarks"></a>Açıklamalar

Olay işleyicilerini iç dizideki ilk öğenin adresi alır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** event.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[EventTargetArray Sınıfı](../windows/eventtargetarray-class.md)<br/>
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)