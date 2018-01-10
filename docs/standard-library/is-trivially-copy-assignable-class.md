---
title: "is_trivially_copy_assignable sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_trivially_copy_assignable
dev_langs: C++
helpviewer_keywords: is_trivially_copy_assignable
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 477b0c513817860aac40a01d921cec50293b54ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="istriviallycopyassignable-class"></a>is_trivially_copy_assignable sınıfı
Türü bir önemsiz copy atama işleci olup olmadığını sınar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class Ty>
struct is_trivially_copy_assignable;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sorgulanacak tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Türü koşulu örneği doğru tutan türü `T` false tuttuğu bir önemsiz copy atama işleci, aksi takdirde sahip bir sınıftır.  
  
 Bir sınıf için bir atama Oluşturucusu `T` , örtük olarak sağlanır, sınıf deyimle `T` sınıfı hiçbir sanal işleve sahip `T` hiçbir sanal temellerine sahip, sınıf türü tüm statik olmayan veri üyeleri sınıflarını Önemsiz sahip atama işleçleri ve sınıf türü dizisi tüm statik olmayan veri üyeleri sınıflarını Önemsiz atama işleçleri sahiptir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [<type_traits>](../standard-library/type-traits.md)



