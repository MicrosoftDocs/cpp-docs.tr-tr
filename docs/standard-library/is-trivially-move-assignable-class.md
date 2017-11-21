---
title: "is_trivially_move_assignable sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_trivially_move_assignable
dev_langs: C++
helpviewer_keywords: is_trivially_move_assignable
ms.assetid: 374f7322-0706-4bc1-a1a5-4191d0315e28
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 078d138126a432e3be0c2709b4ae351f2383ae44
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="istriviallymoveassignable-class"></a>is_trivially_move_assignable sınıfı
Önemsiz taşıma atama işleci türüne sahip olup olmadığını sınar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class Ty>
struct is_trivially_move_assignable;
```  
  
#### <a name="parameters"></a>Parametreler  
 `Ty`  
 Sorgulanacak tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Türü koşulu örneği doğru tutan türü `Ty` false tuttuğu bir önemsiz taşıma atama işleci, aksi takdirde sahip bir sınıftır.  
  
 Bir sınıf için bir taşıma atama işleci `Ty` deyimle varsa:  
  
 örtük olarak sağlanır  
  
 sınıf `Ty` hiçbir sanal işleve sahip  
  
 sınıf `Ty` hiçbir sanal temellerine sahip  
  
 sınıf türü tüm statik olmayan veri üyeleri sınıflarını Önemsiz taşıma atama işleçleri sahip  
  
 sınıf türü dizisi tüm statik olmayan veri üyeleri sınıflarını Önemsiz taşıma atama işleçleri sahip  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< type_traits >](../standard-library/type-traits.md)



