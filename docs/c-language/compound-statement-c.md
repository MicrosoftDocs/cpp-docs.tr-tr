---
title: "Statement (C) bileşik | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- compound statements
- statements, compound
ms.assetid: 32d1bf86-cbbc-42a9-ba3a-1be1c6c7754c
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 369ff1b3097e79fa0da50a82647bbf6ac62464e2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compound-statement-c"></a>Bileşik Deyim (C)
Bileşik deyim (Ayrıca çağrılan bir "bloğu") genellikle başka bir ifade gövdesi olarak gibi görünen **varsa** deyimi. [Bildirimler ve türler](../c-language/declarations-and-types.md) bileşik deyim head görünebilir bildirimleri anlamını ve form açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
 *Bileşik deyim*:  
 **{***bildirimi listesi* kabul*deyimi listesi*kabul**}**   
  
 *bildirim listesi*:  
 *bildirimi*  
  
 *bildirim listesi bildirimi*  
  
 *Ekstre listesini*:  
 s*kstre*  
  
 *deyimi listesi deyimi*  
  
 Bildirimleri varsa, bunlar herhangi deyimleri önce gelmelidir. Bileşik deyim başında bildirilen her tanımlayıcı kapsamını kendi bildirimi noktasından blok sonuna genişletir. Bir iç bloğunda tanımlayıcısının bildirimi olmadığı sürece bloğu görünür olur.  
  
 Bileşik deyim tanımlayıcılarının varsayılan **otomatik** aksi açıkça ile bildirilir sürece **kaydetmek**, **statik**, veya `extern`, İşlevler dışında yalnızca olabilen `extern`. Devre dışı bırakabilirsiniz `extern` işlev bildirimleri ve işlevi belirleyici çıkarılsın `extern`.  
  
 Depolama tahsis ve başlatma bir değişken varsa izin verilmez veya işlev depolama sınıfı ile bileşik deyim içinde bildirilen `extern`. Dış bir değişkene bildirimi göndermede veya başka bir yerde işlevi tanımlanmış.  
  
 Değişkenleri olan bir bloğun içinde bildirilen **otomatik** veya **kaydetmek** anahtar sözcük bırakılan ve gerekirse, başlatılan her zaman bileşik deyim girilir. Bileşik deyim çıkıldı sonra bu değişkenleri tanımlı değil. Bir değişken bir blok içinde bildirilen sahipse **statik** özniteliği, değişkeni, program yürütme başlar ve değerini program boyunca tutar başlatılır. Bkz: [depolama sınıfları](../c-language/c-storage-classes.md) hakkında bilgi için **statik**.  
  
 Bu örnekte bileşik deyim gösterilmektedir:  
  
```  
if ( i > 0 )   
{  
    line[i] = x;  
    x++;  
    i--;  
}  
```  
  
 Bu örnekte, `i` 0'dan büyük bileşik deyim içindeki tüm ifadeler sırayla yürütülür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Deyimleri](../c-language/statements-c.md)