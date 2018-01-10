---
title: "Unicode akışı g-O metin ve ikili modlarda | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.io
dev_langs: C++
helpviewer_keywords:
- stream I/O routines
- I/O [CRT], unicode stream
- Unicode, stream I/O routines
- Unicode stream I/O
ms.assetid: 68be0c3e-a9e6-4fd5-b34a-1b5207f0e7d6
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 76e739ae95788448cc655ca18d32aaf1f8a5c90a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="unicode-stream-io-in-text-and-binary-modes"></a>Metin ve İkili Modlarda Unicode Akışı G/Ç
Ne zaman bir Unicode akışı g/ç yordamı (gibi `fwprintf`, `fwscanf`, `fgetwc`, `fputwc`, `fgetws`, veya `fputws`) metin modunda (varsayılan), iki tür karakter dönüştürme gerçekleşmesi açık olan bir dosya çalıştırır:  
  
-   Unicode ve MBCS veya MBCS Unicode dönüştürme. Ne zaman bir Unicode akışı-g/Ç işlev metin modunda, kaynak çalışır veya hedef akışı birden çok baytlı karakter dizisi olarak kabul edilir. Bu nedenle, Unicode akışı giriş işlevleri birden çok baytlı karakterler geniş karakter dönüştürme (olarak çağrısıyla varsa `mbtowc` işlevi). Aynı nedenden dolayı Unicode akışı çıkış işlevleri geniş karakterler birden çok baytlı karakterleri dönüştürme (olarak çağrısıyla varsa `wctomb` işlevi).  
  
-   Satır başı - yeni satır (CR-LF) çeviri. MBCS - Unicode dönüştürme (Unicode akışı giriş işlevleri için) önce bu çevirmesinin sonra Unicode - MBCS dönüştürme (için Unicode akışı çıkış işlevleri). Giriş sırasında her satır başı - satır besleme bileşimi tek satır besleme karakter çevrilir. Çıkış sırasında her bir satır besleme karakteri satır başı - satır besleme birleşimi çevrilir.  
  
 Ancak, bir Unicode akışı-g/Ç işlevi İkili modda çalıştığında, dosya Unicode olduğu varsayılır ve CR LF çeviri veya karakter dönüştürme giriş veya çıkış sırasında oluşur. _Setmode (_fileno (stdin), _o_bınary); kullanın wcin bir UNICODE metin dosyası doğru şekilde kullanmak için yönerge.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kategorilere göre çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)   
 [Girdi ve Çıktı](../c-runtime-library/input-and-output.md)