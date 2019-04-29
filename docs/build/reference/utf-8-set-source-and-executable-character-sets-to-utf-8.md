---
title: / UTF-8 (kaynak ayarlayın ve yürütülebilir karakter kümelerini UTF-8)
ms.date: 11/04/2016
f1_keywords:
- /utf-8
helpviewer_keywords:
- /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
ms.openlocfilehash: 5ac15c63041e76b8bb0d292868bb982c21866078
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317295"
---
# <a name="utf-8-set-source-and-executable-character-sets-to-utf-8"></a>/ UTF-8 (kaynak ayarlayın ve yürütülebilir karakter kümelerini UTF-8)

Hem kaynak karakter kümesi ve UTF-8 yürütme karakter kümesini belirtir.

## <a name="syntax"></a>Sözdizimi

```
/utf-8
```

## <a name="remarks"></a>Açıklamalar

Kullanabileceğiniz **/UTF-8** kaynak ve yürütme karakter kümelerinin UTF-8 kullanarak kodlanmış olarak belirtmek için seçeneği. Belirtmeye eşdeğerdir **/source-charset:utf-8 /execution-charset:utf-8** komut satırında. Bunlardan birine seçenekleri de etkinleştirir **/Validate-Charset** varsayılan seçeneği. Karakter kümesi adları ve kod sayfası tanımlayıcıları desteklenen bir listesi için bkz. [kod sayfası tanımlayıcıları](/windows/desktop/Intl/code-page-identifiers).

Varsayılan olarak, Visual Studio kaynak dosya kodlanmış bir Unicode biçiminde, örneğin, UTF-16 veya UTF-8 olup olmadığını belirlemek için bayt sırası işareti algılar. Bayt sırası işareti yoksa bulunursa, kaynak dosyası kodlanmış geçerli kullanıcı kod sayfası kullanılarak kullanarak bir kod sayfası belirtmiş olduğunuz sürece varsayar **/UTF-8** veya **/Source-Charset** seçeneği. Visual Studio birkaç karakter kodlamaları birini kullanarak C++ kaynak kod kaydetmenize olanak tanır. Kaynak ve yürütme karakter kümeleri hakkında daha fazla bilgi için bkz: [karakter kümeleri](../../cpp/character-sets.md) dil belgelerinde.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projeyi açmak **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri**, **C/C++**, **komut satırı** klasör.

1. İçinde **ek seçenekler**, ekleme **/UTF-8** tercih edilen kodlamayı belirtmek için seçeneği.

1. Seçin **Tamam** yaptığınız değişiklikleri kaydedin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[/ Execution-Charset (yürütme karakter kümesini Ayarla)](execution-charset-set-execution-character-set.md)<br/>
[/source-charset (Kaynak Karakter Kümesini Ayarla)](source-charset-set-source-character-set.md)<br/>
[/validate-charset (Uyumlu karakterler için doğrula)](validate-charset-validate-for-compatible-characters.md)
