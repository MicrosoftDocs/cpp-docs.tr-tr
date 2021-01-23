---
description: pragmaMicrosoft C/C++ içindeki bileşen yönergesi hakkında daha fazla bilgi edinin
title: bileşeninde pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.component
- component_CPP
helpviewer_keywords:
- component pragma
- pragma, component
no-loc:
- pragma
ms.openlocfilehash: 68a4117439390c6ec978ae9d766efb395a4ceaa4
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712953"
---
# <a name="component-no-locpragma"></a>`component` pragma

Kaynak dosyalardan gelen tarayıcı bilgileri veya bağımlılık bilgileri koleksiyonunu denetler.

## <a name="syntax"></a>Syntax

> **`#pragma component( browser,`** { **`on`** \| **`off`** } \[ **`,`** **`references`** \[ **`,`** *ad* ]] **`)`** \
> **`#pragma component( minrebuild,`** { **`on`** \| **`off`** } **`)`** \
> **`#pragma component( mintypeinfo,`** { **`on`** \| **`off`** } **`)`**

## <a name="remarks"></a>Açıklamalar

### <a name="browser"></a>Tarayıcı

Toplama işlemini açıp kapatabilir ve bilgiler toplanırken dikkate alınmayacak adları belirtebilirsiniz.

Açık veya kapalı ' nın kullanımı, ileriye doğru olan gezinme bilgileri koleksiyonunu denetler pragma . Örneğin:

```cpp
#pragma component(browser, off)
```

Derleyicinin gözatma bilgilerini toplamasını durdurur.

> [!NOTE]
> Bu ile ilgili tarama bilgilerinin toplanmasını etkinleştirmek için pragma , [önce tarama bilgilerinin etkinleştirilmesi gerekir](../build/reference/building-browse-information-files-overview.md).

**`references`** Seçeneği, *ad* bağımsız değişkeniyle birlikte veya olmadan kullanılabilir. **`references`** *Ad* olmadan kullanmak, başvuruların toplanması için açık veya kapalı olur (diğer tarama bilgileri toplanmaya devam eder, ancak). Örneğin:

```cpp
#pragma component(browser, off, references)
```

Derleyicinin başvuru bilgilerini toplama işlemini durdurur.

**`references`** *Adı* ile kullanarak ve **`off`** ' ın, tarama bilgileri penceresinde görünen *ad* başvurularını önler. İlgilenmediğiniz adları ve türleri gözardı etmek ve gözatma bilgisi dosyalarının boyutunu küçültmek için bu sözdizimini kullanın. Örneğin:

```cpp
#pragma component(browser, off, references, DWORD)
```

Bu noktadan sonra gelen DWORD başvurularını yoksayar. Kullanarak DWORD için başvuruların toplanmasını yeniden açabilirsiniz **`on`** :

```cpp
#pragma component(browser, on, references, DWORD)
```

Bu, *ad* ile başvuruları toplamayı sürdürmenin tek yoludur; kapattığınız bir *adı* açık olarak açmanız gerekir.

Önişlemci 'nin *adı* genişletmesinin (null değeri 0 ' a genişletme gibi) engellemek için, tırnak içine alın:

```cpp
#pragma component(browser, off, references, "NULL")
```

### <a name="minimal-rebuild"></a>En az yeniden derleme

Kullanım dışı [ `/Gm` (en az yeniden derlemeyi etkinleştir)](../build/reference/gm-enable-minimal-rebuild.md) özelliği, derleyicinin, disk alanı alan ve C++ sınıf bağımlılığı bilgilerini oluşturmasını ve depolamasını gerektirir. Disk alanından tasarruf etmek için, örneğin `#pragma component( minrebuild, off )` değişiklik olmayan başlık dosyalarında bağımlılık bilgilerini toplamanız gerektiğinde ' yi kullanabilirsiniz. `#pragma component( minrebuild, on )`Bağımlılık toplamayı yeniden açmak için sınıfların değiştirilmesini kaldırdıktan sonra Ekle.

### <a name="reduce-type-information"></a>Tür bilgilerini azaltma

**`mintypeinfo`** Seçeneği belirtilen bölge için hata ayıklama bilgilerini azaltır. Bu bilgilerin hacmi epey büyüktür; .pdb ve .obj dosyalarını etkiler. Bölgedeki sınıfların ve yapıların hatalarını ayıklayamazsınız **`mintypeinfo`** . Seçeneğinin kullanılması, **`mintypeinfo`** aşağıdaki uyarıyı önlemek için yararlı olabilir:

```cmd
LINK : warning LNK4018: too many type indexes in PDB "filename", discarding subsequent type information
```

Daha fazla bilgi için bkz. [ `/Gm` (en düşük yeniden derlemeyi etkinleştir)](../build/reference/gm-enable-minimal-rebuild.md) derleyici seçeneği.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
