---
title: Interfacetraits::Verify yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::Verify
dev_langs:
- C++
helpviewer_keywords:
- Verify method
ms.assetid: 46edd67f-7952-4552-a157-55e823f616c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e1950d6e9d5195ece315863b664b42411231184d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415388"
---
# <a name="interfacetraitsverify-method"></a>InterfaceTraits::Verify Yöntemi

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
__forceinline static void Verify();
```

## <a name="remarks"></a>Açıklamalar

Doğrular `Base` düzgün şekilde türetilir.

Hakkında daha fazla bilgi için `Base`, bkz: **genel Typedefler** konusundaki [Interfacetraits yapısı](../windows/interfacetraits-structure.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[InterfaceTraits Yapısı](../windows/interfacetraits-structure.md)<br/>
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)