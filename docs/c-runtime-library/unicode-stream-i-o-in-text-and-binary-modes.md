---
title: Metin ve ikili modlarda Unicode akışı g/ç | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.io
dev_langs:
- C++
helpviewer_keywords:
- stream I/O routines
- I/O [CRT], unicode stream
- Unicode, stream I/O routines
- Unicode stream I/O
ms.assetid: 68be0c3e-a9e6-4fd5-b34a-1b5207f0e7d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b89ff3fc752901e9b3cf30c305110b387dc04562
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="unicode-stream-io-in-text-and-binary-modes"></a>Metin ve İkili Modlarda Unicode Akışı G/Ç

Ne zaman bir Unicode akışı g/ç yordamı (gibi **fwprintf**, **fwscanf**, **fgetwc**, **fputwc**, **fgetws**, veya **fputws**) metin modunda (varsayılan), iki tür karakter dönüştürme gerçekleşmesi açık olan bir dosya çalıştırır:

- Unicode ve MBCS veya MBCS Unicode dönüştürme. Ne zaman bir Unicode akışı-g/Ç işlev metin modunda, kaynak çalışır veya hedef akışı birden çok baytlı karakter dizisi olarak kabul edilir. Bu nedenle, Unicode akışı giriş işlevleri birden çok baytlı karakterler geniş karakter dönüştürme (olarak varsa çağrısı ile **mbtowc** işlevi). Aynı nedenden dolayı Unicode akışı çıkış işlevleri geniş karakterler birden çok baytlı karakterleri dönüştürme (olarak varsa çağrısı ile **wctomb** işlevi).

- Satır başı - yeni satır (CR-LF) çeviri. MBCS - Unicode dönüştürme (Unicode akışı giriş işlevleri için) önce bu çevirmesinin sonra Unicode - MBCS dönüştürme (için Unicode akışı çıkış işlevleri). Giriş sırasında her satır başı - satır besleme bileşimi tek satır besleme karakter çevrilir. Çıkış sırasında her bir satır besleme karakteri satır başı - satır besleme birleşimi çevrilir.

Ancak, bir Unicode akışı-g/Ç işlevi İkili modda çalıştığında, dosya Unicode olduğu varsayılır ve CR LF çeviri veya karakter dönüştürme giriş veya çıkış sırasında oluşur. _Setmode (_fileno (stdin), _o_bınary); kullanın wcin bir UNICODE metin dosyası doğru şekilde kullanmak için yönerge.

## <a name="see-also"></a>Ayrıca Bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
[Girdi ve Çıktı](../c-runtime-library/input-and-output.md)<br/>
