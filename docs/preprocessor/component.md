---
title: bileşenleri
ms.date: 04/08/2019
f1_keywords:
- vc-pragma.component
- component_CPP
helpviewer_keywords:
- component pragma
- pragmas, component
ms.assetid: 7b66355e-3201-4c14-8190-f4a2a81a604a
ms.openlocfilehash: 4870860650a39d27639ad18100ba37ba14aa15c0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366920"
---
# <a name="component"></a>bileşenleri

Gözatma bilgilerinin ya da kaynak dosyalarından bağımlılık bilgilerinin toplanmasını denetler.

## <a name="syntax"></a>Sözdizimi

> **#pragma component( browser,** { **on** | **off** }[**,** **references** [**,** *name* ]] **)** \
> **#pragma bileşeni (minrebuild,** | **devre dışı)** \
> **#pragma bileşeni (mintypeinfo,** | **devre dışı)**

## <a name="remarks"></a>Açıklamalar

### <a name="browser"></a>Tarayıcı

Toplama işlemini açıp kapatabilir ve bilgiler toplanırken dikkate alınmayacak adları belirtebilirsiniz.

Açık veya kapalı'yı kullanmak pragmadan ileri doğru gözatma bilgilerinin toplanmasını denetler. Örneğin:

```cpp
#pragma component(browser, off)
```

Derleyicinin gözatma bilgilerini toplamasını durdurur.

> [!NOTE]
> Bu pragma ile gözatma bilgilerini toplama işlemini etkinleştirmek için [gözatma bilgilerinin ilk etkinleştirilmelidir](../build/reference/building-browse-information-files-overview.md).

`references` Seçeneği ile veya olmadan kullanılabilir *adı* bağımsız değişken. Kullanarak `references` olmadan *adı* başvuruları toplama açar veya kapatır (diğer gözatma bilgileri toplanmaya devam ancak devam eder). Örneğin:

```cpp
#pragma component(browser, off, references)
```

Derleyicinin başvuru bilgilerini toplama işlemini durdurur.

Kullanarak `references` ile *adı* ve `off` başvurularının *adı* gözatma bilgileri penceresinde görünmesini. İlgilenmediğiniz adları ve türleri gözardı etmek ve gözatma bilgisi dosyalarının boyutunu küçültmek için bu sözdizimini kullanın. Örneğin:

```cpp
#pragma component(browser, off, references, DWORD)
```

o noktadan ilerideki DWORD başvurularını yoksayar. DWORD yapılan başvuruların yeniden kullanarak toplama kapatabilirsiniz `on`:

```cpp
#pragma component(browser, on, references, DWORD)
```

Başvurularını toplamaya devam etmek için tek yol budur *adı*; birinde açıkça etkinleştirmelisiniz *adı* , devre dışı bırakmış.

Önişlemci önlemek için *adı* (NULL 0'a genişletmek gibi), tırnak içine alın:

```cpp
#pragma component(browser, off, references, "NULL")
```

### <a name="minimal-rebuild"></a>En Az Yeniden Derleme

Kullanım dışı [/GM derlemeyi (etkinleştirme en az yeniden derlemeyi)](../build/reference/gm-enable-minimal-rebuild.md) özellik gerektirir oluşturmak ve depolamak için derleyicinin C++ sınıf bağımlılık bilgileri oluşturup disk alanı alır. Disk alanından kazanmak için kullanabileceğiniz `#pragma component( minrebuild, off )` gerekmediği bağımlılık bilgileri, örneğin, değişmeyen üstbilgi dosyalarında toplanacak. INSERT `#pragma component(minrebuild, on)` bağımlılık toplama etkinleştirmek için değişmeyen sınıflardan sonra.

### <a name="reduce-type-information"></a>Tür Bilgilerini Azaltma

`mintypeinfo` Seçeneği, belirtilen bölge için hata ayıklama bilgilerini azaltır. Bu bilgilerin hacmi epey büyüktür; .pdb ve .obj dosyalarını etkiler. mintypeinfo bölgesindeki sınıflarda ve yapılarda hata ayıklaması yapamazsınız. mintypeinfo seçeneğini kullanmak aşağıdaki uyarıyı önlemeye yardımcı olabilir:

```cmd
LINK : warning LNK4018: too many type indexes in PDB "filename", discarding subsequent type information
```

Daha fazla bilgi için [/GM derlemeyi (etkinleştirme en az yeniden derlemeyi)](../build/reference/gm-enable-minimal-rebuild.md) derleyici seçeneği.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)