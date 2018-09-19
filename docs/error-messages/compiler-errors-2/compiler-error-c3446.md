---
title: Derleyici Hatası C3446 | Microsoft Docs
ms.custom: ''
ms.date: 07/21/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3446
dev_langs:
- C++
helpviewer_keywords:
- C3445
ms.assetid: 33064548-24e4-46f1-beb1-476e3c3b3fbf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a88bb77489d2596c271842e7becb0214d1af2821
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018873"
---
# <a name="compiler-error-c3446"></a>Derleyici Hatası C3446

>'*sınıfı*': bir değer sınıfının üyesi için varsayılan üye başlatıcıya izin verilmez

Visual Studio 2015 ve önceki sürümlerinde, derleyici izin verilir (ancak göz ardı) bir değer sınıfının üyesi için varsayılan üye başlatıcıya. Her zaman varsayılan bir değer sınıfının başlatma sıfır-üyeleri başlatır; Varsayılan bir oluşturucu izin verilmez. Visual Studio 2017'de, bu örnekte gösterildiği gibi varsayılan üye Başlatıcı bir derleyici hatası Yükselt:

## <a name="example"></a>Örnek

Aşağıdaki örnek, Visual Studio 2017 ve sonraki sürümlerinde C3446 oluşturur:

```cpp
// C3446.cpp
value struct V
{
       int i = 0; // error C3446: 'V::i': a default member initializer
                  // is not allowed for a member of a value class
       int j {0}; // C3446
};
```

Hatayı düzeltmek için Başlatıcı kaldırın:

```cpp
// C3446b.cpp
value struct V
{
       int i;
       int j;
};
```

