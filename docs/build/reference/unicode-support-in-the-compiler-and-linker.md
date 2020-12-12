---
description: 'Daha fazla bilgi edinin: derleyicide ve bağlayıcıda Unicode desteği'
title: Derleyicide ve Bağlayıcıda Unicode Desteği
ms.date: 12/15/2017
f1_keywords:
- VC.Project.VCLinkerTool.UseUnicodeResponseFiles
- VC.Project.VCLibrarianTool.UseUnicodeResponseFiles
- VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles
- VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles
helpviewer_keywords:
- Unicode, Visual C++
ms.openlocfilehash: c853907dd0d70a4ab7311c41f51d8d73bb25cf20
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97178959"
---
# <a name="unicode-support-in-the-compiler-and-linker"></a>Derleyicide ve Bağlayıcıda Unicode Desteği

Çoğu Visual C++ yapı aracı Unicode girişlerini ve çıkışları destekler.

## <a name="filenames"></a>Dosya Adları

Komut satırında veya Derleyici yönergelerinde (gibi) belirtilen dosya adları `#include` , Unicode karakterler içerebilir.

## <a name="source-code-files"></a>Kaynak kodu dosyaları

Tanımlayıcıları, makroları, dize ve karakter değişmezlerini ve açıklamalarda Unicode karakterleri desteklenir.  Evrensel karakter adları da desteklenir.

Unicode, aşağıdaki kodlamalarda bir kaynak kod dosyasına giriş yapabilir:

- UTF-16 little endian bayt sırası işareti (BOM) ile veya olmadan

- , BOM ile veya olmadan UTF-16 big endian

- BOM ile UTF-8

## <a name="output"></a>Çıktı

Derleme sırasında derleyici, tanılamayı, UTF-16 ' da konsola verir.  Konsolunuzun içinde görüntülenebilen karakterler konsol penceresi özelliklerine bağlıdır.  Bir dosyaya yönlendirilen derleyici çıkışı, geçerli ANSI konsol kod sayfasında bulunur.

## <a name="linker-response-files-and-def-files"></a>Bağlayıcı yanıt dosyaları ve. DEF dosyaları

Yanıt dosyaları ve DEF dosyaları, bir BOM ya da ANSI ile UTF-16 olabilir.

## <a name="asm-and-cod-dumps"></a>. asm ve. cod dökümleri

. asm ve. cod dökümleri, MASM ile uyumluluk için varsayılan olarak ANSI 'de bulunur. UTF-8 çıktısını almak için [/FAU](fa-fa-listing-file.md) kullanın. **/Fas** belirtirseniz, ıntermingled kaynağının doğrudan yazdırılacağını ve bozuk görünebileceğini unutmayın. Örneğin, kaynak kodu UTF-8 ise ve **/FAsu** belirtmediyseniz.

## <a name="see-also"></a>Ayrıca bkz.

[Komut satırından MSVC araç takımını kullanma](../building-on-the-command-line.md)
