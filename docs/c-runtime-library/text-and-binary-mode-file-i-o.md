---
title: Metin ve İkili Mod Dosyası G/Ç
ms.date: 04/11/2018
f1_keywords:
- c.io
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
ms.openlocfilehash: 2c875350aedadb55d8f96fb682d6215030be2198
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57738589"
---
# <a name="text-and-binary-mode-file-io"></a>Metin ve İkili Mod Dosyası G/Ç

Dosya g/ç işlemleri Al iki çeviri modlarından birini yerinde *metin* veya *ikili*dosya açıldığı mod bağlı olarak. Veri dosyaları, genellikle metin modunda işlenir. Dosya çevirisi modu kontrol etmek için birini yapabilirsiniz:

- Geçerli varsayılan ayar Koru ve yalnızca seçilen dosyalar açıldığında alternatif modu belirtin.

- İşlevini [_set_fmode](../c-runtime-library/reference/set-fmode.md) açılmış dosyaları için yeni varsayılan modunu değiştirmek için. Kullanım [_get_fmode](../c-runtime-library/reference/get-fmode.md) geçerli varsayılan modu bulunamıyor. Metin modunu ilk varsayılan ayardır (**_O_TEXT**).

- Doğrudan genel değişkenini ayarlayarak varsayılan çeviri modunu değiştirmek [_fmode](../c-runtime-library/fmode.md) programınızdaki. İşlev **_set_fmode** Bu değişken, ancak değeri de ayarlanabilir doğrudan ayarlar.

Çağırdığınızda bir dosya açma işlevi gibi [_aç](../c-runtime-library/reference/open-wopen.md), [fopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md), [freopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md), [_fsopen](../c-runtime-library/reference/fsopen-wfsopen.md) veya [_sopen_s](../c-runtime-library/reference/sopen-s-wsopen-s.md), geçerli varsayılan ayarı geçersiz kılabilirsiniz **_fmode** işleviuygunbağımsızdeğişkenibelirterek[_set_fmode](../c-runtime-library/reference/set-fmode.md). **Stdin**, **stdout**, ve **stderr** akışları her zaman varsayılan olarak metin modunda açın; bu varsayılan bu dosyalar açılırken kılabilirsiniz. Kullanım [_setmode](../c-runtime-library/reference/setmode.md) dosya açıldıktan sonra dosya tanımlayıcısını kullanarak çeviri modunu değiştirmek için.

## <a name="see-also"></a>Ayrıca bkz.

[Girdi ve Çıktı](../c-runtime-library/input-and-output.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
