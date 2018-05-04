---
title: Makrolardaki özel karakterler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- special characters, in NMAKE macros
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c271d2f39a4d81776c06a107616170192e82d40d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
 [NMAKE Makrosu Tanımlama](../build/defining-an-nmake-macro.md)