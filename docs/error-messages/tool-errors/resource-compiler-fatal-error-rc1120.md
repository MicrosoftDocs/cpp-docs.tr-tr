---
title: "Kaynak Derleyicisi önemli hatası RC1120 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC1120
dev_langs: C++
helpviewer_keywords: RC1120
ms.assetid: 4e462931-e42e-42e3-8bfc-847677194286
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9cc1006dad4b0427a4254f4798b206d975e89e03
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="resource-compiler-fatal-error-rc1120"></a>Kaynak Derleyicisi Önemli Hatası RC1120
bellek yetersiz bayt sayısı gerekli  
  
 Kaynak Derleyicisi kendi yığın depolar öğeleri için depolama alanı bulamadı. Genellikle bu çok fazla simgeleri sahip sonucudur.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümlere kullanarak düzeltmek için  
  
1.  Windows takas dosyası alanı artırın. Takas dosyası alanını artırma hakkında daha fazla bilgi için sanal bellek Windows Yardım'a bakın.  
  
2.  Gereksiz ortadan özellikle gereksiz dosyaları dahil etme `#define`s ve işlev prototipleri.  
  
3.  Geçerli dosya iki veya daha fazla dosyaya bölün ve ayrı olarak derleyin.  
  
4.  Diğer programları veya önemli miktarda bellek tüketerek sistemde çalışan sürücüleri kaldırın.