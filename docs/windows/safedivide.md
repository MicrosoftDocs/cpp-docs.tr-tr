---
title: SafeDivide | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeDivide
dev_langs:
- C++
helpviewer_keywords:
- SafeDivide function
ms.assetid: b5b27484-ad6e-46b1-ba9f-1c7120dd103b
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0264fbd8df7f1dec5d20b40a67299cb4502b72aa
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="safedivide"></a>SafeDivide
Sıfıra bölme karşı koruyan bir şekilde iki sayıyı böler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename T, typename U>  
inline bool SafeDivide (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in] `t`  
 Bölen. Bu t türünde olmalıdır  
  
 [in] `u`  
 Kar payı. Bu türü u olmalıdır  
  
 [out] `result`  
 Parametre nerede `SafeDivide` sonucu depolar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true` herhangi bir hata oluşursa; `false` bir hata oluşursa.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem parçası olan [SafeInt Kitaplığı](../windows/safeint-library.md) ve bir örneğini oluşturmak zorunda kalmadan tek bölme işlemi için tasarlanmış [SafeInt sınıfı](../windows/safeint-class.md).  
  
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
 [SafeModulus](../windows/safemodulus.md)   
 [SafeMultiply](../windows/safemultiply.md)