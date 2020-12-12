---
description: 'Daha fazla bilgi edinin: bölümler (C/C++)'
title: SECTIONS (C/C++)
ms.date: 11/04/2016
f1_keywords:
- SECTIONS
helpviewer_keywords:
- SECTIONS .def file statement
ms.assetid: 7b974366-9ef5-4e57-bbcc-73a1df6f8857
ms.openlocfilehash: aaebeb19c921dfb389c55209c7a371f49043cb56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224770"
---
# <a name="sections-cc"></a>SECTIONS (C/C++)

`definitions`Projenizin çıkış dosyasındaki bölümlerde erişim Belirticilerinin bir veya daha fazla bölümünü tanıtır.

```
SECTIONS
definitions
```

## <a name="remarks"></a>Açıklamalar

Her tanım ayrı bir satırda olmalıdır. `SECTIONS`Anahtar sözcüğü, ilk tanımıyla veya önceki bir satırda aynı satırda olabilir. . Def dosyası bir veya daha fazla deyim içerebilir `SECTIONS` .

Bu `SECTIONS` ifade, görüntü dosyasındaki bir veya daha fazla bölümün özniteliklerini ayarlar ve her bölüm türü için varsayılan öznitelikleri geçersiz kılmak için kullanılabilir.

Biçimi `definitions` :

`.section_name specifier`

, `.section_name` Program görüntinizdeki bir bölümün adıdır ve `specifier` aşağıdaki erişim değiştiricilerinden bir veya daha fazlasına sahiptir:

|Değiştirici|Açıklama|
|--------------|-----------------|
|`EXECUTE`|Bölüm yürütülebilir|
|`READ`|Verilerde okuma işlemlerine izin verir|
|`SHARED`|Görüntüyü yükleyen tüm süreçler arasında bölümü paylaşır|
|`WRITE`|Verilerde yazma işlemlerine izin verir|

Tanımlayıcı adlarını bir boşluk ile ayırın. Örneğin:

```
SECTIONS
.rdata READ WRITE
```

`SECTIONS` Bölüm listesinin başlangıcını işaretler `definitions` . Her birinin `definition` ayrı bir satırda olması gerekir. `SECTIONS`Anahtar sözcüğü, ilk `definition` veya önceki bir satır ile aynı satırda olabilir. . Def dosyası bir veya daha fazla deyim içerebilir `SECTIONS` . `SEGMENTS`Anahtar sözcüğü, için bir eş anlamlı olarak desteklenir `SECTIONS` .

Visual C++ eski sürümleri desteklenir:

```
section [CLASS 'classname'] specifier
```

`CLASS`Anahtar sözcüğü uyumluluk için desteklenir, ancak yok sayılır.

Bölüm özniteliklerini belirtmenin eşdeğer bir yolu, [/section](section-specify-section-attributes.md) seçeneğidir.

## <a name="see-also"></a>Ayrıca bkz.

[Module-Definition deyimleri için kurallar](rules-for-module-definition-statements.md)
