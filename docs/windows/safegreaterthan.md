---
title: SafeGreaterThan | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: SafeGreaterThan
dev_langs: C++
helpviewer_keywords: SafeGreaterThan function
ms.assetid: 32cecac9-ba88-43eb-a7a4-30e390456739
caps.latest.revision: "6"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: f1d09de4e09b76d663482ea73b8f0ed56b249bd1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="safegreaterthan"></a>SafeGreaterThan
İki sayı karşılaştırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename T, typename U>  
inline bool SafeGreaterThan (  
   const T t,  
   const U u  
) throw ();  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`t`  
 Karşılaştırma yapılacak ilk sayı. Bu t türünde olmalıdır  
  
 [in]`u`  
 Karşılaştırılacak ikinci sayı. Bu türü u olmalıdır  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`varsa `t` değerinden daha büyük `u`; Aksi halde `false`.  
  
## <a name="remarks"></a>Açıklamalar  
 `SafeGreaterThan`Normal karşılaştırma işlecinin iki farklı tür numarası karşılaştırmanıza olanak sağlayarak genişletir.  
  
 Bu yöntem parçası olan [SafeInt Kitaplığı](../windows/safeint-library.md) ve bir örneğini oluşturmak zorunda kalmadan tek karşılaştırma işlemi için tasarlanmış [SafeInt sınıfı](../windows/safeint-class.md).  
  
> [!NOTE]
>  Bu yöntem yalnızca tek bir matematik işlemi korunmalıdır zaman kullanılmalıdır. Birden çok işlemi varsa, kullanması gereken `SafeInt` tek tek tek başına işlevleri çağırmak yerine sınıfı.  
  
 T ve U şablonu türleri hakkında daha fazla bilgi için bkz: [SafeInt işlevleri](../windows/safeint-functions.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** safeint.h  
  
 **Namespace:** Microsoft::Utilities  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SafeInt işlevleri](../windows/safeint-functions.md)   
 [SafeInt Kitaplığı](../windows/safeint-library.md)   
 [SafeInt sınıfı](../windows/safeint-class.md)   
 [SafeLessThan](../windows/safelessthan.md)   
 [SafeLessThanEquals](../windows/safelessthanequals.md)   
 [SafeGreaterThanEquals](../windows/safegreaterthanequals.md)