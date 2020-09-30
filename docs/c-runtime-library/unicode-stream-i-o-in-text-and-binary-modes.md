---
title: Metin ve İkili Modlarda Unicode Akışı G/Ç
description: Unicode akış g/ç ile karakter dönüştürmelerinden oluşan bir açıklama.
ms.topic: conceptual
ms.date: 11/04/2016
helpviewer_keywords:
- stream I/O routines
- I/O [CRT], unicode stream
- Unicode, stream I/O routines
- Unicode stream I/O
ms.assetid: 68be0c3e-a9e6-4fd5-b34a-1b5207f0e7d6
ms.openlocfilehash: 9c4ef7da54463021f9487849df0235ae289e38fa
ms.sourcegitcommit: 9451db8480992017c46f9d2df23fb17b503bbe74
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2020
ms.locfileid: "91590244"
---
# <a name="unicode-stream-io-in-text-and-binary-modes"></a>Metin ve İkili Modlarda Unicode Akışı G/Ç

Bir Unicode akış g/ç yordamı ( **fwprintf**, **fwscanf**, **fgetwc**, **fputwc**, **fgetws**veya **fınputıı**gibi) metin modunda (varsayılan) açık olan bir dosya üzerinde çalıştığında, iki tür karakter dönüştürme gerçekleşir:

- Unicode-MBCS veya MBCS 'den Unicode 'a dönüştürme. Unicode Stream-g/ç işlevi metin modunda çalışırken, kaynak veya hedef akışın çok baytlı karakterler dizisi olduğu varsayılır. Bu nedenle, Unicode akış girişi işlevleri çok baytlı karakterleri geniş karakterlere dönüştürür ( **mbtowc** işlevine yapılan bir çağrıda olduğu gibi). Aynı nedenden dolayı, Unicode akış çıkışı işlevleri çok baytlı karakterlere ( **wctomb** işlevine yapılan bir çağrıda olduğu gibi) çok fazla karakter dönüştürür.

- Satır başı satır besleme (CR-LF) çevirisi. Bu çeviri, MBCS-Unicode dönüşümden (Unicode akış girişi işlevleri için) ve Unicode-MBCS dönüştürmesinden (Unicode akış çıkış işlevleri için) önce oluşur. Giriş sırasında her bir satır başı satır besleme kombinasyonu tek satırlık bir akış karakteriyle çevrilir. Çıkış sırasında, her satır besleme karakteri bir satır başı satır besleme birleşimine çevrilir.

Ancak, bir Unicode Stream-g/ç işlevi ikili modda çalışırken, dosyanın Unicode olduğu varsayılır ve giriş veya çıkış sırasında CR-LF çevirisi veya karakter dönüştürme gerçekleşmez. `_setmode( _fileno( stdin ), _O_BINARY );`BIR UNICODE metin dosyasında doğru şekilde kullanmak için yönergesini kullanın `wcin` .

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
[Giriş ve çıkış](../c-runtime-library/input-and-output.md)<br/>
