---
title: "Önemli hata C1067 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1067
dev_langs: C++
helpviewer_keywords: C1067
ms.assetid: e2c94be6-4573-4571-aac9-73d657fe9f96
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7ef424de5d375f2d198a5f358976d058d556c506
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1067"></a>Önemli hata C1067
Derleyici sınırı: türü bir kayıtta boyutu 64K sınırı aşıldı  
  
 Bir simge 247 karakteri aşan bir düzenlenmiş adı varsa, bu hata oluşabilir.  Çözmek için sembol adını kısaltın.  
  
 Derleyici hata ayıklama bilgileri oluşturduğunda, kaynak kodunda karşılaşılan türlerini tanımlamak için tür kayıtları yayar.  Örneğin, türü kayıtları basit yapılar ve işlevlerin bağımsız değişken listeleri içerir.  Bu tür kayıtların bazıları büyük listeleri olabilir.  
  
 Herhangi bir tür kaydının boyutu 64K sınırı yoktur.  Bu 64 K sınır aşılırsa, bu hata meydana gelir.  
  
 C1067 uzun adları birçok sembolleriyle varsa veya bir sınıf, yapı ve birleşim çok fazla sayıda üye sahipse da oluşabilir.