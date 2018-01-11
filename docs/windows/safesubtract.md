---
title: SafeSubtract | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: SafeSubtract
dev_langs: C++
helpviewer_keywords: SafeSubtract function
ms.assetid: c2712ddc-173f-46a1-b09c-e7ebbd9e68b2
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5b94d84e6a348b68258fc1b57c2e0ad9ad30e36d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="safesubtract"></a>SafeSubtract
Taşma karşı koruyan bir şekilde iki sayının çıkarır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename T, typename U>  
inline bool SafeSubtract (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`t`  
 Çıkarma ilk sayısı. Bu t türünde olmalıdır  
  
 [in]`u`  
 Den çıkartılacak sayı `t`. Bu türü u olmalıdır  
  
 [out]`result`  
 Parametre nerede `SafeSubtract` sonucu depolar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`herhangi bir hata oluşursa; `false` bir hata oluşursa.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem parçası olan [SafeInt Kitaplığı](../windows/safeint-library.md) ve bir örneğini oluşturmak zorunda kalmadan tek çıkarma işlemi için tasarlanmış [SafeInt sınıfı](../windows/safeint-class.md).  
  
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
 [SafeAdd](../windows/safeadd.md)