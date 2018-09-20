---
title: SafeGreaterThanEquals | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeGreaterThanEquals
dev_langs:
- C++
helpviewer_keywords:
- SafeGreaterThanEquals function
ms.assetid: 43312fa9-d925-4f9f-a352-a190c02b3005
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b5b7ab93665ce4f5f15aed68520a130897bdcd90
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46397162"
---
# <a name="safegreaterthanequals"></a>SafeGreaterThanEquals

İki sayıyı karşılaştırır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T, typename U>
inline bool SafeGreaterThanEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Parametreler

*T*<br/>
[in] Karşılaştırılacak birinci sayı. Bu tür olmalıdır `T`.

*u*<br/>
[in] Karşılaştırılacak ikinci sayı. Bu tür olmalıdır `U`.

## <a name="return-value"></a>Dönüş Değeri

**doğru** varsa *t* büyüktür veya eşittir *u*; Aksi takdirde **false**.

## <a name="remarks"></a>Açıklamalar

**SafeGreaterThanEquals** standart karşılaştırma işleci iki farklı tür sayı karşılaştırmanıza olanak sağladığından geliştirir.

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
[SafeGreaterThan](../windows/safegreaterthan.md)<br/>
[SafeLessThanEquals](../windows/safelessthanequals.md)<br/>
[SafeLessThan](../windows/safelessthan.md)