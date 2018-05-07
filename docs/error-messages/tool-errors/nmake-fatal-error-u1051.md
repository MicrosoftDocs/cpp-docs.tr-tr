---
title: NMAKE önemli hatası U1051 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1051
dev_langs:
- C++
helpviewer_keywords:
- U1051
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 570c7e5d8e6e8250a67e4f032ac26b04388cfd00
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-fatal-error-u1051"></a>NMAKE Önemli Hatası U1051
Bellek yetersiz  
  
 NMAKE derleme görevleri dosyası çok büyük veya karmaşık olduğundan sanal bellek dahil olmak üzere, bellek yetersiz kaldı.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümlere kullanarak düzeltmek için  
  
1.  Diskte biraz yer açın.  
  
2.  Windows NT disk belleği dosyası ya da Windows takas dosyası boyutunu artırın.  
  
3.  Yalnızca derleme görevleri dosyası parçası kullanılır, derleme görevleri dosyası ayrı dosyalara bölün veya kullanmak **! Eğer** ön işleme NMAKE işlemelidir miktarını sınırlamak için yönergeleri. **! Eğer** yönergelerini **! Eğer**, `!IFDEF`, **! IFNDEF**, **! ELSE IF**, **! ELSE** `IFDEF`, ve **! ELSE** `IFNDEF`.