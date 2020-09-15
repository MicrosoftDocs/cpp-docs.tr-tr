---
title: /translateInclude (içeri aktarma yönergeleri içine çeviri dahil)
description: 'Importable üst bilgisi için #include yönergelerini içeri aktarma üst bilgisi-adı yönergesine çevirmek için/Translateınclude derleyici seçeneğini kullanın.'
ms.date: 09/13/2020
f1_keywords:
- /translateInclude
helpviewer_keywords:
- /translateInclude
- Translate include directives into import directives
ms.openlocfilehash: 0050f2cb117e48d69cf97a587ef128b9b45790af
ms.sourcegitcommit: b492516cc65120250b9ea23f96f7f63f37f99fae
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2020
ms.locfileid: "90079111"
---
# <a name="translateinclude-translate-include-directives-into-import-directives"></a>`/translateInclude` (İçeri aktarma yönergeleri içine çeviri ekleme yönergeleri)

Derleyiciye, `#include` `import header-name;` metin ekleme kullanmak yerine, Importable üst bilgisi için yönergeleri bir yönergeye çevirmesini söyler.

## <a name="syntax"></a>Syntax

> **`/translateInclude`**

## <a name="remarks"></a>Açıklamalar

**`/translateInclude`** Derleyici seçeneği [`/experimental:module`](experimental-module.md) , derleyici seçeneğini kullanarak [/std: c + + en son](std-specify-language-standard-version.md) seçeneğiyle birlikte deneysel modüller desteğini etkinleştirmenizi gerektirir. Bu seçenek, Visual Studio 2019 sürüm 16,8 ' den itibaren kullanılabilir.

**`/translateInclude`** Bu seçenek, örneğin `<vector>` bir Importable başlık birimi olduğu durumlarda aşağıdaki dönüşümü etkin hale getirir:

```cpp
#include <vector>
```

Derleyici bu yönergeyi ile değiştirir:

```cpp
import <vector> ;
```

MSVC içinde, Importable başlık birimi bir başvuruya göre adlandırılmaktadır **`/headerUnit`** . Daha fazla bilgi için bkz. [ `/headerUnit` (IBC başlık birimini kullanın)](headerunit.md).

### <a name="examples"></a>Örnekler

İki üstbilgi dosyasına ve bu tabloda listelenen üst bilgi birimlerine başvuran bir proje verildi:

| Üst bilgi dosyası | IFC dosyası |
|--|--|
| *`C:\utils\util.h`* | *`C:\util.h.ifc`* |
| *`C:\app\app.h`* | *`C:\app.h.ifc`* |

Ve üst bilgileri içeren bir kaynak *`.cpp`* Dosya,

```cpp
#include "utils/util.h"
#include "app/app.h"

int main() { }
```

**`/translateInclude`** Seçeneği, derleyicinin üstbilgileri yeniden derlemek yerine üst bilgi birimlerini içeri aktarmasını sağlar. *`util.h`* *`app.h`* Bunun yerine, üst bilgi birimlerinin içeri aktarmalarını ve içine dahil etme yönergelerini çeviren örnek bir komut satırı aşağıda verilmiştir:

```CMD
cl /IC:\ /experimental:module /translateInclude /headerUnit C:\utils\util.h=C:\util.h.ifc /headerUnit C:\app\app.h=C:\app.h.ifc
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. Yapılandırma açılan **öğesini** **Tüm yapılandırmalara**ayarlayın.

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. Seçeneği eklemek için **ek seçenekler** özelliğini değiştirin *`/translateInclude`* . Sonra, değişikliklerinizi kaydetmek için **Tamam** ' ı veya **Uygula** ' yı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[`/experimental:module` (Modül desteğini etkinleştir)](experimental-module.md)\
[ `/headerUnit` (IBC başlık birimini kullanın)](headerunit.md). \
[`/module:exportHeader` (Üst bilgi birimleri oluştur)](module-exportheader.md)\
[`/module:reference` (Adlandırılmış modül ıFC kullanın)](module-reference.md)
