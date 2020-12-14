---
description: Şu konuda daha fazla bilgi edinin:/Validate-charset (uyumlu karakterler için Doğrula)
title: /validate-charset (Uyumlu karakterler için doğrula)
ms.date: 02/06/2019
f1_keywords:
- /validate-charset
- validate-charset
helpviewer_keywords:
- /validate-charset compiler option
ms.assetid: 50360fd0-4d32-4a4f-95d0-53d38c12ad4c
ms.openlocfilehash: bda69c59fc89aae5028543ba579ee1e0b70f67e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250406"
---
# <a name="validate-charset-validate-for-compatible-characters"></a>/validate-charset (Uyumlu karakterler için doğrula)

Kaynak dosya metninin UTF-8 olarak yalnızca karakter gösterilebilir tablo içerdiğini doğrular.

## <a name="syntax"></a>Syntax

```
/validate-charset[-]
```

## <a name="remarks"></a>Açıklamalar

Kaynak kodun yalnızca kaynak karakter kümesinde ve yürütme karakter kümesinde gösterilebilen karakterleri içerdiğini doğrulamak için **/Validate-charset** seçeneğini kullanabilirsiniz. **/Source-charset**, **/Execution-charset** veya **/UTF-8 belirtildiğinde** derleyici seçeneklerini belirttiğinizde bu denetim otomatik olarak etkinleştirilir. **/Validate-charset-** seçeneğini belirterek bu denetimi açıkça devre dışı bırakabilirsiniz.

Varsayılan olarak, Visual Studio, kaynak dosyanın kodlanmış bir Unicode biçiminde olup olmadığını (örneğin, UTF-16 veya UTF-8) belirlemekte kullanılacak bir bayt sıra işareti algılar. Herhangi bir bayt düzeni işareti bulunmazsa, **/UTF-8 belirtildiğinde** veya **/Source-charset** seçeneğini kullanarak bir kod sayfası belirtmediğiniz müddetçe, kaynak dosyanın geçerli kullanıcı kodu sayfası kullanılarak kodlandığını varsayar. Visual Studio, birkaç karakter kodlamalarını kullanarak C++ kaynak kodunuzu kaydetmenizi sağlar. Kaynak ve yürütme karakter kümeleri hakkında bilgi için, dil belgelerindeki [karakter kümelerine](../../cpp/character-sets.md) bakın. Desteklenen kod sayfası tanımlayıcılarının ve karakter kümesi adlarının listesi için bkz. [kod sayfası tanımlayıcıları](/windows/win32/Intl/code-page-identifiers).

Visual Studio, kaynak karakter kümesi ve yürütme karakter kümesi arasında dönüştürme sırasında iç karakter kodlaması olarak UTF-8 ' i kullanır. Kaynak dosyadaki bir karakter yürütme karakter kümesi içinde temsil edilemez, UTF-8 dönüştürmesi bir soru işareti '? ' karakteri koyar. **/Validate-charset** seçeneği, derlemenin bir uyarı raporlamasına neden olur.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**, **C/C++**, **komut satırı** klasörünü genişletin.

1. **Ek seçenekler**' de **/Validate-charset** seçeneğini ekleyin ve tercih ettiğiniz kodlamayı belirtin.

1. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)<br/>
[/Execution-charset (yürütme karakter kümesini Ayarla)](execution-charset-set-execution-character-set.md)<br/>
[/Source-charset (kaynak karakter kümesini Ayarla)](source-charset-set-source-character-set.md)<br/>
[/UTF-8 belirtildiğinde (kaynak ve yürütülebilir karakter kümelerini UTF-8 olarak ayarla)](utf-8-set-source-and-executable-character-sets-to-utf-8.md)
