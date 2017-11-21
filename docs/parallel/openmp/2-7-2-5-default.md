---
title: "2.7.2.5 varsayılan | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c856df07-705c-4ad3-9105-a268dd33e939
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 26dff1f0e8b3b88b4891617a2eef2bb2d82240eb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="2725-default"></a>2.7.2.5 default
**Varsayılan** yan tümcesi değişkenleri veri paylaşımı özniteliklerini etkileyen kullanıcıya izin verir. Söz dizimi **varsayılan** yan tümcesi aşağıdaki gibidir:  
  
```  
default(shared | none)  
```  
  
 Belirtme **default(shared)** açıkça her görünen bir değişken listesi için eşdeğer bir gruba bir **paylaşılan** yan tümcesi olduğu sürece **threadprivate** veya **cons**`t`-tam. Açık olmadığında **varsayılan** yan tümcesi, varsayılan davranıştır aynı IF **default(shared)** belirtildi.  
  
 Belirtme **default(none)** aşağıdakilerden en az birini paralel yapı sözcük kapsamını bir değişkende yapılan her gönderme için doğru olmasını gerektirir:  
  
-   Değişken bir veri paylaşım öznitelik yan tümcesi başvuru içeren bir yapı içinde açıkça listelenir.  
  
-   Değişkeni paralel yapı içinde bildirildi.  
  
-   Bu değişken **threadprivate**.  
  
-   Değişkeni sahip bir **const**-tam türü.  
  
-   For döngüsü denetim değişkeniyle değişkenidir bir **için** hemen izleyen döngü bir **için** veya **için paralel** yönergesi ve değişken başvuru döngünün içinde görünür .  
  
 Bir değişken belirtme bir **firstprivate**, **lastprivate**, veya **azaltma** kapalı yönergesi yan tümcesi kapsayan değişkenine dolaylı bir başvuru neden olur bağlamı. Bu tür örtük başvuruları yukarıda listelenen gereksinimleri de tabidir.  
  
 Yalnızca tek bir **varsayılan** yan tümcesi belirtilebilir bir **paralel** yönergesi.  
  
 Bir değişkenin varsayılan veri paylaşım öznitelik kullanarak geçersiz kılınmış **özel**, **firstprivate**, **lastprivate**, **azaltma**, ve **paylaşılan** yan tümceleri, aşağıdaki örnekte gösterildiği gibi:  
  
```  
#pragma  omp  parallel  for  default(shared)  firstprivate(i)\  
   private(x)  private(r)  lastprivate(i)  
```