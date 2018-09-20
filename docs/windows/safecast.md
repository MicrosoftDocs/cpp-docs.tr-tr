---
title: SafeCast | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeCast
dev_langs:
- C++
helpviewer_keywords:
- SafeCast function
ms.assetid: 55316729-8456-403a-9f96-59d4038f67af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 65794dafe5e45cbd4c0e2a7eb49c34377009deee
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392989"
---
# <a name="safecast"></a>SafeCast

Bir başka bir türe sayı türü çevirir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T, typename U>
inline bool SafeCast (
   const T From,
   U& To
);
```

### <a name="parameters"></a>Parametreler

*Kaynak*<br/>
[in] Dönüştürülecek kaynak sayısı. Bu tür olmalıdır `T`.

*Hedef*<br/>
[out] Yeni bir sayı türü referansı. Bu tür olmalıdır `U`.

## <a name="return-value"></a>Dönüş Değeri

**doğru** Eğer hiç Hata oluşmazsa; **false** hata oluşması durumunda.

## <a name="remarks"></a>Açıklamalar

Bu yöntem, parçasıdır [SafeInt Kitaplığı](../windows/safeint-library.md) örneği oluşturulmadan tek atama işlemi için tasarlanmış ve [SafeInt sınıfı](../windows/safeint-class.md).

> [!NOTE]
> Bu yöntem, yalnızca tek bir işlem korunması gereken durumlarda kullanılmalıdır. Birden çok işlem varsa, kullanması gereken `SafeInt` tek tek başına işlevleri çağırmak yerine sınıfı.

T ve U şablon türleri hakkında daha fazla bilgi için bkz. [SafeInt işlevleri](../windows/safeint-functions.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** safeint.h

**Namespace:** Microsoft::Utilities

## <a name="see-also"></a>Ayrıca Bkz.

[SafeInt İşlevleri](../windows/safeint-functions.md)<br/>
[SafeInt Kitaplığı](../windows/safeint-library.md)<br/>
[SafeInt Sınıfı](../windows/safeint-class.md)