---
title: SafeMultiply | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeMultiply
dev_langs:
- C++
helpviewer_keywords:
- SafeMultiply function
ms.assetid: 81d988a5-fac7-4930-8c37-c24fa8e2c853
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9c0c78a8c17c47ea91d89b3dc7451d60ed0a567b
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40019098"
---
# <a name="safemultiply"></a>SafeMultiply
Birlikte taşmasına karşı koruyan bir şekilde iki sayıyı çarpar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template<typename T, typename U>  
inline bool SafeMultiply (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *t*  
 Çarpılacak ilk sayı. Bu tür olmalıdır `T`.  
  
 [in] *u*  
 Çarpılacak ikinci sayı. Bu tür olmalıdır `U`.  
  
 [out] *sonucu*  
 Parametrenin nereden **SafeMultiply** sonucu depolar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 **doğru** Eğer hiç Hata oluşmazsa; **false** hata oluşması durumunda.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem, parçasıdır [SafeInt Kitaplığı](../windows/safeint-library.md) örneği oluşturulmadan tek çarpma işlemi için tasarlanmış ve [SafeInt sınıfı](../windows/safeint-class.md).  
  
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
 [SafeDivide](../windows/safedivide.md)