---
description: 'Daha fazla bilgi edinin: derleyicide ve bağlayıcıda Unicode desteği'
title: Derleyicide ve Bağlayıcıda Unicode Desteği
ms.date: 03/07/2021
f1_keywords:
- VC.Project.VCLinkerTool.UseUnicodeResponseFiles
- VC.Project.VCLibrarianTool.UseUnicodeResponseFiles
- VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles
- VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles
helpviewer_keywords:
- Unicode, Visual C++
ms.openlocfilehash: e1795a5a9b9d4a3a1672b2661aa598d0ef6e059f
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102465346"
---
# <a name="unicode-support-in-the-compiler-and-linker"></a>Derleyicide ve bağlayıcıda Unicode desteği

Çoğu Microsoft C/C++ (MSVC) derleme araçları Unicode girişlerini ve çıkışları destekler.

## <a name="filenames"></a>Dosya Adları

Komut satırında veya Derleyici yönergelerinde (gibi) belirtilen dosya adları `#include` , Unicode karakterler içerebilir.

## <a name="source-code-files"></a>Kaynak kodu dosyaları

Tanımlayıcıları, makroları, dize ve karakter değişmezlerini ve açıklamalarda Unicode karakterleri desteklenir.  Evrensel karakter adları da desteklenir.

Unicode, aşağıdaki kodlamalarda bir kaynak kod dosyasına giriş yapabilir:

- UTF-16 little endian bayt sırası işareti (BOM) ile veya olmadan

- , BOM ile veya olmadan UTF-16 big endian

- BOM ile UTF-8

Visual Studio IDE 'de, dosyaları Unicode olanlar da dahil olmak üzere birkaç kodlama biçiminde kaydedebilirsiniz. **Kaydet** düğmesine açılan menüyü kullanarak **dosyayı farklı kaydet** iletişim kutusuna kaydedin. Açılan listede **kodlamalı kaydet** ' i seçin. Ardından, **Gelişmiş kaydetme seçenekleri** iletişim kutusunda, açılan listeden bir kodlama seçin. Dosyayı kaydetmek için **Tamam ' ı** seçin.

## <a name="output"></a>Çıktı

Derleme sırasında derleyici, tanılamayı, UTF-16 ' da konsola verir.  Konsolunuzun içinde görüntülenebilen karakterler konsol penceresi özelliklerine bağlıdır.  Bir dosyaya yönlendirilen derleyici çıkışı, geçerli ANSI konsol kod sayfasında bulunur.

## <a name="linker-response-files-and-def-files"></a>Bağlayıcı yanıt dosyaları ve `.DEF` dosyaları

Yanıt dosyaları ve *`.DEF`* dosyalar, BIR bom veya ANSI Ile UTF-16 ya da UTF-8 olabilir.

## <a name="asm-and-cod-dumps"></a>`.asm` ve `.cod` dökümleri

*`.asm`* ve *`.cod`* dökümleri, Masd ile uyumluluk için varsayılan olarak ANSI olarak ayarlanır. [`/FAu`](fa-fa-listing-file.md)UTF-8 çıktısını almak için kullanın.

Belirtirseniz **`/FAs`** , ıntermingled kaynağı doğrudan yazdırılır. Örneğin, kaynak kodu UTF-8 olduğunda ve belirtmediğiniz durumlarda bozuk görünebilir **`/FAsu`** .

## <a name="see-also"></a>Ayrıca bkz.

[Komut satırından MSVC araç takımını kullanma](../building-on-the-command-line.md)
