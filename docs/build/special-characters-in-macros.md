---
title: "Makrolardaki özel karakterler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: special characters, in NMAKE macros
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 648122a9c8f3cf97d08128e6e12090ebc12631d9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="special-characters-in-macros"></a>Makrolardaki Özel Karakterler
Bir sayı (#) oturum sonra bir tanımı bir açıklama belirtir. Değişmez değer bir sayı işareti makro belirtmek için de bir şapka (^) kullanın ^ #.  
  
 Dolar işareti ($) makrosu çağırma belirtir. Belirtmek için değişmez değer $ $$ kullanın.  
  
 Yeni bir satır tanımına genişletmek için eğik çizgiyle bitmelidir (\\). Makro çağrıldığında, ters eğik çizgi artı yeni satır karakteri boşluk ile değiştirilir. Değişmez değer ters eğik çizgi satırın sonundaki belirtmek için bir şapka (^) koyun veya yorum tanımlayıcısı ile izleyin (#).  
  
 Değişmez değer yeni satır karakteri belirtmek için de bir şapka (^) içeren satırı Bitir:  
  
```  
CMDS = cls^  
dir  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [NMAKE makrosu tanımlama](../build/defining-an-nmake-macro.md)