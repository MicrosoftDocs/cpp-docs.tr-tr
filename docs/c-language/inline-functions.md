---
description: 'Daha fazla bilgi edinin: satır Içi Işlevler'
title: Satır İçi İşlevler
ms.date: 10/16/2017
helpviewer_keywords:
- fast code
- inline functions, __inline keyword
- functions [C++], inline functions
ms.assetid: 00f4b2ff-8ad0-4165-9f4c-2ef157d03f31
ms.openlocfilehash: 616e85f2ac298420b3de174551ea2f6f879f24f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137560"
---
# <a name="inline-functions"></a>Satır İçi İşlevler

**Microsoft'a Özgü**

**`__inline`** Anahtar sözcüğü, derleyiciye bir işlev çağrısının her örneği için işlev tanımı içindeki kodu yerini vermesini söyler. Ancak, değiştirme yalnızca derleyicinin denetiminde gerçekleştirilir. Örneğin, derleyici bir işlevi adresi alınmışsa veya satır içine alınmak için çok büyükse satır içine almaz.

Bir işlevin satır içine alınabilecek bir aday olarak değerlendirilebilmesi için yeni stilde işlev tanımını kullanması gerekir.

Bir satır içi işlevi belirtmek için bu biçimi kullanın:

> **`__inline`***tür*<sub>opt</sub> *işlev tanımı*

Satır içi işlevlerin kullanımı, aşağıdaki nedenlerden dolayı daha hızlı bir şekilde kod oluşturur ve bazen eşdeğer işlev çağrısının oluşturacağından daha küçük kod oluşturabilir:

- İşlev çağrılarını yürütmek için gereken süreden tasarruf etmenizi sağlar.

- Üç veya daha az satıra sahip olanlar gibi küçük satır içi işlevler, derleyici bağımsız değişkenleri ve bir dönüş değerini işlemek üzere kod oluşturmadığı için eşdeğer işlev çağrısından daha az kod oluşturur.

- Derleyici yordamlar arası iyileştirme gerçekleştirmediği için satır içinde oluşturulan işlevlere normal işlevlerde kullanılamayan kod iyileştirmeleri uygulanır.

Kullanan işlevler **`__inline`** satır içi assembler kodu ile karıştırılmamalıdır. Daha fazla bilgi için bkz. [satır Içi assembler](../c-language/inline-assembler-c.md) .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[satır içi, __inline, \_ _forceinline](../cpp/inline-functions-cpp.md)
