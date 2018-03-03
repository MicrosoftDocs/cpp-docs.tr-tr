---
title: "Kaynak Derleyicisi önemli hatası RC1120 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC1120
dev_langs:
- C++
helpviewer_keywords:
- RC1120
ms.assetid: 4e462931-e42e-42e3-8bfc-847677194286
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 28a35cc2f932cdf655324d05c10bdb875aa895a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-fatal-error-rc1120"></a>Kaynak Derleyicisi Önemli Hatası RC1120
bellek yetersiz bayt sayısı gerekli  
  
 Kaynak Derleyicisi kendi yığın depolar öğeleri için depolama alanı bulamadı. Genellikle bu çok fazla simgeleri sahip sonucudur.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümlere kullanarak düzeltmek için  
  
1.  Windows takas dosyası alanı artırın. Takas dosyası alanını artırma hakkında daha fazla bilgi için sanal bellek Windows Yardım'a bakın.  
  
2.  Gereksiz ortadan özellikle gereksiz dosyaları dahil etme `#define`s ve işlev prototipleri.  
  
3.  Geçerli dosya iki veya daha fazla dosyaya bölün ve ayrı olarak derleyin.  
  
4.  Diğer programları veya önemli miktarda bellek tüketerek sistemde çalışan sürücüleri kaldırın.