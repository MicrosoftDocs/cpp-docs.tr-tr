---
title: /UTF-8 belirtildiğinde (kaynak ve yürütülebilir karakter kümelerini olarak UTF-8ayarla)
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
ms.openlocfilehash: c98a30b0ec4b36b8bd87fb0956d9382751975cfd
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168871"
---
# <a name="utf-8-set-source-and-executable-character-sets-to-opno-locutf-8"></a>`/utf-8`(Kaynak ve yürütülebilir karakter kümelerini olarak UTF-8ayarla)

Hem kaynak karakter kümesini hem de yürütme karakter kümesini belirtir UTF-8.

## <a name="syntax"></a>Sözdizimi

> **`/utf-8`**

## <a name="remarks"></a>Açıklamalar

Öğesini kullanarak UTF-8hem kaynak **`/utf-8`** hem de yürütme karakter kümelerini belirtmek için seçeneğini kullanabilirsiniz. Komut satırında belirtmeye **`/source-charset:utf-8 /execution-charset:utf-8`** eşdeğerdir. Bu seçeneklerden herhangi biri, **`/validate-charset`** varsayılan olarak seçeneği de sunar. Desteklenen kod sayfası tanımlayıcılarının ve karakter kümesi adlarının listesi için bkz. [kod sayfası tanımlayıcıları](/windows/win32/Intl/code-page-identifiers).

Varsayılan olarak, Visual Studio kaynak dosyanın kodlanmış bir Unicode biçiminde olup olmadığını (örneğin, UTF-16 veya UTF-8) tespit etmek için bir bayt sırası işareti algılar. Herhangi bir bayt düzeni işareti bulunmazsa, veya **`/utf-8`** **`/source-charset`** seçeneğini kullanarak bir kod sayfası belirtmediğiniz müddetçe, kaynak dosyanın geçerli kullanıcı kodu sayfası kullanılarak kodlandığını varsayar. Visual Studio, birkaç karakter kodlamalarını kullanarak C++ kaynak kodunuzu kaydetmenizi sağlar. Kaynak ve yürütme karakter kümeleri hakkında bilgi için, dil belgelerindeki [karakter kümelerine](../../cpp/character-sets.md) bakın.

## <a name="set-the-option-in-visual-studio-or-programmatically"></a>Visual Studio veya program aracılığıyla seçeneği ayarlama

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **C/C++** > **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler**' de, tercih **`/utf-8`** ettiğiniz kodlamayı belirtme seçeneğini ekleyin.

1. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[/Execution-charset (yürütme karakter kümesini Ayarla)](execution-charset-set-execution-character-set.md)<br/>
[/source-charset (Kaynak Karakter Kümesini Ayarla)](source-charset-set-source-character-set.md)<br/>
[/validate-charset (Uyumlu karakterler için doğrula)](validate-charset-validate-for-compatible-characters.md)
