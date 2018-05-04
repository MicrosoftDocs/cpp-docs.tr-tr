---
title: Metin ve ikili mod dosyası g/ç | Microsoft Docs
ms.custom: ''
ms.date: 04/11/2018
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.io
dev_langs:
- C++
helpviewer_keywords:
- files [C++], open functions
- I/O [CRT], text files
- functions [CRT], file access
- binary access, binary mode file I/O
- translation, modes
- I/O [CRT], binary
- text files, I/O
- I/O [CRT], translation modes
- translation modes (file I/O)
- binary access
ms.assetid: 3196e321-8b87-4609-b302-cd6f3c516051
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4be1a3619fcd441dbcca53b0a1c369e30f9fb678
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="text-and-binary-mode-file-io"></a>Metin ve İkili Mod Dosyası G/Ç

Dosya g/ç işlemleri sürer iki çeviri modlarından birini yerinde *metin* veya *ikili*dosya açıldığı mod bağlı olarak. Veri dosyaları genellikle metin modunda işlenir. Dosya çevirisi modu denetlemek için birini yapabilirsiniz:

- Geçerli varsayılan ayarı koruyun ve yalnızca seçilen dosyaları açtığınızda alternatif modunu belirtin.

- İşlevini [_set_fmode](../c-runtime-library/reference/set-fmode.md) açılmış dosyaları için yeni varsayılan modunu değiştirmek için. Kullanım [_get_fmode](../c-runtime-library/reference/get-fmode.md) geçerli varsayılan mod bulunamıyor. Metin modunu ilk varsayılan ayardır (**_O_TEXT**).

- Doğrudan genel değişkeni ayarlayarak varsayılan çeviri modu değiştirme [_fmode](../c-runtime-library/fmode.md) programınızdaki. İşlev **_set_fmode** Bu değişken, ancak değerini de ayarlanabilir doğrudan ayarlar.

Çağırdığınızda bir dosyanın açılması işlevi gibi [_kurulum Aç](../c-runtime-library/reference/open-wopen.md), [fopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md), [freopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md), [_fsopen](../c-runtime-library/reference/fsopen-wfsopen.md) veya [_sopen_s](../c-runtime-library/reference/sopen-s-wsopen-s.md), geçerli varsayılan ayarı geçersiz kılabilirsiniz **_fmode** işlevineuygunbağımsızdeğişkenbelirterek[_set_fmode](../c-runtime-library/reference/set-fmode.md). **Stdin**, **stdout**, ve **stderr** akışları her zaman varsayılan olarak metin modunda açın; Ayrıca bu varsayılan bu dosyalar açılırken geçersiz kılabilirsiniz. Kullanım [_setmode](../c-runtime-library/reference/setmode.md) dosya açıldıktan sonra dosya tanımlayıcısı kullanılarak çeviri modu değiştirmek için.

## <a name="see-also"></a>Ayrıca Bkz.

[Girdi ve Çıktı](../c-runtime-library/input-and-output.md)<br/>
 [Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
