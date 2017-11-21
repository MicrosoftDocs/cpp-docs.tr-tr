---
title: SafeAdd | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: SafeAdd
dev_langs: C++
helpviewer_keywords: SafeAdd function
ms.assetid: 3f82b91d-59fe-4ee1-873b-d056182fa8be
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 394a79554acad936a180a8bde0a04b5e6d10069f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="safeadd"></a>SafeAdd
Taşma karşı koruyan bir şekilde iki sayıları toplar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename T, typename U>  
inline bool SafeAdd (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`t`  
 Eklenecek ilk sayı. Bu t türünde olmalıdır  
  
 [in]`u`  
 Eklenecek ikinci sayı. Bu türü u olmalıdır  
  
 [out]`result`  
 Parametre nerede `SafeAdd` sonucu depolar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`herhangi bir hata oluşursa; `false` bir hata oluşursa.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem parçası olan [SafeInt Kitaplığı](../windows/safeint-library.md) ve bir örneğini oluşturmak zorunda kalmadan tek ekleme işlemi için tasarlanmış [SafeInt sınıfı](../windows/safeint-class.md).  
  
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
 [SafeSubtract](../windows/safesubtract.md)