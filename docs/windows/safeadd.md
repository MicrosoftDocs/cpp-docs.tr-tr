---
title: SafeAdd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeAdd
dev_langs:
- C++
helpviewer_keywords:
- SafeAdd function
ms.assetid: 3f82b91d-59fe-4ee1-873b-d056182fa8be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ada0997a03cefbec4bcc4faa26ad4eaf8c176ff2
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704893"
---
# <a name="safeadd"></a>SafeAdd

İki sayıyı taşmasına karşı koruyan bir şekilde ekler.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T, typename U>
inline bool SafeAdd (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Parametreler

*T*<br/>
[in] Eklenecek ilk sayı. Bu t türünde olmalıdır

*u*<br/>
[in] Eklenecek ikinci sayı. Bu u türü olmalıdır

*Sonuç*<br/>
[out] Parametrenin nereden **SafeAdd** sonucu depolar.

## <a name="return-value"></a>Dönüş Değeri

**doğru** Eğer hiç Hata oluşmazsa; **false** hata oluşması durumunda.

## <a name="remarks"></a>Açıklamalar

Bu yöntem, parçasıdır [SafeInt Kitaplığı](../windows/safeint-library.md) örneğini oluşturmadan bir tek bir toplama işlemi için tasarlanmış ve [SafeInt sınıfı](../windows/safeint-class.md).

> [!NOTE]
> Bu yöntem, yalnızca tek bir matematiksel işlem korunması gereken durumlarda kullanılmalıdır. Birden çok işlem varsa, kullanması gereken `SafeInt` tek tek başına işlevleri çağırmak yerine sınıfı.

T ve U şablon türleri hakkında daha fazla bilgi için bkz. [SafeInt işlevleri](../windows/safeint-functions.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** safeint.h

**Namespace:** Microsoft::Utilities

## <a name="see-also"></a>Ayrıca Bkz.

[SafeInt İşlevleri](../windows/safeint-functions.md)  
[SafeInt Kitaplığı](../windows/safeint-library.md)  
[SafeInt Sınıfı](../windows/safeint-class.md)  
[SafeSubtract](../windows/safesubtract.md)