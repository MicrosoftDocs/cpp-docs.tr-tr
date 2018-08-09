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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 769c09d39d8640826607d954ae6e6f4672e23647
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014581"
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
 [in] *t*  
 Karşılaştırılacak birinci sayı. Bu tür olmalıdır `T`.  
  
 [in] *u*  
 Karşılaştırılacak ikinci sayı. Bu tür olmalıdır `U`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 **doğru** varsa *t* ve *u* olmayan Aksi takdirde eşit **false**.  
  
## <a name="remarks"></a>Açıklamalar  
 Yöntem geliştirir `!=` çünkü **SafeNotEquals** iki farklı tür sayı karşılaştırmanızı sağlar.  
  
 Bu yöntem, parçasıdır [SafeInt Kitaplığı](../windows/safeint-library.md) örneği oluşturmaya gerek kalmadan tek bir karşılaştırma işlemi için tasarlanmış ve [SafeInt sınıfı](../windows/safeint-class.md).  
  
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
 [SafeEquals](../windows/safeequals.md)