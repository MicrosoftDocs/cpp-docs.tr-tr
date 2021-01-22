---
description: 'Daha fazla bilgi için: pragma'
title: once pragması
ms.date: 01/19/2021
f1_keywords:
- vc-pragma.once
- once_CPP
helpviewer_keywords:
- once pragma
- pragmas, once
ms.openlocfilehash: 87e3a87d8922868ce8ac3c48815c09de8727eba7
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667229"
---
# <a name="once-pragma"></a>`once` Prag

Bir kaynak kod dosyası derlenirken derleyicinin başlık dosyasını yalnızca bir kez içerdiğini belirtir.

## <a name="syntax"></a>Syntax

> **`#pragma once`**

## <a name="remarks"></a>Açıklamalar

' Nin kullanımı, `#pragma once` derleyici açılmaya, ve dosyayı `#include` çeviri birimindeki dosyanın birincisinden sonra yeniden okuyameyeceği için derleme sürelerini azaltabilir. *Çoklu ekleme iyileştirmesi* olarak adlandırılır. Dosya içeriğini birden çok eklemeyi önlemek için Önişlemci Makro tanımlarını kullanan *Include Guard* iDom öğesine benzer bir etkiye sahiptir. Ayrıca, *bir tanım kuralının* ihlallerini önlemeye de yardımcı olur: Tüm şablonların, türlerin, işlevlerin ve nesnelerin kodunuzda birden fazla tanımı yok.

Örnek:

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

[`pragma` yönergeler ve `__pragma` anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
