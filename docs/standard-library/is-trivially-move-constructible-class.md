---
title: "is_trivially_move_constructible sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_trivially_move_constructible
dev_langs: C++
helpviewer_keywords: is_trivially_move_constructible
ms.assetid: 740bdec7-65e5-47b3-b94f-a2479ceac3ec
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7b918809c0fabf7e0d65770dd12149d2f258189e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="istriviallymoveconstructible-class"></a>is_trivially_move_constructible sınıfı
Önemsiz türündeyse testleri Oluşturucusu taşıyın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class Ty>
struct is_trivially_move_constructible;
```  
  
#### <a name="parameters"></a>Parametreler  
 `Ty`  
 Sorgulanacak tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Türü koşulu örneği doğru tutan türü `Ty` false tuttuğu bir önemsiz taşıma oluşturucusu, aksi durumda olan bir sınıftır.  
  
 Bir sınıf için bir taşıma oluşturucusuna `Ty` deyimle varsa:  
  
 örtülü olarak bildirilen  
  
 parametre türleri örtük bir bildirimi gereksinimlerine eşdeğer  
  
 sınıf `Ty` hiçbir sanal işleve sahip  
  
 sınıf `Ty` hiçbir sanal temellerine sahip  
  
 sınıfta hiç geçici olmayan statik veri üyeleri yok  
  
 tüm doğrudan taban sınıfının `Ty` Önemsiz taşıma oluşturucuları sahip  
  
 sınıf türü tüm statik olmayan veri üyeleri sınıflarını Önemsiz taşıma oluşturucuları sahip  
  
 sınıf türü dizisi tüm statik olmayan veri üyeleri sınıflarını Önemsiz taşıma oluşturucuları sahip  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [<type_traits>](../standard-library/type-traits.md)



