---
title: /UTF-8 belirtildiğinde (kaynak ve yürütülebilir karakter kümelerini UTF-8 olarak ayarla)
ms.date: 11/04/2016
f1_keywords:
- /utf-8
helpviewer_keywords:
- /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
ms.openlocfilehash: 1ff0f23ad0758642c73b1b35d6d4dd1be20899cb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498175"
---
# <a name="utf-8-set-source-and-executable-character-sets-to-utf-8"></a>/UTF-8 belirtildiğinde (kaynak ve yürütülebilir karakter kümelerini UTF-8 olarak ayarla)

Hem kaynak karakter kümesini hem de yürütme karakter kümesini UTF-8 olarak belirtir.

## <a name="syntax"></a>Sözdizimi

```
/utf-8
```

## <a name="remarks"></a>Açıklamalar

Kaynak ve yürütme karakter kümelerini UTF-8 kullanarak kodlanmış olarak belirtmek için **/UTF-8 belirtildiğinde** seçeneğini kullanabilirsiniz. Komut satırında **/Source-charset: UTF-8/Execution-charset: UTF-8** belirtmeye eşdeğerdir. Bu seçeneklerden herhangi biri, varsayılan olarak **/Validate-charset** seçeneğini de etkinleştirmesine izin vermez. Desteklenen kod sayfası tanımlayıcılarının ve karakter kümesi adlarının listesi için bkz. [kod sayfası tanımlayıcıları](/windows/win32/Intl/code-page-identifiers).

Varsayılan olarak, Visual Studio, kaynak dosyanın kodlanmış bir Unicode biçiminde olup olmadığını (örneğin, UTF-16 veya UTF-8) belirlemekte kullanılacak bir bayt sıra işareti algılar. Herhangi bir bayt düzeni işareti bulunmazsa, **/UTF-8 belirtildiğinde** veya **/Source-charset** seçeneğini kullanarak bir kod sayfası belirtmediğiniz müddetçe, kaynak dosyanın geçerli kullanıcı kodu sayfası kullanılarak kodlandığını varsayar. Visual Studio, birkaç karakter kodlamalarını C++ kullanarak kaynak kodunuzu kaydetmenizi sağlar. Kaynak ve yürütme karakter kümeleri hakkında bilgi için, dil belgelerindeki [karakter kümelerine](../../cpp/character-sets.md) bakın.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz [. C++ Visual Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**, **CC++/** , **komut satırı** klasörünü genişletin.

1. **Ek seçenekler**' de, tercih ettiğiniz kodlamayı belirtmek için **/UTF-8 belirtildiğinde** seçeneğini ekleyin.

1. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[/Execution-charset (yürütme karakter kümesini Ayarla)](execution-charset-set-execution-character-set.md)<br/>
[/source-charset (Kaynak Karakter Kümesini Ayarla)](source-charset-set-source-character-set.md)<br/>
[/validate-charset (Uyumlu karakterler için doğrula)](validate-charset-validate-for-compatible-characters.md)
