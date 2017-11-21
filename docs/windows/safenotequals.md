---
title: SafeNotEquals | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: SafeNotEquals
dev_langs: C++
helpviewer_keywords: SafeNotEquals function
ms.assetid: 032e45a8-4159-4b55-b7cc-ecd27f4e4788
caps.latest.revision: "6"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: dc77d2a8d4558fad3f1339edbfd7d9d8e1b102ea
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="safenotequals"></a>SafeNotEquals
İki sayıyı eşit olup olmadığını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename T, typename U>  
inline bool SafeNotEquals (  
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
 `true`varsa `t` ve `u` olmayan tersi `false`.  
  
## <a name="remarks"></a>Açıklamalar  
 Yöntem geliştirir `!=` çünkü `SafeNotEquals` numaraları iki farklı türde karşılaştırmanıza olanak sağlar.  
  
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
 [SafeEquals](../windows/safeequals.md)