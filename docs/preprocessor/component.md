---
title: bileşenleri
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.component
- component_CPP
helpviewer_keywords:
- component pragma
- pragmas, component
ms.assetid: 7b66355e-3201-4c14-8190-f4a2a81a604a
ms.openlocfilehash: af0e4d7267fab92c867431ab70f4d8a0240a79d2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666121"
---
# <a name="component"></a>bileşenleri
Gözatma bilgilerinin ya da kaynak dosyalarından bağımlılık bilgilerinin toplanmasını denetler.

## <a name="syntax"></a>Sözdizimi

```
#pragma component( browser, { on | off }[, references [, name ]] )
#pragma component( minrebuild, on | off )
#pragma component( mintypeinfo, on | off )
```

## <a name="remarks"></a>Açıklamalar

### <a name="browser"></a>Tarayıcı

Toplama işlemini açıp kapatabilir ve bilgiler toplanırken dikkate alınmayacak adları belirtebilirsiniz.

Açık veya kapalı'yı kullanmak pragmadan ileri doğru gözatma bilgilerinin toplanmasını denetler. Örneğin:

```
#pragma component(browser, off)
```

Derleyicinin gözatma bilgilerini toplamasını durdurur.

> [!NOTE]
> Bu pragma ile gözatma bilgilerini toplama işlemini etkinleştirmek için [gözatma bilgilerinin ilk etkinleştirilmelidir](../build/reference/building-browse-information-files-overview.md).

`references` Seçeneği ile veya olmadan kullanılabilir *adı* bağımsız değişken. Kullanarak `references` olmadan *adı* başvuruları toplama açar veya kapatır (diğer gözatma bilgileri toplanmaya devam ancak devam eder). Örneğin:

```
#pragma component(browser, off, references)
```

Derleyicinin başvuru bilgilerini toplama işlemini durdurur.

Kullanarak `references` ile *adı* ve `off` başvurularının *adı* gözatma bilgileri penceresinde görünmesini. İlgilenmediğiniz adları ve türleri gözardı etmek ve gözatma bilgisi dosyalarının boyutunu küçültmek için bu sözdizimini kullanın. Örneğin:

```
#pragma component(browser, off, references, DWORD)
```

o noktadan ilerideki DWORD başvurularını yoksayar. DWORD yapılan başvuruların yeniden kullanarak toplama kapatabilirsiniz `on`:

```
#pragma component(browser, on, references, DWORD)
```

Başvurularını toplamaya devam etmek için tek yol budur *adı*; birinde açıkça etkinleştirmelisiniz *adı* , devre dışı bırakmış.

Önişlemci önlemek için *adı* (NULL 0'a genişletmek gibi), tırnak içine alın:

```
#pragma component(browser, off, references, "NULL")
```

### <a name="minimal-rebuild"></a>En Az Yeniden Derleme

Visual C++ en az yeniden derleme özelliği, derleyicinin disk alanında yer kaplayan C++ sınıf bağımlılık bilgileri oluşturup depolamasını gerektirir. Disk alanından kazanmak için kullanabileceğiniz `#pragma component( minrebuild, off )` gerekmediği bağımlılık bilgileri, örneğin, değişmeyen üstbilgi dosyalarında toplanacak. INSERT `#pragma component(minrebuild, on)` bağımlılık toplama etkinleştirmek için değişmeyen sınıflardan sonra.

### <a name="reduce-type-information"></a>Tür Bilgilerini Azaltma

`mintypeinfo` Seçeneği, belirtilen bölge için hata ayıklama bilgilerini azaltır. Bu bilgilerin hacmi epey büyüktür; .pdb ve .obj dosyalarını etkiler. mintypeinfo bölgesindeki sınıflarda ve yapılarda hata ayıklaması yapamazsınız. mintypeinfo seçeneğini kullanmak aşağıdaki uyarıyı önlemeye yardımcı olabilir:

```
LINK : warning LNK4018: too many type indexes in PDB "filename", discarding subsequent type information
```

Daha fazla bilgi için [en az yeniden derlemeyi etkinleştir](../build/reference/gm-enable-minimal-rebuild.md) (/ Gm) derleyici seçeneği.

## <a name="see-also"></a>Ayrıca Bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)