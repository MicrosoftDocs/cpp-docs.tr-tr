---
title: WeakRef::operator&amp; işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::operator&
dev_langs:
- C++
helpviewer_keywords:
- operator& operator
ms.assetid: 900afb73-3801-4d08-9b41-2e6a62011ccd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f8bb81ca1591fc398b1d0814fca918309169e82c
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600990"
---
# <a name="weakrefoperatoramp-operator"></a>WeakRef::operator&amp; işleci

Döndürür bir `ComPtrRef` geçerli temsil eden nesne **WeakRef** nesne.

## <a name="syntax"></a>Sözdizimi

```cpp
Details::ComPtrRef<WeakRef> operator&() throw()  
```

## <a name="return-value"></a>Dönüş Değeri

A `ComPtrRef` geçerli temsil eden nesne **WeakRef** nesne.

## <a name="remarks"></a>Açıklamalar

Kodunuzda kullanılmak üzere tasarlanmamıştır iç Yardımcısı operatörün budur.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[WeakRef Sınıfı](../windows/weakref-class.md)