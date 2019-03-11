---
title: Metin ve İkili Modlarda Unicode Akışı G/Ç
ms.date: 11/04/2016
f1_keywords:
- c.io
helpviewer_keywords:
- stream I/O routines
- I/O [CRT], unicode stream
- Unicode, stream I/O routines
- Unicode stream I/O
ms.assetid: 68be0c3e-a9e6-4fd5-b34a-1b5207f0e7d6
ms.openlocfilehash: c16d2f74856bb42dfd6ffc4e1af7306f6edd97fb
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57746023"
---
# <a name="unicode-stream-io-in-text-and-binary-modes"></a>Metin ve İkili Modlarda Unicode Akışı G/Ç

Ne zaman bir Unicode akışı g/ç yordamına (gibi **fwprintf**, **fwscanf**, **fgetwc**, **fputwc**, **fgetws**, veya **fputws**) metin modunda (varsayılan), iki tür karakter dönüştürme gerçekleşmesi açık olan bir dosya üzerinde çalışır:

- Unicode MBCS veya MBCS-Unicode dönüştürme. Ne zaman bir Unicode akışı g/Ç işlevi metin modunda, kaynak çalışır veya hedef akışın bir dizi çok baytlı karakter olduğu varsayılır. Bu nedenle Unicode akışı girdi işlevleri çok baytlı karakter geniş karakterlere dönüştürür (bir çağrıda olduğu gibi **mbtowc** işlevi). Aynı nedenden dolayı Unicode akış çıkışı işlevleri geniş karakterleri çok baytlı karakterlere dönüştürür (bir çağrıda olduğu gibi **wctomb** işlevi).

- Satır başı - satır besleme (CR-LF) çeviri. MBCS - Unicode dönüştürme (Unicode akışı girdi işlevleri için) önce bu çeviri oluşur ve Unicode - MBCS dönüştürme (için Unicode akış çıkışı işlevleri) sonra. Giriş sırasında her satır başı - satır besleme birleşimi bir tek satır besleme karakteri ile çevrilmiştir. Çıkış sırasında her bir satır besleme karakteri bir satır başı - satır besleme bileşimi çevrilir.

Ancak, bir Unicode akışı g/Ç işlevi İkili modda çalışırken, dosya Unicode olarak kabul edilir ve CR-LF çeviri veya karakter dönüştürme giriş veya çıkış sırasında oluşur. _Setmode (_fileno (stdin), _o_bınary) kullanın wcin UNICODE metin dosyası üzerinde doğru şekilde kullanmak için yönerge.

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
[Girdi ve Çıktı](../c-runtime-library/input-and-output.md)<br/>
