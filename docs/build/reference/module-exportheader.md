---
title: '/Module: exportHeader (üst bilgi birimleri oluştur)'
description: 'Belirtilen üst bilgi adı veya içerme dosyaları için modül üst birimleri oluşturmak üzere/Module: exportHeader derleyici seçeneğini kullanın.'
ms.date: 09/13/2020
f1_keywords:
- /module:exportHeader
helpviewer_keywords:
- /module:exportHeader
- Create header units
ms.openlocfilehash: f0c0ce1c593df742af77aa36189df1e89de75b6b
ms.sourcegitcommit: b492516cc65120250b9ea23f96f7f63f37f99fae
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2020
ms.locfileid: "90079112"
---
# <a name="moduleexportheader-create-header-units"></a>`/module:exportHeader` (Üst bilgi birimleri oluştur)

Derleyiciye giriş bağımsız değişkenleri tarafından belirtilen başlık birimlerini oluşturmasını söyler. Derleyici IFC () dosyalarında çıktı oluşturur *`.ifc`* .

## <a name="syntax"></a>Syntax

> **`/module:exportHeader`** *`header-name`* \[...]\
> **`/module:exportHeader`** *`filename`* \[...]

### <a name="arguments"></a>Arguments

*`header-name`*\
Dışarı aktarılacak üstbilgi dosyası. *`header-name`* Bağımsız değişken, bir yönerge için bağımsız değişkenle aynı formu almalıdır `#include` .

*`filename`*\
Öğesinden bir başlık birimi oluşturmak için üst bilgi dosyasının göreli veya mutlak yolu.

## <a name="remarks"></a>Açıklamalar

**`/module:exportHeader`** Derleyici seçeneği [`/experimental:module`](experimental-module.md) , derleyici seçeneğini kullanarak [/std: c + + en son](std-specify-language-standard-version.md) seçeneğiyle birlikte deneysel modüller desteğini etkinleştirmenizi gerektirir. Bu seçenek, Visual Studio 2019 sürüm 16,8 ' den itibaren kullanılabilir.

Tek **`/module:exportHeader`** derleyici seçeneği, derlemeniz için gereken sayıda üst bilgi-ad bağımsız değişkeni belirtebilir. Bunları ayrı belirtmeniz gerekmez.

Varsayılan olarak, derleyici bir üstbilgi birimi derlendiğinde bir nesne dosyası oluşturmaz. Bir nesne dosyası oluşturmak için **`/Fo`** derleyici seçeneğini belirtin. Daha fazla bilgi için bkz. [ `/Fo` (nesne dosyası adı)](fo-object-file-name.md).

Derleyici, *`header-name`* belirttiğiniz her türlü dahil olmak üzere, içerme dizini arama sırasına göre bir, çözer. Daha fazla bilgi için bkz. [ `/I` (ek ekleme dizinleri)](i-additional-include-directories.md).

Bağımsız değişken, *`header-name`* kaynakta göründüğü şekilde belirtilmelidir. Bağımsız değişken, `<` komut satırındaki ve ve işleçlerinin tırnak içine alınmasına duyarlıdır `>` . VS2019 komut istemi kullanımı gibi bir üst bilgi birimi oluşturmak için doğru kaçış komutu `<vector>` şöyle görünebilir:

```cmd
cl ... /experimental:module /module:exportHeader "<vector>"
```

Gibi yerel bir proje üst bilgisi oluşturmak `"utils/util.h"` şöyle görünebilir:

```cmd
cl ... /experimental:module /module:exportHeader """util/util.h"""
```

Diğer komut satırı işlemcilerinde alıntı kuralları farklı olabilir.

*`header-name`* Formunu kullanırken **`/module:exportHeader`** , tamamlayıcı seçeneğini kullanmanın yararlı olduğunu fark edebilirsiniz **`/module:showResolvedHeader`** . **`/module:showResolvedHeader`** Seçeneği, *`header-name`* bağımsız değişkenin çözümlendiğini dosyaya mutlak bir yol yazdırır.

**`/module:exportHeader`** , altında bile birden çok girişi aynı anda işleyebilir **`/MP`** . **`/module:output <directory>`** Her derleme için ayrı bır ıFC dosyası oluşturmak için kullanmanızı öneririz.

### <a name="examples"></a>Örnekler

Verilen üstbilgiler `"C:\util\util.h"` ve `"C:\app\app.h"` , *`header-name`* Bu komutu kullanarak bunları bağımsız değişken olarak dışarı aktarabilirsiniz:

```cmd
cl /IC:\ /experimental:module /module:exportHeader """util/util.h""" """app/app.h""" /FoC:\obj
```

*`filename`* Bu komutu kullanarak bunları bağımsız değişken olarak dışarı aktarabilirsiniz:

```cmd
cl /IC:\ /experimental:module /module:exportHeader C:\util\util.h C:\app\app.h /FoC:\obj
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. Yapılandırma açılan **öğesini** **Tüm yapılandırmalara**ayarlayın.

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. Seçenek ve herhangi bir bağımsız değişken eklemek için **ek seçenekler** özelliğini değiştirin *`/module:exportHeader`* . Sonra, değişikliklerinizi kaydetmek için **Tamam** ' ı veya **Uygula** ' yı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[`/experimental:module` (Modül desteğini etkinleştir)](experimental-module.md)\
[`/headerUnit` (IBC başlık birimini kullan)](headerunit.md)\
[`/module:reference` (Adlandırılmış modül ıFC kullanın)](module-reference.md)\
[`/translateInclude` (İçeri aktarma yönergeleri içine çeviri ekleme yönergeleri)](translateinclude.md)
