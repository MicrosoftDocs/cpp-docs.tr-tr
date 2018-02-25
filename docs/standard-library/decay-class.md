---
title: "decay sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::decay
dev_langs:
- C++
helpviewer_keywords:
- decay class
ms.assetid: 96baa2fd-c8e0-49af-be91-ba375ba7f9dc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d43ee8ff7971af3026066b3483de4808ec2dc114
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="decay-class"></a>decay Sınıfı
Değere göre geçti olarak türü üretir. Yaptığında türü başvuru olmayan, sabit olmayan geçici olmayan ya da bir işaretçi bir işlev veya bir dizi türü türe yapar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>
struct decay;

template <class T>  
using decay_t = typename decay<T>::type;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Değiştirilecek tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Decay şablon türü değer bağımsız değişken olarak geçirilen gibi sonuç türü oluşturmak için kullanın. Şablon sınıfının üye typedef `type` bulunan aşağıdaki aşamaları tanımlanan değiştirilmiş bir türü bulunur:  
  
-   Türü `U` olarak tanımlanan `remove_reference<T>::type`.  
  
-   Varsa `is_array<U>::value` doğrudur değiştirilmiş türü `type` olan `remove_extent<U>::type *`.  
  
-   Aksi halde, eğer `is_function<U>::value` doğrudur değiştirilmiş türü `type` olan `add_pointer<U>::type`.  
  
-   Aksi takdirde, değiştirilmiş türü `type` olan `remove_cv<U>::type`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [<type_traits>](../standard-library/type-traits.md)



