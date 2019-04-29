---
title: SECTIONS (C/C++)
ms.date: 11/04/2016
f1_keywords:
- SECTIONS
helpviewer_keywords:
- SECTIONS .def file statement
ms.assetid: 7b974366-9ef5-4e57-bbcc-73a1df6f8857
ms.openlocfilehash: 5125b09675969c784aafe375faf1fdbc36d8c5d9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318634"
---
# <a name="sections-cc"></a>SECTIONS (C/C++)

Bir veya daha fazla bir bölüm tanıtır `definitions` projenizin çıkış dosyası olarak bölümlerde erişim belirticileri olan.

```
SECTIONS
definitions
```

## <a name="remarks"></a>Açıklamalar

Her tanım ayrı bir satırda olmalıdır. `SECTIONS` Anahtar sözcüğü, ilk tanım ile aynı satırda veya bir önceki satırdaki olabilir. Bir veya daha fazla .def dosyası içerebilir `SECTIONS` deyimleri.

Bu `SECTIONS` deyimi görüntü dosyasında bir veya daha fazla bölüm öznitelikleri ayarlar ve varsayılan öznitelikleri her bölüm türü için geçersiz kılmak için kullanılabilir.

Biçimi `definitions` olan:

`.section_name specifier`

Burada `.section_name` program görüntüsü bir bölümde adıdır ve `specifier` biri veya birkaçı aşağıdaki erişim değiştiriciler:

|Değiştirici|Açıklama|
|--------------|-----------------|
|`EXECUTE`|Yürütülebilir bir bölümdür|
|`READ`|Veri okuma işlemlerinin sağlar|
|`SHARED`|Resmi yüklemek tüm işlemler arasında bölümü paylaşır|
|`WRITE`|Veri yazma işlemleri sağlar.|

Belirleyicisi adlarının boşlukla ayırın. Örneğin:

```
SECTIONS
.rdata READ WRITE
```

`SECTIONS` Bölüm listesi başlangıcını işaretler `definitions`. Her `definition` ayrı bir satırda olmalıdır. `SECTIONS` Anahtar sözcüğü, birinci ile aynı satırda olabilir `definition` veya önceki bir satır. Bir veya daha fazla .def dosyası içerebilir `SECTIONS` deyimleri. `SEGMENTS` Anahtar sözcüğü bir eşanlamlısı olarak desteklenen `SECTIONS`.

Visual C++'ın daha eski sürümleri desteklenir:

```
section [CLASS 'classname'] specifier
```

`CLASS` Anahtar sözcüğü, uyumluluk için desteklenir, ancak göz ardı edilir.

Bölüm özniteliklerini belirt eşdeğer bir yolu [/SECTION](section-specify-section-attributes.md) seçeneği.

## <a name="see-also"></a>Ayrıca bkz.

[Modül Tanımlama Deyimleri Kuralları](rules-for-module-definition-statements.md)
