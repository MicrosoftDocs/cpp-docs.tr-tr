---
title: / UTF-8 (kaynak ayarlayın ve yürütülebilir karakter kümelerini UTF-8)
ms.date: 11/04/2016
f1_keywords:
- /utf-8
helpviewer_keywords:
- /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
ms.openlocfilehash: cb71e1846348adf4cf8a8eb385e6c5f7ac2bac74
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636533"
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

1. Projeyi açmak **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri**, **C/C++**, **komut satırı** klasör.

1. İçinde **Gelişmiş Seçenekler**, ekleme **/UTF-8** seçenek ve tercih edilen kodlamayı belirtin.

1. Seçin **Tamam** yaptığınız değişiklikleri kaydedin.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[/ Execution-Charset (yürütme karakter kümesini Ayarla)](../../build/reference/execution-charset-set-execution-character-set.md)<br/>
[/source-charset (Kaynak Karakter Kümesini Ayarla)](../../build/reference/source-charset-set-source-character-set.md)<br/>
[/validate-charset (Uyumlu karakterler için doğrula)](../../build/reference/validate-charset-validate-for-compatible-characters.md)