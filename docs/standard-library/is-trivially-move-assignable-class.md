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
ms.workload: cplusplus
ms.openlocfilehash: 267314b73bfdf2d408038836bc3c4eac8e3317ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [<type_traits>](../standard-library/type-traits.md)



