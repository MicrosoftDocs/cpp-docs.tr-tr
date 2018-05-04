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
ms.openlocfilehash: be5afa2dc4980f9393deb498c7a5decdc56aece5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="inline-functions"></a>Satır İçi İşlevler

**Microsoft özel**

`__inline` anahtar sözcüğü, derleyiciye işlev tanımı içindeki kodu bir işlev çağrısının her örneğiyle değiştirmesini söyler. Ancak, değiştirme yalnızca derleyicinin denetiminde gerçekleştirilir. Örneğin, derleyici bir işlevi adresi alınmışsa veya satır içine alınmak için çok büyükse satır içine almaz.

Bir işlevin satır içine alınabilecek bir aday olarak değerlendirilebilmesi için yeni stilde işlev tanımını kullanması gerekir.

Bir satır içi işlevi belirtmek için bu biçimi kullanın:

> **__inline** *türü*<sub>kabul</sub> *işlev tanımı*

Satır içi işlevlerin kullanımı, aşağıdaki nedenlerden dolayı daha hızlı bir şekilde kod oluşturur ve bazen eşdeğer işlev çağrısının oluşturacağından daha küçük kod oluşturabilir:

- İşlev çağrılarını yürütmek için gereken süreden tasarruf etmenizi sağlar.

- Üç veya daha az satıra sahip olanlar gibi küçük satır içi işlevler, derleyici bağımsız değişkenleri ve bir dönüş değerini işlemek üzere kod oluşturmadığı için eşdeğer işlev çağrısından daha az kod oluşturur.

- Derleyici yordamlar arası iyileştirme gerçekleştirmediği için satır içinde oluşturulan işlevlere normal işlevlerde kullanılamayan kod iyileştirmeleri uygulanır.

`__inline` kullanan işlevler satır içi derleyici koduyla karıştırılmamalıdır. Bkz: [satır içi derleyicisi](../c-language/inline-assembler-c.md) daha fazla bilgi için.

**SON Microsoft özel**  

## <a name="see-also"></a>Ayrıca Bkz.

[Satır içi, __inline, \__forceinline](../cpp/inline-functions-cpp.md)

