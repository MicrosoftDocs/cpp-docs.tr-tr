---
description: 'Hakkında daha fazla bilgi edinin: `/utf-8` (kaynak ve yürütülebilir karakter kümelerini olarak ayarla UTF-8 )'
title: /UTF-8 belirtildiğinde (kaynak ve yürütülebilir karakter kümelerini olarak ayarla UTF-8 )
ms.date: 04/26/2020
f1_keywords:
- /utf-8
helpviewer_keywords:
- /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
no-loc:
- UTF
- UTF-8
- UTF-16
ms.openlocfilehash: f9d58315a55d0e390ec07a1907af0befda127c54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176411"
---
# <a name="utf-8-set-source-and-executable-character-sets-to-no-locutf-8"></a>`/utf-8` (Kaynak ve yürütülebilir karakter kümelerini olarak ayarla UTF-8 )

Hem kaynak karakter kümesini hem de yürütme karakter kümesini belirtir UTF-8 .

## <a name="syntax"></a>Syntax

> **`/utf-8`**

## <a name="remarks"></a>Açıklamalar

Öğesini **`/utf-8`** kullanarak hem kaynak hem de yürütme karakter kümelerini belirtmek için seçeneğini kullanabilirsiniz UTF-8 . **`/source-charset:utf-8 /execution-charset:utf-8`** Komut satırında belirtmeye eşdeğerdir. Bu seçeneklerden herhangi biri, **`/validate-charset`** Varsayılan olarak seçeneği de sunar. Desteklenen kod sayfası tanımlayıcılarının ve karakter kümesi adlarının listesi için bkz. [kod sayfası tanımlayıcıları](/windows/win32/Intl/code-page-identifiers).

Varsayılan olarak, Visual Studio kaynak dosyanın kodlanmış bir Unicode biçiminde olup olmadığını (örneğin, veya) tespit etmek için bir bayt sırası işareti algılar UTF-16 UTF-8 . Herhangi bir bayt düzeni işareti bulunmazsa, veya seçeneğini kullanarak bir kod sayfası belirtmediğiniz müddetçe, kaynak dosyanın geçerli kullanıcı kodu sayfası kullanılarak kodlandığını varsayar **`/utf-8`** **`/source-charset`** . Visual Studio, birkaç karakter kodlamalarını kullanarak C++ kaynak kodunuzu kaydetmenizi sağlar. Kaynak ve yürütme karakter kümeleri hakkında bilgi için, dil belgelerindeki [karakter kümelerine](../../cpp/character-sets.md) bakın.

## <a name="set-the-option-in-visual-studio-or-programmatically"></a>Visual Studio veya program aracılığıyla seçeneği ayarlama

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler**' de, **`/utf-8`** tercih ettiğiniz kodlamayı belirtme seçeneğini ekleyin.

1. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)<br/>
[/Execution-charset (yürütme karakter kümesini Ayarla)](execution-charset-set-execution-character-set.md)<br/>
[/Source-charset (kaynak karakter kümesini Ayarla)](source-charset-set-source-character-set.md)<br/>
[/validate-charset (Uyumlu karakterler için doğrula)](validate-charset-validate-for-compatible-characters.md)
