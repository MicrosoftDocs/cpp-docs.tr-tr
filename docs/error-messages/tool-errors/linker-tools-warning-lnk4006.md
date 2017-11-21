---
title: "Bağlayıcı araçları uyarısı LNK4006 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4006
dev_langs: C++
helpviewer_keywords: LNK4006
ms.assetid: 3a637d17-1676-4ea6-bd8b-290137d28d3b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c39482dbf53e5a919e8af1927697ef06ba7972b3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-warning-lnk4006"></a>Bağlayıcı Araçları Uyarısı LNK4006
nesnesinde zaten tanımlanmış simge; göz ardı ikinci tanımı  
  
 Verilen `symbol`, düzenlenmiş biçiminde, birden çok kez tanımlanmış. Bu uyarı karşılaşıldığında, `symbol` iki kez eklenir ancak yalnızca kendi ilk form kullanılır.  
  
 İki alma kitaplıklar birinde birleştirmeyi çalışırsanız, bu uyarı alabilirsiniz.  
  
 C çalışma zamanı kitaplığı yeniden bu iletiyi yoksayabilirsiniz.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümlere kullanarak düzeltmek için  
  
1.  Verilen `symbol` ile derleme tarafından oluşturulan paketlenmiş bir işlev olabilir [/Gy](../../build/reference/gy-enable-function-level-linking.md). Bu simgenin birden fazla dosyada eklendi ancak derlemeleri arasında değiştirildi. Dahil tüm dosyaları yeniden derleyin `symbol`.  
  
2.  Verilen `symbol` farklı iki üye nesnelerde farklı kitaplıklarında tanımlanmış olabilir.  
  
3.  Mutlak iki kez, her tanımında farklı bir değerle tanımlanmış olabilir.  
  
4.  Hata iletisi kitaplıkları, birleştirilirken aldıysanız `symbol` eklenmesini Kitaplığı'nda zaten mevcut.