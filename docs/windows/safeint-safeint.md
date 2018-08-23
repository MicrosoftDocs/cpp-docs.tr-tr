---
title: SafeInt::SafeInt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeInt::SafeInt
- SafeInt
- SafeInt.SafeInt
dev_langs:
- C++
helpviewer_keywords:
- SafeInt class, constructor
ms.assetid: 39e6f632-a396-40e6-9ece-cc3d4c5a78ef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2ddb7092b1a5556485848d122e21ac54b6efe182
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42606961"
---
# <a name="safeintsafeint"></a>SafeInt::SafeInt

Oluşturur bir **SafeInt** nesne.

## <a name="syntax"></a>Sözdizimi

```cpp
SafeInt() throw

SafeInt (
   const T& i
) throw ()

SafeInt (
   bool b
) throw ()

template <typename U>
SafeInt (
   const SafeInt <U, E>& u
)

I template <typename U>
SafeInt (
   const U& i
)  
```

### <a name="parameters"></a>Parametreler

[in] *ediyorum*  
Yeni değeri **SafeInt** nesne. Bu oluşturucuya bağlı olarak U, ya da T türünde bir parametresi olmalıdır.

[in] *b*  
Yeni bir Boole değeri **SafeInt** nesne.

[in] *u*  
A **SafeInt** türüne Yeni **SafeInt** nesnesi aynı değere sahip *u*, ancak türü t

U depolanan verilerin türünü **SafeInt**. Bu, bir Boole değeri, karakter veya tamsayı türü olabilir. Bir tamsayı türü ise, yeniden imzalanmış imzalanmamış veya bırakılabilir ve 8 ile 64 bit arasında olmalıdır.

## <a name="remarks"></a>Açıklamalar

Şablon türleri hakkında daha fazla bilgi için `T` ve `E`, bkz: [SafeInt sınıfı](../windows/safeint-class.md).

Oluşturucu giriş parametresi *miyim* veya *u*, Boolean, karakter veya tamsayı türü olmalıdır. Parametresi, başka bir tür ise **SafeInt** sınıf çağrıları [static_assert](../cpp/static-assert.md) geçersiz giriş parametresi belirtmek için.

Şablon türü kullanmak oluşturucular `U` otomatik olarak giriş parametresi tarafından belirtilen türe dönüştürmek `T`. **SafeInt** sınıfı, veri kaybı olmadan verileri dönüştürür. Hata işleyicisine raporları `E` veri türüne dönüştüremezse `T` veri kaybı olmadan.

Oluşturursanız, bir **SafeInt** değeri hemen başlatmak gereken bir Boole parametresi. Yapısı kopyalanamıyor bir **SafeInt** kodu kullanarak `SafeInt<bool> sb;`. Bu, bir derleme hatasına neden olur.

## <a name="requirements"></a>Gereksinimler

**Başlık:** safeint.h

**Namespace:** msl::utilities

## <a name="see-also"></a>Ayrıca Bkz.

[SafeInt Kitaplığı](../windows/safeint-library.md)  
[SafeInt Sınıfı](../windows/safeint-class.md)  
[SafeIntException Sınıfı](../windows/safeintexception-class.md)