---
title: SafeNotEquals | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeNotEquals
dev_langs:
- C++
helpviewer_keywords:
- SafeNotEquals function
ms.assetid: 032e45a8-4159-4b55-b7cc-ecd27f4e4788
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 19427d24d61581d207101605a8456e8067ade929
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713849"
---
# <a name="safenotequals"></a>SafeNotEquals

İki sayıyı eşit olup olmadığını belirler.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T, typename U>
inline bool SafeNotEquals (
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

**doğru** varsa *t* ve *u* olmayan Aksi takdirde eşit **false**.

## <a name="remarks"></a>Açıklamalar

Yöntem geliştirir `!=` çünkü **SafeNotEquals** iki farklı tür sayı karşılaştırmanızı sağlar.

Bu yöntem, parçasıdır [SafeInt Kitaplığı](../windows/safeint-library.md) örneği oluşturmaya gerek kalmadan tek bir karşılaştırma işlemi için tasarlanmış ve [SafeInt sınıfı](../windows/safeint-class.md).

> [!NOTE]
> Bu yöntem, yalnızca tek bir matematiksel işlem korunması gereken durumlarda kullanılmalıdır. Birden çok işlem varsa, kullanması gereken `SafeInt` tek tek başına işlevleri çağırmak yerine sınıfı.

Şablon türleri hakkında daha fazla bilgi için `T` ve `U`, bkz: [SafeInt işlevleri](../windows/safeint-functions.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** safeint.h

**Namespace:** Microsoft::Utilities

## <a name="see-also"></a>Ayrıca Bkz.

[SafeInt İşlevleri](../windows/safeint-functions.md)  
[SafeInt Kitaplığı](../windows/safeint-library.md)  
[SafeInt Sınıfı](../windows/safeint-class.md)  
[SafeEquals](../windows/safeequals.md)