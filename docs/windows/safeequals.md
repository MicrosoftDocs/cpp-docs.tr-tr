---
title: SafeEquals | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeEquals
dev_langs:
- C++
helpviewer_keywords:
- SafeEquals function
ms.assetid: 6019627d-f170-413b-9abd-2b5b34396a72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 81f30386946c7fd187f1044804b9f1737a94c58f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718663"
---
# <a name="safeequals"></a>SafeEquals

Eşit olup olmadığını belirlemek için iki sayının karşılaştırır.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T, typename U>
inline bool SafeEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Parametreler

*T*<br/>
[in] Karşılaştırılacak birinci sayı. Bu t türünde olmalıdır

*u*<br/>
[in] Karşılaştırılacak ikinci sayı. Bu u türü olmalıdır

## <a name="return-value"></a>Dönüş Değeri

**doğru** varsa *t* ve *u* Aksi takdirde eşit **false**.

## <a name="remarks"></a>Açıklamalar

Yöntem geliştirir `==` çünkü **SafeEquals** iki farklı tür sayı karşılaştırmanızı sağlar.

Bu yöntem, parçasıdır [SafeInt Kitaplığı](../windows/safeint-library.md) örneği oluşturmaya gerek kalmadan tek bir karşılaştırma işlemi için tasarlanmış ve [SafeInt sınıfı](../windows/safeint-class.md).

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
[SafeNotEquals](../windows/safenotequals.md)