---
title: "Kural tanımlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c0d6ca616e3685db36d6d24b339a860eab4c6150
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="defining-a-rule"></a>Kural Tanımlama
*Fromext* bağımlı bir dosyanın uzantısını temsil eder ve *toext* bir hedef dosya uzantısını temsil eder.  
  
```  
.fromext.toext:  
   commands  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Uzantılar büyük küçük harfe duyarlı değildir. Makrolar temsil etmek için çağrılacak *fromext* ve *toext*; makrolar ön işleme sırasında genişletilir. Önceki nokta (.) *fromext* satırın başındaki görünmesi gerekir. İki nokta (:) sıfır veya daha fazla boşluk ya da sekme tarafından gelmelidir. Yalnızca boşluk veya sekmeler, komutu belirtmek için noktalı virgül (;), bir açıklama belirtmek için bir numara işareti (#) veya yeni satır karakteri ile izlenebilir. Diğer bir boşluk izin verilir. Komutları açıklama blokları olduğu gibi belirtilir.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
 [Yolları kurallarda Ara](../build/search-paths-in-rules.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıkarım Kuralları](../build/inference-rules.md)