---
title: once pragması
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.once
- once_CPP
helpviewer_keywords:
- once pragma
- pragmas, once
ms.assetid: c7517556-6403-4b16-8898-f2aa0a6f685f
ms.openlocfilehash: 643ad83b672f7b632925383972751a966256eb41
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220542"
---
# <a name="once-pragma"></a>once pragması

Bir kaynak kod dosyası derlenirken derleyicinin başlık dosyasını yalnızca bir kez içerdiğini belirtir.

## <a name="syntax"></a>Sözdizimi

> **bir kez #pragma**

## <a name="remarks"></a>Açıklamalar

' Nin `#pragma once` kullanımı, derleyici açılmaya, ve dosyayı çeviri birimindeki dosyanın birincisinden `#include` sonra yeniden okuyameyeceği için derleme sürelerini azaltabilir. *Çoklu ekleme iyileştirmesi*olarak adlandırılır. Dosya içeriğini birden çok eklemeyi önlemek için Önişlemci Makro tanımlarını kullanan *Include Guard* iDom öğesine benzer bir etkiye sahiptir. Ayrıca, *tek bir tanım kuralının*ihlallerini önlemeye de yardımcı olur, tüm şablonlar, türler, işlevler ve nesneler kodunuzda birden fazla tanıma sahip değildir.

Örneğin:

```cpp
// header.h
#pragma once
// Code placed here is included only once per translation unit
```

Bir Önişlemci simgesiyle `#pragma once` genel ad alanını pollute olmadığından, yeni kod için yönergeyi öneririz. Daha az yazma gerektirir, daha az dikkat dağıtıcı olur ve *sembol*çakışmalarına neden olmaz, farklı üstbilgi dosyaları koruma değeri olarak aynı Önişlemci sembolünü kullandıklarında hata oluşur. C++ Standart bir parçası değildir, ancak birkaç ortak derleyiciler tarafından kullanılamaz şekilde uygulanır.

Hem Include Guard IOM `#pragma once` hem de aynı dosyada kullanılması yararlıdır. Derleyici, Include Guard idi 'yi tanır ve açıklama olmayan bir kod ya da Önişlemci yönergesi deyimin standart biçimi olmadan `#pragma once` önce veya sonra geliyorsa yönergeyle aynı şekilde birden çok ekleme iyileştirmesi uygular:

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

`#pragma once` Bir veya birden çok kez dahil olmak üzere tasarlanan üst bilgi dosyalarında, etkilerini kontrol etmek için önişlemci sembolleri kullanan bir koruyucu. Bu tasarıma bir örnek için bkz \<. onaylama. h > üst bilgi dosyası. Ayrıca, dahil edilen dosyalara birden çok yol oluşturmaktan kaçınmak için ekleme yollarınızı yönetmeye özen gösterin. Bu, hem dahil etme hem de ekleme için birden çok içerme iyileştirmesi `#pragma once`ve.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
