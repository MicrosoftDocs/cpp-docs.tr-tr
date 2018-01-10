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
ms.workload: cplusplus
ms.openlocfilehash: 4d954abc593fcba3887da4f7ee4bd5ce1e443e18
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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