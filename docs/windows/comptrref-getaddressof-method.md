---
title: ComPtrRef::GetAddressOf metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::GetAddressOf
dev_langs:
- C++
helpviewer_keywords:
- GetAddressOf method
ms.assetid: 797df323-a2fa-412b-ab60-32cce3721096
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a0f35bbe2bdc0d0c8d3500e6b157da542458b1fe
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421030"
---
# <a name="comptrrefgetaddressof-method"></a>ComPtrRef::GetAddressOf Metodu

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
InterfaceType* const * GetAddressOf() const;
```

## <a name="return-value"></a>Dönüş Değeri

Adres geçerli tarafından temsil edilen arabirimi için bir işaretçi **ComPtrRef** nesne.

## <a name="remarks"></a>Açıklamalar

Adresi geçerli tarafından temsil edilen arabirimi için bir işaretçi alır **ComPtrRef** nesne.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[ComPtrRef Sınıfı](../windows/comptrref-class.md)<br/>
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)