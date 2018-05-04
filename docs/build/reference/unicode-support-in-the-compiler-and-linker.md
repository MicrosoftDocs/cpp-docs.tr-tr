---
title: Derleyicide ve bağlayıcıda Unicode desteği | Microsoft Docs
ms.custom: ''
ms.date: 12/15/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.UseUnicodeResponseFiles
- VC.Project.VCLibrarianTool.UseUnicodeResponseFiles
- VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles
- VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles
dev_langs:
- C++
helpviewer_keywords:
- Unicode, Visual C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec0b84cd62f3fcca378ab55de16006925e685b37
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="unicode-support-in-the-compiler-and-linker"></a>Derleyicide ve Bağlayıcıda Unicode Desteği

Çoğu Visual C++ derleme araçları Unicode girişleri ve çıkışları destekler.

## <a name="filenames"></a>Dosya Adları

Komut satırında veya derleyici yönergeleri belirtilen dosya adları (gibi `#include`) Unicode karakterler içerebilir.

## <a name="source-code-files"></a>Kaynak kodu dosyaları

Unicode karakterler tanımlayıcıları, makroları, dize ve karakter değişmez değerleri ve açıklamaları desteklenir.  Evrensel karakter adları de desteklenir.

Unicode aşağıdaki Kodlamalar bir kaynak kodu dosyasına girebilirsiniz:

- UTF-16 little endian bayt sırası işareti (BOM) olmadan veya ile

- UTF-16 big endian ile veya olmadan AĞACI

- UTF-8 ile AĞACI

## <a name="output"></a>Çıkış

Derleme sırasında derleyici UTF-16 konsolunda tanılama çıkarır.  Konsol penceresinde özellikler, konsolda görüntülenen karakterleri bağlıdır.  Bir dosyaya yeniden yönlendirilen derleyici çıkışı geçerli ANSI konsol kod sayfasında yapılır.

## <a name="linker-response-files-and-def-files"></a>Bağlayıcı yanıt dosyaları ve. DEF dosyaları

Yanıt dosyaları ve DEF dosyalarını bir ürün reçetesi veya ANSI ya da UTF-16 olabilir.

## <a name="asm-and-cod-dumps"></a>.asm ve .cod dökümleri

.asm ve .cod dökümleri ANSI MASM ile uyumluluk için varsayılan olan. Kullanım [/FAu](../../build/reference/fa-fa-listing-file.md) UTF-8 çıktısını almak için. Belirttiğiniz gerçekleştiriyorsanız **/FAs**, intermingled kaynak yalnızca doğrudan basılır ve, örneğin kaynak kodudur UTF-8 ve belirtmediğiniz bozuk görünebilir **/FAsu**.

## <a name="see-also"></a>Ayrıca bkz.

[Komut satırında C/C++ kodu derleme](../../build/building-on-the-command-line.md)