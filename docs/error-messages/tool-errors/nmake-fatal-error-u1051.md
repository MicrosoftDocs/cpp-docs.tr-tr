---
title: "NMAKE önemli hatası U1051 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: U1051
dev_langs: C++
helpviewer_keywords: U1051
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 93c109bf723b3c4cf08e998a715fe8f6f33be466
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1051"></a>NMAKE Önemli Hatası U1051
Bellek yetersiz  
  
 NMAKE derleme görevleri dosyası çok büyük veya karmaşık olduğundan sanal bellek dahil olmak üzere, bellek yetersiz kaldı.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümlere kullanarak düzeltmek için  
  
1.  Diskte biraz yer açın.  
  
2.  Windows NT disk belleği dosyası ya da Windows takas dosyası boyutunu artırın.  
  
3.  Yalnızca derleme görevleri dosyası parçası kullanılır, derleme görevleri dosyası ayrı dosyalara bölün veya kullanmak **! Eğer** ön işleme NMAKE işlemelidir miktarını sınırlamak için yönergeleri. **! Eğer** yönergelerini **! Eğer**, `!IFDEF`, **! IFNDEF**, **! ELSE IF**, **! ELSE** `IFDEF`, ve **! ELSE** `IFNDEF`.