---
title: Önemli hata C1002 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1002
dev_langs:
- C++
helpviewer_keywords:
- C1002
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c63a8d399b3e8c781694d89825e7898fd1db4639
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33225057"
---
# <a name="fatal-error-c1002"></a>Önemli hata C1002
yığın alanı 2 geçişindeki derleyici dışındadır  
  
 Derleyici, ikinci geçişi sırasında çok fazla sayıda simgeleri veya karmaşık ifadeler programla büyük olasılıkla dinamik bellek alana verdi.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümlere kullanarak düzeltmek için  
  
1.  Kaynak dosya birkaç küçük dosyalara bölün.  
  
2.  İfadeler daha küçük alt ifadelere bölün.  
  
3.  Diğer programları veya bellek tüketmesine sürücüleri kaldırın.