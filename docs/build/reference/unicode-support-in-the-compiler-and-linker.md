---
title: "Derleyicide ve bağlayıcıda Unicode desteği | Microsoft Docs"
ms.custom: 
ms.date: 12/15/2017
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.UseUnicodeResponseFiles
- VC.Project.VCLibrarianTool.UseUnicodeResponseFiles
- VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles
- VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles
dev_langs: C++
helpviewer_keywords: Unicode, Visual C++
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fe775a53914089648a868a94aa2c863ee87790c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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