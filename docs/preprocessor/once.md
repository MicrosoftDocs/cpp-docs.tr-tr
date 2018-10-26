---
title: sonra | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.once
- once_CPP
dev_langs:
- C++
helpviewer_keywords:
- once pragma
- pragmas, once
ms.assetid: c7517556-6403-4b16-8898-f2aa0a6f685f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 14b66b2305e90c0e36ed17d3c325f145ff850704
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50056028"
---
# <a name="once"></a>once
Bir kaynak kodu dosyasını derlerken dosyanın (açık) yalnızca bir kez derleyici tarafından dahil olacağını belirtir.

## <a name="syntax"></a>Sözdizimi

```
#pragma once
```

## <a name="remarks"></a>Açıklamalar

Kullanımını `#pragma once` derleyici değil açın ve sonra ilk dosyayı okuma gibi derleme zamanlarını azaltabilir `#include` çeviri biriminin dosya. Bu olarak adlandırılır *iyileştirme birden çok dahil*. Benzer şekilde etkiye sahiptir `#include guard` birden çok eklenmesi, dosyanın içeriğini engellemek için makro önişlemci tanımları kullanan deyimidir. Bu ayrıca ihlallerini önlemeye yardımcı olur *tek tanım kuralı*— tüm şablonları, türler, İşlevler ve nesneler, kodunuzda birden fazla tanıma sahip gereksinim.

Örneğin:

```
// header.h
#pragma once
// Code placed here is included only once per translation unit
```

Öneririz `#pragma once` yeni kod için yönerge önişlemci sembolü ile genel ad pollute değil çünkü. Daha az yazarak gerektirir, daha az dağıtıyor ve sembol çakışması neden — farklı bir üst bilgi dosyaları koruma değeri olarak aynı önişlemci sembolü kullandığınızda ortaya çıkan hatalar. C++ standardının bir parçası değildir, ancak temelinizi birkaç ortak derleyiciler tarafından uygulanır.

Her ikisi de kullanmak için herhangi bir avantaj sağlamaz # guard deyim include ve `#pragma once` aynı dosyada. Derleyici tanır # guard deyimidir ve birden çok dahil en iyi duruma getirme aynı şekilde uygular include `#pragma once` açıklaması olmayan kod veya önişlemci yönergesi önce veya sonra deyim standart biçiminde geliyorsa yönergesi:

```
// header.h
// Demonstration of the #include guard idiom.
// Note that the defined symbol can be arbitrary.
#ifndef HEADER_H_     // equivalently, #if !defined HEADER_H_
#define HEADER_H_
// Code placed here is included only once per translation unit
#endif // HEADER_H_
```

Öneririz `#include guard` kod uygulamayan derleyicileri için taşınabilir olması gerektiğinde deyim `#pragma once` yönergesi, mevcut kodu ile tutarlılık sağlamak için veya birden çok dahil en iyi duruma getirme imkansızdır. Dosya sistemi yumuşatma ya da diğer adlı eklediğinizde bu yolları önlemek tanımlayan derleyicinin aynı karmaşık projeler içinde oluşabilir kurallı yoluyla dosyaları içerir.

Kullanmamaya özen `#pragma once` veya `#include guard` ifadede etkilerini kontrol etmek için önişlemci sembolleri kullanarak tasarlanmış birden çok kez eklenmesi üst bilgi dosyaları. Bu tasarım örneği için bkz: \<assert.h > üst bilgi dosyası. Ayrıca yönetmek dikkatli olun yenmek eklenen dosyalar, çoklu yolları oluşturmaktan kaçınmak için yol eklemeyi iyileştirme her ikisi için de birden çok dahil `#include guard`s ve `#pragma once`.

## <a name="see-also"></a>Ayrıca Bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)