---
description: :/Execution-charset (yürütme karakter kümesini Ayarla) hakkında daha fazla bilgi
title: /Execution-charset (yürütme karakter kümesini Ayarla)
ms.date: 02/06/2019
f1_keywords:
- execution-charset
- /execution-charset
helpviewer_keywords:
- /execution-charset compiler option
- -execution-charset compiler option
ms.assetid: 0e02f487-2236-45bc-95f3-5760933a8f96
ms.openlocfilehash: 38d17ba1d7e73fa337c81cc0c54f0053bfcff2ca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200825"
---
# <a name="execution-charset-set-execution-character-set"></a>/Execution-charset (yürütme karakter kümesini Ayarla)

Çalıştırılabilir için yürütme karakter kümesini belirtmenizi sağlar.

## <a name="syntax"></a>Söz dizimi

```
/execution-charset:[IANA_name|.CPID]
```

## <a name="arguments"></a>Bağımsız değişkenler

*IANA_name*<br/>
IANA tanımlı karakter kümesi adı.

*CPıD*<br/>
Kod sayfası tanımlayıcısı.

## <a name="remarks"></a>Açıklamalar

Bir yürütme karakter kümesi belirtmek için **/Execution-charset** seçeneğini kullanabilirsiniz. Yürütme karakter kümesi, programınızın tüm ön işleme adımlarındaki derleme aşamasına giriş olan programınızdaki metin için kullanılan kodlardır. Bu karakter kümesi, derlenmiş koddaki herhangi bir dizenin veya karakter sabit gösteriminin iç temsili için kullanılır. Kaynak dosyalarınız temel yürütme karakter kümesinde gösterilemeyen karakterler içermesi durumunda kullanılacak genişletilmiş yürütme karakter kümesini belirtmek için bu seçeneği ayarlayın. Kullanılacak karakter kümesini belirtmek için ıANA veya ISO karakter kümesi adını ya da bir nokta (.) ve arkasından 3 ile 5 basamaklı bir ondalık kod sayfası tanımlayıcısı kullanabilirsiniz. Desteklenen kod sayfası tanımlayıcılarının ve karakter kümesi adlarının listesi için bkz. [kod sayfası tanımlayıcıları](/windows/win32/Intl/code-page-identifiers).

Varsayılan olarak, Visual Studio, kaynak dosyanın kodlanmış bir Unicode biçiminde olup olmadığını (örneğin, UTF-16 veya UTF-8) belirlemekte kullanılacak bir bayt sıra işareti algılar. Herhangi bir bayt düzeni işareti bulunmazsa, **/Source-charset** seçeneğini veya **/UTF-8 belirtildiğinde** seçeneğini kullanarak bir karakter kümesi adı veya kod sayfası belirtmediğiniz müddetçe, kaynak dosyanın geçerli kullanıcı kodu sayfası kullanılarak kodlandığını varsayar. Visual Studio, birkaç karakter kodlamalarını kullanarak C++ kaynak kodunuzu kaydetmenizi sağlar. Kaynak ve yürütme karakter kümeleri hakkında bilgi için, dil belgelerindeki [karakter kümelerine](../../cpp/character-sets.md) bakın.

Hem kaynak karakter kümesini hem de yürütme karakter kümesini UTF-8 olarak ayarlamak istiyorsanız, **/UTF-8 belirtildiğinde** derleyici seçeneğini kısayol olarak kullanabilirsiniz. Komut satırında **/Source-charset: UTF-8/Execution-charset: UTF-8** belirtmeye eşdeğerdir. Bu seçeneklerden herhangi biri, varsayılan olarak **/Validate-charset** seçeneğini de etkinleştirmesine izin vermez.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**, **C/C++**, **komut satırı** klasörünü genişletin.

1. **Ek seçenekler**' de **/Execution-charset** seçeneğini ekleyin ve tercih ettiğiniz kodlamayı belirtin.

1. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)<br/>
[/Source-charset (kaynak karakter kümesini Ayarla)](source-charset-set-source-character-set.md)<br/>
[/UTF-8 belirtildiğinde (kaynak ve yürütülebilir karakter kümelerini UTF-8 olarak ayarla)](utf-8-set-source-and-executable-character-sets-to-utf-8.md)<br/>
[/validate-charset (Uyumlu karakterler için doğrula)](validate-charset-validate-for-compatible-characters.md)
