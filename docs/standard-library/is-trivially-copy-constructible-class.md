---
title: "is_trivially_copy_constructible sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_copy_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 438a5e2aa262eefaa7d2c6cfcfe5786051646b87
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="istriviallycopyconstructible-class"></a>is_trivially_copy_constructible Sınıfı
Önemsiz kopya Oluşturucu türündeyse testleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>
struct is_trivially_copy_constructible;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sorgulanacak tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Türü koşulu örneği doğru tutan türü `T` false tuttuğu Önemsiz kopya Oluşturucu, aksi takdirde sahip bir sınıftır.  
  
 Bir sınıf için bir kopya Oluşturucu `T` bu örtülü olarak bildirilen, sınıf deyimle `T` hiçbir sanal işlevleri veya sanal tabanları, sınıfın tüm doğrudan temellerine sahip `T` Önemsiz kopya oluşturucuları, tüm statik olmayan sınıflarını sahip veri üyeleri sınıf türü Önemsiz kopya oluşturucuları, ve önemsiz kopya oluşturucuları dizisi türünde sınıfı tüm statik olmayan veri üyeleri sınıflarını sahiptir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [<type_traits>](../standard-library/type-traits.md)



