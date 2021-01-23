---
description: 'Daha fazla bilgi edinin: pragma'
title: tek pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.once
- once_CPP
helpviewer_keywords:
- once pragma
- pragma, once
no-loc:
- pragma
ms.openlocfilehash: 3edb5f88202ee783e587b1f886eddddf427f6133
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713486"
---
# <a name="once-no-locpragma"></a>`once` pragma

Bir kaynak kod dosyası derlenirken derleyicinin başlık dosyasını yalnızca bir kez içerdiğini belirtir.

## <a name="syntax"></a>Syntax

> **`#pragma once`**

## <a name="remarks"></a>Açıklamalar

' Nin kullanımı, `#pragma once` derleyici açılmaya, ve dosyayı `#include` çeviri birimindeki dosyanın birincisinden sonra yeniden okuyameyeceği için derleme sürelerini azaltabilir. *Çoklu ekleme iyileştirmesi* olarak adlandırılır. Dosya içeriğini birden çok eklemeyi önlemek için Önişlemci Makro tanımlarını kullanan *Include Guard* iDom öğesine benzer bir etkiye sahiptir. Ayrıca, *bir tanım kuralının* ihlallerini önlemeye de yardımcı olur: Tüm şablonların, türlerin, işlevlerin ve nesnelerin kodunuzda birden fazla tanımı yok.

Örneğin:

```cpp
// header.h
#pragma once
// Code placed here is included only once per translation unit
```

`#pragma once`Bir Önişlemci simgesiyle genel ad alanını pollute olmadığından, yeni kod için yönergeyi öneririz. Daha az yazma gerektirir, daha az dikkat dağıtıcı olur ve *sembol* çakışmalarına neden olamaz. Farklı üstbilgi dosyaları koruma değeri olarak aynı Önişlemci sembolünü kullandıklarında sembol çarpışmaları hatalara neden oldu. C++ standardının bir parçası değildir, ancak birkaç ortak derleyiciler tarafından kullanılamaz şekilde uygulanır.

Hem Include Guard IOM hem de aynı dosyada kullanılması yararlıdır `#pragma once` . Derleyici, Include Guard idi 'yi tanır ve `#pragma once` Açıklama olmayan bir kod ya da Önişlemci yönergesi deyimin standart biçimi olmadan önce veya sonra geliyorsa yönergeyle aynı şekilde birden çok ekleme iyileştirmesi uygular:

```cpp
// header.h
// Demonstration of the #include guard idiom.
// Note that the defined symbol can be arbitrary.
#ifndef HEADER_H_     // equivalently, #if !defined HEADER_H_
#define HEADER_H_
// Code placed here is included only once per translation unit
#endif // HEADER_H_
```

Kod, `#pragma once` yönergeyi uygulamayan, mevcut kodla tutarlılığı sürdürmek için veya çoklu ekleme iyileştirmesinin imkansız olması halinde, bir kodu, yönergeyi uygulayan derleyicilere taşınabilir hale getirmeli, Include Guard deyimidir. Dosya sistemi diğer adı veya diğer ad içerme yolları, derleyicinin benzer içerme dosyalarını kurallı yola göre tanımlamayı engelliyorsa, karmaşık projelerde bu durum oluşabilir.

`#pragma once`Bir veya birden çok kez dahil olmak üzere tasarlanan üst bilgi dosyalarında, etkilerini kontrol etmek için önişlemci sembolleri kullanan bir koruyucu. Bu tasarıma bir örnek için bkz \<assert.h> . üstbilgi dosyası. Ayrıca, dahil edilen dosyalara birden çok yol oluşturmaktan kaçınmak için ekleme yollarınızı yönetmeye özen gösterin. Bu, hem dahil etme hem de ekleme için birden çok içerme iyileştirmesi ve `#pragma once` .

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
