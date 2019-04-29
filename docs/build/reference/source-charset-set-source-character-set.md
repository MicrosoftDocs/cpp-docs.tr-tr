---
title: / Source-Charset (kaynak karakter kümesini Ayarla)
ms.date: 02/06/2019
f1_keywords:
- source-charset
- /source-charset
helpviewer_keywords:
- /execution-charset compiler option
ms.assetid: d3c5bf7f-526d-4ee4-acc5-c1a02a4fc481
ms.openlocfilehash: 54f8d4d0edaa310384d19a9c9a188f96ec895eac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318218"
---
# <a name="source-charset-set-source-character-set"></a>/ Source-Charset (kaynak karakter kümesini Ayarla)

Kaynak karakter için bir yürütülebilir dosyanızın belirtmenize olanak sağlar.

## <a name="syntax"></a>Sözdizimi

```
/source-charset:[IANA_name|.CPID]
```

## <a name="arguments"></a>Arguments

**IANA_name**<br/>
IANA tarafından tanımlanan karakter kümesinin adı.

**CPID**<br/>
Ondalık sayı olarak kod sayfası tanımlayıcısı.

## <a name="remarks"></a>Açıklamalar

Kullanabileceğiniz **/Source-Charset** bir genişletilmiş kaynak karakter kümesi Kaynak dosyalarınız temel kaynak karakter kümesinde temsil karakter eklediğinizde kullanılacağını belirtmek için seçeneği. Kaynak karakter kümesi, programınızın kaynak metin ön işleme aşamalarını derleme önce girdi olarak kullanılan iç temsili yorumlamak için kullanılan kodlamayı ' dir. İç gösterimine sonra yürütülebilir dosya dize ve karakter değerlerini depolamak için yürütme karakter kümesi dönüştürülür. Ya da IANA kullanabilir veya ISO karakter kümesinin adı veya bir nokta (.) karakter kümesini belirtmek için bir 3-5 basamaklı ondalık kod sayfası tanımlayıcısı tarafından takip. Karakter kümesi adları ve kod sayfası tanımlayıcıları desteklenen bir listesi için bkz. [kod sayfası tanımlayıcıları](/windows/desktop/Intl/code-page-identifiers).

Varsayılan olarak, Visual Studio kaynak dosya kodlanmış bir Unicode biçiminde, örneğin, UTF-16 veya UTF-8 olup olmadığını belirlemek için bayt sırası işareti algılar. Bayt sırası işareti yoksa bulunursa, kaynak dosyası kodlanmış geçerli kullanıcı kod sayfasını kullanarak, bir karakter kümesi adı veya kod sayfasını kullanarak belirtmediğiniz sürece varsayar **/Source-Charset** seçeneği. Visual Studio birkaç karakter kodlamaları birini kullanarak C++ kaynak kod kaydetmenize olanak tanır. Kaynak ve yürütme karakter kümeleri hakkında daha fazla bilgi için bkz. [karakter kümeleri](../../cpp/character-sets.md) dil belgelerinde.

Sağladığınız kaynak karakter kümesi 7 bit ASCII karakter, karakter kümesindeki aynı kod noktaları eşlenmelidir veya izlemek çok sayıda derleme hataları olasıdır. Ayrıca, kaynak karakter kümesi eşlenebilir encodable UTF-8 Ayarla genişletilmiş Unicode karakter olmalıdır. UTF-8'de encodable olmayan karakterler bir uygulamaya özgü alternatif tarafından temsil edilir. Microsoft derleyicisi için bu karakterler soru işareti kullanır.

Kaynak karakter kümesi hem yürütme karakter kümesini UTF-8'e ayarlamak istiyorsanız, kullanabileceğiniz **/UTF-8** kısayol olarak derleyici seçeneği. Belirtmeye eşdeğerdir **/source-charset:utf-8 /execution-charset:utf-8** komut satırında. Bunlardan birine seçenekleri de etkinleştirir **/Validate-Charset** varsayılan seçeneği.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projeyi açmak **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri**, **C/C++**, **komut satırı** klasör.

1. İçinde **ek seçenekler**, ekleme **/Source-Charset** seçenek ve tercih edilen kodlamayı belirtin.

1. Seçin **Tamam** yaptığınız değişiklikleri kaydedin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[/ Execution-Charset (yürütme karakter kümesini Ayarla)](execution-charset-set-execution-character-set.md)<br/>
[/utf-8 (Kaynak ve Yürütülebilir karakter kümelerini UTF-8 olarak ayarla)](utf-8-set-source-and-executable-character-sets-to-utf-8.md)<br/>
[/validate-charset (Uyumlu karakterler için doğrula)](validate-charset-validate-for-compatible-characters.md)
