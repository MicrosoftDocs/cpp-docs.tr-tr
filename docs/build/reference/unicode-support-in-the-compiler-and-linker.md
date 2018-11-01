---
title: Derleyicide ve Bağlayıcıda Unicode Desteği
ms.date: 12/15/2017
f1_keywords:
- VC.Project.VCLinkerTool.UseUnicodeResponseFiles
- VC.Project.VCLibrarianTool.UseUnicodeResponseFiles
- VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles
- VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles
helpviewer_keywords:
- Unicode, Visual C++
ms.openlocfilehash: cb21165e51960c0ca2f728381413c1a7260c9f83
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50494984"
---
# <a name="unicode-support-in-the-compiler-and-linker"></a>Derleyicide ve Bağlayıcıda Unicode Desteği

Çoğu Visual C++ derleme araçları, Unicode giriş ve çıkışlarını destekler.

## <a name="filenames"></a>Dosya Adları

Komut satırında veya derleme yönergelerinde belirtilen dosya adları (gibi `#include`) Unicode karakterler içerebilir.

## <a name="source-code-files"></a>Kaynak kodu dosyaları

Unicode karakterler tanımlayıcıları, makroları, dize ve karakter değişmez değerleri ve açıklamaları desteklenir.  Evrensel karakter adları da desteklenir.

Unicode aşağıdaki kodlamalarda kaynak kod dosyasına girilebilir:

- UTF-16 little endian içeren veya içermeyen bayt sırası işareti (BOM)

- UTF-16 big endian içeren veya içermeyen ürün reçetesi

- BOM ile UTF-8

## <a name="output"></a>Çıkış

Derleme sırasında derleyici UTF-16 içindeki konsola tanılama çıktısını alır.  Konsolunuzda görüntülenebilen karakterler konsol penceresinin özelliklerine bağlıdır.  Dosyaya yeniden yönlendirilen Derleyici çıktısı geçerli ANSI konsol kod sayfasındadır.

## <a name="linker-response-files-and-def-files"></a>Bağlayıcı yanıt dosyaları ve. DEF dosyaları

Yanıt dosyaları ve DEF dosyaları ya da UTF-16 BOM ya da ANSI olabilir.

## <a name="asm-and-cod-dumps"></a>.asm ve .cod dökümleri

.asm ve .cod dökümleri, varsayılan olarak MASM ile uyumluluk için ANSI olan. Kullanım [/fau](../../build/reference/fa-fa-listing-file.md) UTF-8 çıktısını almak için. Belirttiğiniz gerçekleştiriyorsanız **/Fas**, karıştırılmış kaynak yalnızca doğrudan yazdırılır ve, örneğin kaynak kodu UTF-8. ve belirtmediğiniz görünebileceğini **fasu**.

## <a name="see-also"></a>Ayrıca bkz.

[Komut satırında C/C++ kodu derleme](../../build/building-on-the-command-line.md)