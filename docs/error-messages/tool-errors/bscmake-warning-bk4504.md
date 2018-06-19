---
title: BSCMAKE uyarısı BK4504 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK4504
dev_langs:
- C++
helpviewer_keywords:
- BK4504
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a17aa8b4e2a98d3bda5d21ea84962791b8051dc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33295190"
---
# <a name="bscmake-warning-bk4504"></a>BSCMAKE Uyarısı BK4504
Dosya çok fazla başvuru içeriyor; Bu kaynaktan gelen ek başvurular yoksayılıyor  
  
 .Cpp dosyası birden fazla 64.000 simge başvurularını içerir. BSCMAKE bir dosyada 64.000 başvuruları karşılaştığında, tüm ek başvurular yok sayar.  
  
 Sorunu düzeltmek için dosyayı ikiye bölün ya da daha fazla dosya, her biri daha azını 64.000 sahip sembol başvuruları veya kullanmak `#pragma component(browser)` belirli başvurular için oluşturulan sınırı sembolleri için önişlemci yönergesi. Daha fazla bilgi için bkz: [bileşen](../../preprocessor/component.md).