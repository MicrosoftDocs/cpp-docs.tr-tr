---
title: SafeLessThan | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeLessThan
dev_langs:
- C++
helpviewer_keywords:
- SafeLessThan function
ms.assetid: 9d85bc0d-8d94-4d59-9b72-ef3c63a120a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a5824b1e3ba050cf8c6d9c0f7b56231211f1f59a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377207"
---
# <a name="safelessthan"></a>SafeLessThan

Bir sayı daha az olup olmadığını belirler.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T, typename U>
inline bool SafeLessThan (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Parametreler

*T*<br/>
[in] İlk sayı. Bu tür olmalıdır `T`.

*u*<br/>
[in] İkinci numarası. Bu tür olmalıdır `U`.

## <a name="return-value"></a>Dönüş Değeri

**doğru** varsa *t* olduğu küçüktür *u*; Aksi takdirde **false**.

## <a name="remarks"></a>Açıklamalar

Bu yöntem standart karşılaştırma işleci, çünkü geliştirir. **SafeLessThan** numarası iki farklı türde karşılaştırmanızı sağlar.

Bu yöntem, parçasıdır [SafeInt Kitaplığı](../windows/safeint-library.md) örneği oluşturmaya gerek kalmadan tek bir karşılaştırma işlemi için tasarlanmış ve [SafeInt sınıfı](../windows/safeint-class.md).

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
[SafeLessThanEquals](../windows/safelessthanequals.md)<br/>
[SafeGreaterThan](../windows/safegreaterthan.md)<br/>
[SafeGreaterThanEquals](../windows/safegreaterthanequals.md)