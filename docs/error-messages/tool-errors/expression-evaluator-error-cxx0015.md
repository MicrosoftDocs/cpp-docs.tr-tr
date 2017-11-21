---
title: "İfade değerlendirici hatası CXX0015 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0015
dev_langs: C++
helpviewer_keywords:
- CXX0015
- CAN0015
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d6b04fd2b13b2acd9021dcd8e751a0b4cbefd166
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="expression-evaluator-error-cxx0015"></a>İfade Değerlendirici Hatası CXX0015
ifade çok karmaşık (yığın taşması)  
  
 Girdiğiniz ifade çok karmaşık veya iç içe geçmiş çok derine C ifade değerlendiricisi kullanılabilir depolama alanı miktarı.  
  
 Taşma genellikle çok fazla bekleyen hesaplamalar nedeniyle oluşur.  
  
 Hesaplanacak ifade diğer bölümleri için beklemek zorunda yerine karşılaştı gibi her bileşen ifadenin değerlendirilmesi şekilde ifadeyi yeniden düzenleyin.  
  
 Deyim birden fazla komuttan bölün.  
  
 Bu hata için CAN0015 aynıdır.