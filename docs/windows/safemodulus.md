---
title: SafeModulus | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeModulus
dev_langs:
- C++
helpviewer_keywords:
- SafeModulus function
ms.assetid: ae5c81eb-5dcf-45a5-aa76-465fdfe68654
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 48feb16696243479849492171732b0d070ce032f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427920"
---
# <a name="safemodulus"></a>SafeModulus

İki sayıyı mod işlemi gerçekleştirir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T, typename U>
inline bool SafeModulus (
   const T t,
   const U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Parametreler

*T*<br/>
[in] Bölen. Bu tür olmalıdır `T`.

*u*<br/>
[in] Bölünen. Bu tür olmalıdır `U`.

*Sonuç*<br/>
[out] Parametrenin nereden **SafeModulus** sonucu depolar.

## <a name="return-value"></a>Dönüş Değeri

**doğru** Eğer hiç Hata oluşmazsa; **false** hata oluşması durumunda.

## <a name="remarks"></a>Açıklamalar

Bu yöntem, parçasıdır [SafeInt Kitaplığı](../windows/safeint-library.md) örneği oluşturulmadan tek mod işlemi için tasarlanmış ve [SafeInt sınıfı](../windows/safeint-class.md).

> [!NOTE]
> Bu yöntem, yalnızca tek bir matematiksel işlem korunması gereken durumlarda kullanılmalıdır. Birden çok işlem varsa, kullanması gereken `SafeInt` tek tek başına işlevleri çağırmak yerine sınıfı.

Şablon türleri hakkında daha fazla bilgi için `T` ve `U`, bkz: [SafeInt işlevleri](../windows/safeint-functions.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** safeint.h

**Namespace:** Microsoft::Utilities

## <a name="see-also"></a>Ayrıca Bkz.

[SafeInt İşlevleri](../windows/safeint-functions.md)<br/>
[SafeInt Kitaplığı](../windows/safeint-library.md)<br/>
[SafeInt Sınıfı](../windows/safeint-class.md)<br/>
[SafeDivide](../windows/safedivide.md)