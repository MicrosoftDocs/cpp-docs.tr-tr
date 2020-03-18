---
title: Metin ve İkili Mod Dosyası G/Ç
ms.date: 04/11/2018
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
ms.openlocfilehash: 75d302e625747d6e02e1d904c21542530d70d02f
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79444632"
---
# <a name="text-and-binary-mode-file-io"></a>Metin ve İkili Mod Dosyası G/Ç

Dosya g/ç işlemleri, dosyanın açıldığı moda bağlı olarak iki çeviri modundan birinde, *metin* veya *ikili*bir yerde gerçekleşir. Veri dosyaları genellikle metin modunda işlenir. Dosya çevirisi modunu denetlemek için aşağıdakilerden biri olabilir:

- Geçerli varsayılan ayarı koruyun ve yalnızca seçili dosyaları açtığınızda alternatif modu belirtin.

- Yeni açılan dosyaların varsayılan modunu değiştirmek için [_set_fmode](../c-runtime-library/reference/set-fmode.md) işlevini kullanın. Geçerli varsayılan modu bulmak için [_get_fmode](../c-runtime-library/reference/get-fmode.md) kullanın. İlk varsayılan ayar metin modudur ( **_O_TEXT**).

- Varsayılan çeviri modunu programınızdaki [_fmode](../c-runtime-library/fmode.md) genel değişkeni ayarlayarak doğrudan değiştirin. İşlevi **_set_fmode** bu değişkenin değerini ayarlar, ancak doğrudan de ayarlanabilir.

[_Open](../c-runtime-library/reference/open-wopen.md), [fopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md), [serbest aç](../c-runtime-library/reference/freopen-wfreopen.md), [freopen_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md), [_fsopen](../c-runtime-library/reference/fsopen-wfsopen.md) veya [_sopen_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)gibi bir dosya açma işlevini çağırdığınızda, işlev [_fmode](../c-runtime-library/reference/set-fmode.md)uygun bağımsız değişkenini belirterek **_set_fmode** geçerli varsayılan ayarını geçersiz kılabilirsiniz. **STDIN**, **stdout**ve **stderr** akışları her zaman varsayılan olarak metin modunda açılır; Ayrıca, bu dosyalardan herhangi birini açarken bu varsayılanı geçersiz kılabilirsiniz. Dosya açıldıktan sonra dosya tanımlayıcısını kullanarak çeviri modunu değiştirmek için [_setmode](../c-runtime-library/reference/setmode.md) kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Girdi ve Çıktı](../c-runtime-library/input-and-output.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
