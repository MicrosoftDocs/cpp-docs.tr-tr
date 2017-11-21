---
title: "is_trivially_copy_constructible sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_trivially_copy_constructible
dev_langs: C++
helpviewer_keywords: is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 465d5a1756a416eac2c01c5191b4f63f986ffcba
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [< type_traits >](../standard-library/type-traits.md)



