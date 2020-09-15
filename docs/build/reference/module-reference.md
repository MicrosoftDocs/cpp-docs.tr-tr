---
title: '/Module: Reference (adlandırılmış modül ıFC kullanın)'
description: 'Belirtilen üst bilgi adı veya içerme dosyaları için modül üst birimleri oluşturmak üzere/Module: Reference derleyici seçeneğini kullanın.'
ms.date: 09/13/2020
f1_keywords:
- /module:reference
helpviewer_keywords:
- /module:reference
- Use named module IFC
ms.openlocfilehash: 5f40f6b700c38f3238cc7a621313621085fbc289
ms.sourcegitcommit: b492516cc65120250b9ea23f96f7f63f37f99fae
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2020
ms.locfileid: "90079116"
---
# <a name="modulereference-use-named-module-ifc"></a>`/module:reference` (Adlandırılmış modül ıFC kullanın)

Derleyiciye geçerli derleme için mevcut bir IFC () kullanmasını söyler *`.ifc`* .

## <a name="syntax"></a>Syntax

> **`/module:reference`** *`module-name=filename`*\
> **`/module:reference`** *`filename`*

### <a name="arguments"></a>Arguments

*`filename`*\
*IFC verisi*, önceden oluşturulmuş modül bilgilerini içeren dosyanın adı. Birden fazla modülün içeri aktarılması için, **`/module:reference`** her bir dosya için ayrı bir seçenek ekleyin.

*`module-name`*\
Dışarıya aktarılmış birincil modül arabirimi birimi adı veya tam modül bölümü adı için geçerli bir ad.

## <a name="remarks"></a>Açıklamalar

**`/module:reference`** Derleyici seçeneği [`/experimental:module`](experimental-module.md) , derleyici seçeneğini kullanarak [/std: c + + en son](std-specify-language-standard-version.md) seçeneğiyle birlikte deneysel modüller desteğini etkinleştirmenizi gerektirir. Bu seçenek, Visual Studio 2019 sürüm 16,8 ' den itibaren kullanılabilir.

**`/module:reference`** Bağımsız değişken *`filename`* bir olmadan ise *`module-name`* , *`filename`* belirli bir içeri aktarma bağımsız değişken adlarını doğrulamak için dosya çalışma zamanında açılır. Çok sayıda bağımsız değişkene sahip senaryolarda, daha yavaş çalışma zamanı performansına neden olabilir **`/module:reference`** .

*`module-name`* Geçerli bir birincil modül arabirimi birim adı veya tam modül bölüm adı olmalıdır. Birincil modül arabirimi adlarına örnek olarak şunlar verilebilir:

- `M`
- `M.N.O`
- `MyModule`
- `my_module`

Tam modül bölümü adlarına örnek olarak şunlar verilebilir:

- `M:P`
- `M.N.O:P.Q`
- `MyModule:Algorithms`
- `my_module:algorithms`

Bir modül başvurusu kullanılarak oluşturulduysa *`module-name`* , derleyici bu adı içeri aktarmaya karşılaştığında komut satırındaki diğer modüller aranmaz. Örneğin, şu komut satırı verildiğinde:

```cmd
cl ... /experimental:module /module:reference m.ifc /module:reference m=n.ifc
```

Yukarıdaki durumda, derleyici `import m;` daha sonra *`m.ifc`* görümezse aranmaz.

### <a name="examples"></a>Örnekler

Bu tabloda listelenen üç modül verilmiştir:

| Modül | IFC dosyası |
|--|--|
| *`M`* | *`m.ifc`* |
| *`M:Part1`* | *`m-part1.ifc`* |
| *`Core.Networking`* | *`Networking.ifc`* |

Bağımsız değişken kullanan başvuru seçenekleri *`filename`* şöyle görünebilir:

```cmd
cl ... /experimental:module /module:reference m.ifc /module:reference m-part.ifc /module:reference Networking.ifc
```

Kullanarak başvuru seçenekleri *`module-name=filename`* şöyle görünebilir:

```cmd
cl ... /experimental:module /module:reference m=m.ifc /module:reference M:Part1=m-part.ifc /module:reference Core.Networking=Networking.ifc
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. Yapılandırma açılan **öğesini** **Tüm yapılandırmalara**ayarlayın.

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. Seçenek ve bağımsız değişkenlerini eklemek için **ek seçenekler** özelliğini değiştirin *`/module:reference`* . Sonra, değişikliklerinizi kaydetmek için **Tamam** ' ı veya **Uygula** ' yı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[`/experimental:module` (Modül desteğini etkinleştir)](experimental-module.md)\
[`/headerUnit` (IBC başlık birimini kullan)](headerunit.md)\
[`/module:exportHeader` (Üst bilgi birimleri oluştur)](module-exportheader.md)\
[`/translateInclude` (İçeri aktarma yönergeleri içine çeviri ekleme yönergeleri)](translateinclude.md)
