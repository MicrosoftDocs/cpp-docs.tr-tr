---
title: /Execution-charset (yürütme karakter kümesini Ayarla)
ms.date: 02/06/2019
f1_keywords:
- execution-charset
- /execution-charset
helpviewer_keywords:
- /execution-charset compiler option
- -execution-charset compiler option
ms.assetid: 0e02f487-2236-45bc-95f3-5760933a8f96
ms.openlocfilehash: 44e83524867bc8a914706e1f5b45b61bc4a48087
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492910"
---
# <a name="execution-charset-set-execution-character-set"></a>/Execution-charset (yürütme karakter kümesini Ayarla)

Çalıştırılabilir için yürütme karakter kümesini belirtmenizi sağlar.

## <a name="syntax"></a>Sözdizimi

```
/execution-charset:[IANA_name|.CPID]
```

## <a name="arguments"></a>Arguments

*IANA_name*<br/>
IANA tanımlı karakter kümesi adı.

*CPID*<br/>
Kod sayfası tanımlayıcısı.

## <a name="remarks"></a>Açıklamalar

Bir yürütme karakter kümesi belirtmek için **/Execution-charset** seçeneğini kullanabilirsiniz. Yürütme karakter kümesi, programınızın tüm ön işleme adımlarındaki derleme aşamasına giriş olan programınızdaki metin için kullanılan kodlardır. Bu karakter kümesi, derlenmiş koddaki herhangi bir dizenin veya karakter sabit gösteriminin iç temsili için kullanılır. Kaynak dosyalarınız temel yürütme karakter kümesinde gösterilemeyen karakterler içermesi durumunda kullanılacak genişletilmiş yürütme karakter kümesini belirtmek için bu seçeneği ayarlayın. Kullanılacak karakter kümesini belirtmek için ıANA veya ISO karakter kümesi adını ya da bir nokta (.) ve arkasından 3 ile 5 basamaklı bir ondalık kod sayfası tanımlayıcısı kullanabilirsiniz. Desteklenen kod sayfası tanımlayıcılarının ve karakter kümesi adlarının listesi için bkz. [kod sayfası tanımlayıcıları](/windows/win32/Intl/code-page-identifiers).

Varsayılan olarak, Visual Studio, kaynak dosyanın kodlanmış bir Unicode biçiminde olup olmadığını (örneğin, UTF-16 veya UTF-8) belirlemekte kullanılacak bir bayt sıra işareti algılar. Herhangi bir bayt düzeni işareti bulunmazsa, **/Source-charset** seçeneğini veya **/UTF-8 belirtildiğinde** seçeneğini kullanarak bir karakter kümesi adı veya kod sayfası belirtmediğiniz müddetçe, kaynak dosyanın geçerli kullanıcı kodu sayfası kullanılarak kodlandığını varsayar. Visual Studio, birkaç karakter kodlamalarını C++ kullanarak kaynak kodunuzu kaydetmenizi sağlar. Kaynak ve yürütme karakter kümeleri hakkında bilgi için, dil belgelerindeki [karakter kümelerine](../../cpp/character-sets.md) bakın.

Hem kaynak karakter kümesini hem de yürütme karakter kümesini UTF-8 olarak ayarlamak istiyorsanız, **/UTF-8 belirtildiğinde** derleyici seçeneğini kısayol olarak kullanabilirsiniz. Komut satırında **/Source-charset: UTF-8/Execution-charset: UTF-8** belirtmeye eşdeğerdir. Bu seçeneklerden herhangi biri, varsayılan olarak **/Validate-charset** seçeneğini de etkinleştirmesine izin vermez.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz [. C++ Visual Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**, **CC++/** , **komut satırı** klasörünü genişletin.

1. **Ek seçenekler**' de **/Execution-charset** seçeneğini ekleyin ve tercih ettiğiniz kodlamayı belirtin.

1. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[/source-charset (Kaynak Karakter Kümesini Ayarla)](source-charset-set-source-character-set.md)<br/>
[/utf-8 (Kaynak ve Yürütülebilir karakter kümelerini UTF-8 olarak ayarla)](utf-8-set-source-and-executable-character-sets-to-utf-8.md)<br/>
[/validate-charset (Uyumlu karakterler için doğrula)](validate-charset-validate-for-compatible-characters.md)
