---
title: SECTIONS (C/C++)
ms.date: 11/04/2016
f1_keywords:
- SECTIONS
helpviewer_keywords:
- SECTIONS .def file statement
ms.assetid: 7b974366-9ef5-4e57-bbcc-73a1df6f8857
ms.openlocfilehash: 7b6708e760a85a137a01718d07a5f167de849220
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485872"
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

Bölüm özniteliklerini belirt eşdeğer bir yolu [/SECTION](../../build/reference/section-specify-section-attributes.md) seçeneği.

## <a name="see-also"></a>Ayrıca Bkz.

[Modül Tanımlama Deyimleri Kuralları](../../build/reference/rules-for-module-definition-statements.md)