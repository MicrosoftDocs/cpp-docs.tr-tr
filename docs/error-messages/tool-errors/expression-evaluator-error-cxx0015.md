---
title: İfade değerlendirici hatası CXX0015 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0015
dev_langs:
- C++
helpviewer_keywords:
- CXX0015
- CAN0015
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 945dbda4759fa2989acb0411d1a3216a5e9a036c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33297615"
---
# <a name="expression-evaluator-error-cxx0015"></a>İfade Değerlendirici Hatası CXX0015
ifade çok karmaşık (yığın taşması)  
  
 Girdiğiniz ifade çok karmaşık veya iç içe geçmiş çok derine C ifade değerlendiricisi kullanılabilir depolama alanı miktarı.  
  
 Taşma genellikle çok fazla bekleyen hesaplamalar nedeniyle oluşur.  
  
 Hesaplanacak ifade diğer bölümleri için beklemek zorunda yerine karşılaştı gibi her bileşen ifadenin değerlendirilmesi şekilde ifadeyi yeniden düzenleyin.  
  
 Deyim birden fazla komuttan bölün.  
  
 Bu hata için CAN0015 aynıdır.