---
title: /headerUnit (ıBC başlık birimini kullanın)
description: Geçerli derlemede içeri aktarılacak mevcut bir ıBC üst bilgi birimini belirtmek için/headerUnit derleyici seçeneğini kullanın.
ms.date: 09/13/2020
f1_keywords:
- /headerUnit
helpviewer_keywords:
- /headerUnit
- Use header unit IFC
ms.openlocfilehash: 2734df728b188dcfbbe5f475cfc67715a070975d
ms.sourcegitcommit: b492516cc65120250b9ea23f96f7f63f37f99fae
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2020
ms.locfileid: "90079120"
---
# <a name="headerunit-use-header-unit-ifc"></a>`/headerUnit` (IBC başlık birimini kullan)

Derleyiciye, `#include` `import header-name;` metin ekleme kullanmak yerine, Importable üst bilgisi için yönergeleri bir yönergeye çevirmesini söyler.

## <a name="syntax"></a>Syntax

> **`/headerUnit`** *`header-filename`*=*`ifc-filename`*

### <a name="arguments"></a>Arguments

*`header-filename`*\
Derleyicinin ' a çözümleyen dosyanın adı `header-name` . `import header-name ;`Derleyici sırasında `header-name` disk üzerindeki bir dosyayı çözer. *`header-filename`* Bu dosyayı belirtmek için kullanın. Bir kez eşleştirdikten sonra derleyici, içeri aktarma için adlı ilgili IFC 'yi açar *`ifc-filename`* .

*`ifc-filename`*\
*IFC verisi*, önceden oluşturulmuş modül bilgilerini içeren dosyanın adı. Birden fazla üstbilgi birimini içeri aktarmak için **`/headerUnit`** her bir dosya için ayrı bir seçenek ekleyin.

## <a name="remarks"></a>Açıklamalar

**`/headerUnit`** Derleyici seçeneği [`/experimental:module`](experimental-module.md) , derleyici seçeneğini kullanarak [/std: c + + en son](std-specify-language-standard-version.md) seçeneğiyle birlikte deneysel modüller desteğini etkinleştirmenizi gerektirir. Bu seçenek, Visual Studio 2019 sürüm 16,8 ' den itibaren kullanılabilir.

Derleyici, tek bir *`header-name`* ile birden çok IFC dosyası arasında eşleme yapamıyor. Birden çok *`header-name`* bağımsız değişkeni tek BIR IFC ile eşleştirirken, bunu önermiyoruz. IFC Get 'in içeriği, yalnızca tarafından belirtilen üst bilgi olarak içeri aktarılır *`header-name`* .

### <a name="examples"></a>Örnekler

İki üstbilgi dosyasına ve bu tabloda listelenen üst bilgi birimlerine başvuran bir proje verildi:

| Üst bilgi dosyası | IFC dosyası |
|--|--|
| *`C:\utils\util.h`* | *`C:\util.h.ifc`* |
| *`C:\app\app.h`* | *`C:\app.h.ifc`* |

Bu belirli üstbilgi dosyaları için üst bilgi birimlerine başvurmak üzere derleyici seçenekleri şu örnekteki gibi görünebilir:

```CMD
cl ... /experimental:module /translateInclude /headerUnit C:\utils\util.h=C:\util.h.ifc /headerUnit C:\app\app.h=C:\app.h.ifc
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. Yapılandırma açılan **öğesini** **Tüm yapılandırmalara**ayarlayın.

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. Seçenekleri ve bağımsız değişkenleri eklemek için **ek seçenekler** özelliğini değiştirin *`/headerUnit`* . Sonra, değişikliklerinizi kaydetmek için **Tamam** ' ı veya **Uygula** ' yı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[`/experimental:module` (Modül desteğini etkinleştir)](experimental-module.md)\
[`/module:exportHeader` (Üst bilgi birimleri oluştur)](module-exportheader.md)\
[`/module:reference` (Adlandırılmış modül ıFC kullanın)](module-reference.md)\
[`/translateInclude` (İçeri aktarma yönergeleri içine çeviri ekleme yönergeleri)](translateinclude.md)\
