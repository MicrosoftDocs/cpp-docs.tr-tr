---
title: bileşen pragması
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.component
- component_CPP
helpviewer_keywords:
- component pragma
- pragmas, component
ms.assetid: 7b66355e-3201-4c14-8190-f4a2a81a604a
ms.openlocfilehash: 73b308fdc426be9b403b808d4e638b4f5c1e9149
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040736"
---
# <a name="component-pragma"></a>bileşen pragması

Kaynak dosyalardan gelen tarayıcı bilgileri veya bağımlılık bilgileri koleksiyonunu denetler.

## <a name="syntax"></a>Syntax

> **#pragma bileşeni (tarayıcı,** { **on** \| **off** } \[ **,** **Başvurular** \[ **,** *ad* ]] **)** \
> **#pragma bileşeni (mini yeniden oluşturma,** { **on** \| **off** } **)** \
> **#pragma bileşeni (mintypeınfo,** { **on** \| **off** } **)**

## <a name="remarks"></a>Açıklamalar

### <a name="browser"></a>Tarayıcı

Toplama işlemini açıp kapatabilir ve bilgiler toplanırken dikkate alınmayacak adları belirtebilirsiniz.

Açık veya kapalı'yı kullanmak pragmadan ileri doğru gözatma bilgilerinin toplanmasını denetler. Örneğin:

```cpp
#pragma component(browser, off)
```

Derleyicinin gözatma bilgilerini toplamasını durdurur.

> [!NOTE]
> Bu pragma ile ilgili tarama bilgilerinin toplanmasını etkinleştirmek için, [önce tarama bilgilerinin etkinleştirilmesi gerekir](../build/reference/building-browse-information-files-overview.md).

**References** seçeneği *ad* bağımsız değişkeniyle birlikte veya olmadan kullanılabilir. *Ad* olmadan **başvuruların** kullanılması başvuruların toplanmasına açık veya kapalı olur (diğer tarama bilgileri toplanmaya devam eder, ancak). Örneğin:

```cpp
#pragma component(browser, off, references)
```

Derleyicinin başvuru bilgilerini toplama işlemini durdurur.

*Name* ve **off** ile **başvuruların** kullanılması, tarama bilgileri penceresinde görünen *ad* başvurularını önler. İlgilenmediğiniz adları ve türleri gözardı etmek ve gözatma bilgisi dosyalarının boyutunu küçültmek için bu sözdizimini kullanın. Örneğin:

```cpp
#pragma component(browser, off, references, DWORD)
```

Bu noktadan sonra gelen DWORD başvurularını yoksayar. **Üzerinde**kullanarak DWORD başvurularını toplamayı yeniden açabilirsiniz:

```cpp
#pragma component(browser, on, references, DWORD)
```

Bu, *ad*ile başvuruları toplamayı sürdürmenin tek yoludur; kapattığınız bir *adı* açık olarak açmanız gerekir.

Önişlemci 'nin *adı* genişletmesinin (null değeri 0 ' a genişletme gibi) engellemek için, tırnak içine alın:

```cpp
#pragma component(browser, off, references, "NULL")
```

### <a name="minimal-rebuild"></a>En az yeniden derleme

Kullanım dışı bırakılan [/GI (en az yeniden derlemeyi etkinleştir)](../build/reference/gm-enable-minimal-rebuild.md) özelliği, derleyicinin, disk alanı alan C++ sınıf bağımlılığı bilgilerini oluşturmasını ve depolamasını gerektirir. Disk alanından tasarruf etmek için, örneğin `#pragma component( minrebuild, off )` değişiklik olmayan başlık dosyalarında bağımlılık bilgilerini toplamanız gerektiğinde ' yi kullanabilirsiniz. `#pragma component( minrebuild, on )`Bağımlılık toplamayı yeniden açmak için sınıfların değiştirilmesini kaldırdıktan sonra Ekle.

### <a name="reduce-type-information"></a>Tür bilgilerini azaltma

`mintypeinfo`Seçeneği belirtilen bölge için hata ayıklama bilgilerini azaltır. Bu bilgilerin hacmi epey büyüktür; .pdb ve .obj dosyalarını etkiler. mintypeinfo bölgesindeki sınıflarda ve yapılarda hata ayıklaması yapamazsınız. mintypeinfo seçeneğini kullanmak aşağıdaki uyarıyı önlemeye yardımcı olabilir:

```cmd
LINK : warning LNK4018: too many type indexes in PDB "filename", discarding subsequent type information
```

Daha fazla bilgi için bkz. [/GD (en az yeniden derlemeyi etkinleştir)](../build/reference/gm-enable-minimal-rebuild.md)  derleyici seçeneği.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
