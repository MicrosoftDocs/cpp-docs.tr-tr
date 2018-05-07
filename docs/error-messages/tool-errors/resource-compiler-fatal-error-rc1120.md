---
title: Kaynak Derleyicisi önemli hatası RC1120 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC1120
dev_langs:
- C++
helpviewer_keywords:
- RC1120
ms.assetid: 4e462931-e42e-42e3-8bfc-847677194286
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d117f7b106e14cde2def5477fab5ad0fc92a6411
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="resource-compiler-fatal-error-rc1120"></a>Kaynak Derleyicisi Önemli Hatası RC1120
bellek yetersiz bayt sayısı gerekli  
  
 Kaynak Derleyicisi kendi yığın depolar öğeleri için depolama alanı bulamadı. Genellikle bu çok fazla simgeleri sahip sonucudur.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümlere kullanarak düzeltmek için  
  
1.  Windows takas dosyası alanı artırın. Takas dosyası alanını artırma hakkında daha fazla bilgi için sanal bellek Windows Yardım'a bakın.  
  
2.  Gereksiz ortadan özellikle gereksiz dosyaları dahil etme `#define`s ve işlev prototipleri.  
  
3.  Geçerli dosya iki veya daha fazla dosyaya bölün ve ayrı olarak derleyin.  
  
4.  Diğer programları veya önemli miktarda bellek tüketerek sistemde çalışan sürücüleri kaldırın.