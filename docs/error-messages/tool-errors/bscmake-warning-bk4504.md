---
title: "BSCMAKE uyarısı BK4504 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- BK4504
dev_langs:
- C++
helpviewer_keywords:
- BK4504
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 58a59b3141a8d7051aa7ece1bcb71dd960fabb18
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="bscmake-warning-bk4504"></a>BSCMAKE Uyarısı BK4504
Dosya çok fazla başvuru içeriyor; Bu kaynaktan gelen ek başvurular yoksayılıyor  
  
 .Cpp dosyası birden fazla 64.000 simge başvurularını içerir. BSCMAKE bir dosyada 64.000 başvuruları karşılaştığında, tüm ek başvurular yok sayar.  
  
 Sorunu düzeltmek için dosyayı ikiye bölün ya da daha fazla dosya, her biri daha azını 64.000 sahip sembol başvuruları veya kullanmak `#pragma component(browser)` belirli başvurular için oluşturulan sınırı sembolleri için önişlemci yönergesi. Daha fazla bilgi için bkz: [bileşen](../../preprocessor/component.md).