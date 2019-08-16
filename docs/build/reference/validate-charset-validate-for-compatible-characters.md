---
title: /validate-charset (Uyumlu karakterler için doğrula)
ms.date: 02/06/2019
f1_keywords:
- /validate-charset
- validate-charset
helpviewer_keywords:
- /validate-charset compiler option
ms.assetid: 50360fd0-4d32-4a4f-95d0-53d38c12ad4c
ms.openlocfilehash: 2390aa98b9416eb538f529c8c370c888cccf4734
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498167"
---
# <a name="validate-charset-validate-for-compatible-characters"></a>/validate-charset (Uyumlu karakterler için doğrula)

Kaynak dosya metninin UTF-8 olarak yalnızca karakter gösterilebilir tablo içerdiğini doğrular.

## <a name="syntax"></a>Sözdizimi

```
/validate-charset[-]
```

## <a name="remarks"></a>Açıklamalar

Kaynak kodun yalnızca kaynak karakter kümesinde ve yürütme karakter kümesinde gösterilebilen karakterleri içerdiğini doğrulamak için **/Validate-charset** seçeneğini kullanabilirsiniz. **/Source-charset**, **/Execution-charset**veya **/UTF-8 belirtildiğinde** derleyici seçeneklerini belirttiğinizde bu denetim otomatik olarak etkinleştirilir. **/Validate-charset-** seçeneğini belirterek bu denetimi açıkça devre dışı bırakabilirsiniz.

Varsayılan olarak, Visual Studio, kaynak dosyanın kodlanmış bir Unicode biçiminde olup olmadığını (örneğin, UTF-16 veya UTF-8) belirlemekte kullanılacak bir bayt sıra işareti algılar. Herhangi bir bayt düzeni işareti bulunmazsa, **/UTF-8 belirtildiğinde** veya **/Source-charset** seçeneğini kullanarak bir kod sayfası belirtmediğiniz müddetçe, kaynak dosyanın geçerli kullanıcı kodu sayfası kullanılarak kodlandığını varsayar. Visual Studio, birkaç karakter kodlamalarını C++ kullanarak kaynak kodunuzu kaydetmenizi sağlar. Kaynak ve yürütme karakter kümeleri hakkında bilgi için, dil belgelerindeki [karakter kümelerine](../../cpp/character-sets.md) bakın. Desteklenen kod sayfası tanımlayıcılarının ve karakter kümesi adlarının listesi için bkz. [kod sayfası tanımlayıcıları](/windows/win32/Intl/code-page-identifiers).

Visual Studio, kaynak karakter kümesi ve yürütme karakter kümesi arasında dönüştürme sırasında iç karakter kodlaması olarak UTF-8 ' i kullanır. Kaynak dosyadaki bir karakter yürütme karakter kümesi içinde temsil edilemez, UTF-8 dönüştürmesi bir soru işareti '? ' karakteri koyar. **/Validate-charset** seçeneği, derlemenin bir uyarı raporlamasına neden olur.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz [. C++ Visual Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**, **CC++/** , **komut satırı** klasörünü genişletin.

1. **Ek seçenekler**' de **/Validate-charset** seçeneğini ekleyin ve tercih ettiğiniz kodlamayı belirtin.

1. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[/Execution-charset (yürütme karakter kümesini Ayarla)](execution-charset-set-execution-character-set.md)<br/>
[/source-charset (Kaynak Karakter Kümesini Ayarla)](source-charset-set-source-character-set.md)<br/>
[/utf-8 (Kaynak ve Yürütülebilir karakter kümelerini UTF-8 olarak ayarla)](utf-8-set-source-and-executable-character-sets-to-utf-8.md)
