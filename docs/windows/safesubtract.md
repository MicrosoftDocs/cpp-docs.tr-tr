---
title: SafeSubtract | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeSubtract
dev_langs:
- C++
helpviewer_keywords:
- SafeSubtract function
ms.assetid: c2712ddc-173f-46a1-b09c-e7ebbd9e68b2
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a82281f1078acd5e3ed0662964a0171ccd72c336
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018380"
---
# <a name="safesubtract"></a>SafeSubtract
İki sayıyı taşmasına karşı koruyan bir şekilde çıkarır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template<typename T, typename U>  
inline bool SafeSubtract (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *t*  
 Çıkarma ilk numarası. Bu tür olmalıdır `T`.  
  
 [in] *u*  
 Den çıkarılacak sayı *t*. Bu tür olmalıdır `U`.  
  
 [out] *sonucu*  
 Parametrenin nereden **SafeSubtract** sonucu depolar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 **doğru** Eğer hiç Hata oluşmazsa; **false** hata oluşması durumunda.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem, parçasıdır [SafeInt Kitaplığı](../windows/safeint-library.md) örneği oluşturulmadan tek çıkarma işlemi için tasarlanmış ve [SafeInt sınıfı](../windows/safeint-class.md).  
  
> [!NOTE]
>  Bu yöntem, yalnızca tek bir matematiksel işlem korunması gereken durumlarda kullanılmalıdır. Birden çok işlem varsa, kullanması gereken `SafeInt` tek tek başına işlevleri çağırmak yerine sınıfı.  
  
 Şablon türleri hakkında daha fazla bilgi için `T` ve `U`, bkz: [SafeInt işlevleri](../windows/safeint-functions.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** safeint.h  
  
 **Namespace:** Microsoft::Utilities  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SafeInt işlevleri](../windows/safeint-functions.md)   
 [SafeInt Kitaplığı](../windows/safeint-library.md)   
 [SafeInt sınıfı](../windows/safeint-class.md)   
 [SafeAdd](../windows/safeadd.md)