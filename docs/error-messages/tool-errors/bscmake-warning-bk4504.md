---
title: "BSCMAKE uyarısı BK4504 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: BK4504
dev_langs: C++
helpviewer_keywords: BK4504
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f7f6d854fbd74d9ca05ba6797bbd57db52b7a70e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="bscmake-warning-bk4504"></a>BSCMAKE Uyarısı BK4504
Dosya çok fazla başvuru içeriyor; Bu kaynaktan gelen ek başvurular yoksayılıyor  
  
 .Cpp dosyası birden fazla 64.000 simge başvurularını içerir. BSCMAKE bir dosyada 64.000 başvuruları karşılaştığında, tüm ek başvurular yok sayar.  
  
 Sorunu düzeltmek için dosyayı ikiye bölün ya da daha fazla dosya, her biri daha azını 64.000 sahip sembol başvuruları veya kullanmak `#pragma component(browser)` belirli başvurular için oluşturulan sınırı sembolleri için önişlemci yönergesi. Daha fazla bilgi için bkz: [bileşen](../../preprocessor/component.md).