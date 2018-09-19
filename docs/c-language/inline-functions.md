---
title: Satır içi işlevler | Microsoft Docs
ms.custom: ''
ms.date: 10/16/2017
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- fast code
- inline functions, __inline keyword
- functions [C++], inline functions
ms.assetid: 00f4b2ff-8ad0-4165-9f4c-2ef157d03f31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 127438da4929e58e07e10701dd64869b084fe4c5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078588"
---
# <a name="inline-functions"></a>Satır İçi İşlevler

**Microsoft'a özgü**

`__inline` anahtar sözcüğü, derleyiciye işlev tanımı içindeki kodu bir işlev çağrısının her örneğiyle değiştirmesini söyler. Ancak, değiştirme yalnızca derleyicinin denetiminde gerçekleştirilir. Örneğin, derleyici bir işlevi adresi alınmışsa veya satır içine alınmak için çok büyükse satır içine almaz.

Bir işlevin satır içine alınabilecek bir aday olarak değerlendirilebilmesi için yeni stilde işlev tanımını kullanması gerekir.

Bir satır içi işlevi belirtmek için bu biçimi kullanın:

> **__inline** *türü*<sub>iyileştirilmiş</sub> *işlev tanımı*

Satır içi işlevlerin kullanımı, aşağıdaki nedenlerden dolayı daha hızlı bir şekilde kod oluşturur ve bazen eşdeğer işlev çağrısının oluşturacağından daha küçük kod oluşturabilir:

- İşlev çağrılarını yürütmek için gereken süreden tasarruf etmenizi sağlar.

- Üç veya daha az satıra sahip olanlar gibi küçük satır içi işlevler, derleyici bağımsız değişkenleri ve bir dönüş değerini işlemek üzere kod oluşturmadığı için eşdeğer işlev çağrısından daha az kod oluşturur.

- Derleyici yordamlar arası iyileştirme gerçekleştirmediği için satır içinde oluşturulan işlevlere normal işlevlerde kullanılamayan kod iyileştirmeleri uygulanır.

`__inline` kullanan işlevler satır içi derleyici koduyla karıştırılmamalıdır. Bkz: [satır içi Assembler](../c-language/inline-assembler-c.md) daha fazla bilgi için.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Satır içi, __inline, \__forceinline](../cpp/inline-functions-cpp.md)

