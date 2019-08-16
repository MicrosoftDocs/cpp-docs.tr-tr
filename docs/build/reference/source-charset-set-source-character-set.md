---
title: /Source-charset (kaynak karakter kümesini Ayarla)
ms.date: 02/06/2019
f1_keywords:
- source-charset
- /source-charset
helpviewer_keywords:
- /execution-charset compiler option
ms.assetid: d3c5bf7f-526d-4ee4-acc5-c1a02a4fc481
ms.openlocfilehash: cd3e4eb3fd305ba6bdd298d18b1edb80f2b98343
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498250"
---
# <a name="source-charset-set-source-character-set"></a>/Source-charset (kaynak karakter kümesini Ayarla)

Çalıştırılabilir için kaynak karakter kümesini belirtmenizi sağlar.

## <a name="syntax"></a>Sözdizimi

```
/source-charset:[IANA_name|.CPID]
```

## <a name="arguments"></a>Arguments

**IANA_name**<br/>
IANA tanımlı karakter kümesi adı.

**CPID**<br/>
Kod sayfası tanımlayıcısı, ondalık sayı olarak.

## <a name="remarks"></a>Açıklamalar

Kaynak dosyalarınız temel kaynak karakter kümesinde temsil edilmeyen karakterler içermesi durumunda kullanılacak bir genişletilmiş kaynak karakter kümesi belirtmek için **/Source-charset** seçeneğini kullanabilirsiniz. Kaynak karakter kümesi, programınızın kaynak metnini, derlemeden önce ön işleme aşamalarına girdi olarak kullanılan iç gösterimiyle yorumlamak için kullanılan kodlamadır. İç gösterim daha sonra, çalıştırılabilir dosyada dize ve karakter değerlerini depolamak için yürütme karakter kümesine dönüştürülür. Kullanılacak karakter kümesini belirtmek için ıANA veya ISO karakter kümesi adını ya da bir nokta (.) ve arkasından 3 ile 5 basamaklı bir ondalık kod sayfası tanımlayıcısı kullanabilirsiniz. Desteklenen kod sayfası tanımlayıcılarının ve karakter kümesi adlarının listesi için bkz. [kod sayfası tanımlayıcıları](/windows/win32/Intl/code-page-identifiers).

Varsayılan olarak, Visual Studio, kaynak dosyanın kodlanmış bir Unicode biçiminde olup olmadığını (örneğin, UTF-16 veya UTF-8) belirlemekte kullanılacak bir bayt sıra işareti algılar. Herhangi bir bayt düzeni işareti bulunmazsa, **/Source-charset** seçeneğini kullanarak bir karakter kümesi adı veya kod sayfası belirtmediğiniz müddetçe, kaynak dosyanın geçerli kullanıcı kodu sayfası kullanılarak kodlandığını varsayar. Visual Studio, birkaç karakter kodlamalarını C++ kullanarak kaynak kodunuzu kaydetmenizi sağlar. Kaynak ve yürütme karakter kümeleri hakkında daha fazla bilgi için, dil belgelerindeki [karakter kümelerine](../../cpp/character-sets.md) bakın.

Sağladığınız kaynak karakter kümesi, 7 bit ASCII karakter kümesini karakter kümesi içindeki aynı kod noktalarına eşlenmelidir veya çok sayıda derleme hatası olabilir. Kaynak karakter kümesi aynı zamanda UTF-8 ile kodlenebilir genişletilmiş Unicode karakter kümesine eşlenebilir olmalıdır. UTF-8 içinde kodlenebilir olmayan karakterler uygulamaya özgü bir değiştirme ile temsil edilir. Microsoft derleyicisi, bu karakterler için bir soru işareti kullanır.

Hem kaynak karakter kümesini hem de yürütme karakter kümesini UTF-8 olarak ayarlamak istiyorsanız, **/UTF-8 belirtildiğinde** derleyici seçeneğini kısayol olarak kullanabilirsiniz. Komut satırında **/Source-charset: UTF-8/Execution-charset: UTF-8** belirtmeye eşdeğerdir. Bu seçeneklerden herhangi biri, varsayılan olarak **/Validate-charset** seçeneğini de etkinleştirmesine izin vermez.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz [. C++ Visual Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**, **CC++/** , **komut satırı** klasörünü genişletin.

1. **Ek seçenekler**' de **/Source-charset** seçeneğini ekleyin ve tercih ettiğiniz kodlamayı belirtin.

1. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[/Execution-charset (yürütme karakter kümesini Ayarla)](execution-charset-set-execution-character-set.md)<br/>
[/utf-8 (Kaynak ve Yürütülebilir karakter kümelerini UTF-8 olarak ayarla)](utf-8-set-source-and-executable-character-sets-to-utf-8.md)<br/>
[/validate-charset (Uyumlu karakterler için doğrula)](validate-charset-validate-for-compatible-characters.md)
