---
title: "Satır içi işlevler | Microsoft Docs"
ms.custom: 
ms.date: 10/16/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- fast code
- inline functions, __inline keyword
- functions [C++], inline functions
ms.assetid: 00f4b2ff-8ad0-4165-9f4c-2ef157d03f31
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8b5adadc990bed67abe739a4d73b2973b26ca207
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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

