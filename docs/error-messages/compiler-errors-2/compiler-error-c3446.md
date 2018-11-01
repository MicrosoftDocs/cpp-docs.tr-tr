---
title: Derleyici Hatası C3446
ms.date: 07/21/2017
f1_keywords:
- C3446
helpviewer_keywords:
- C3445
ms.assetid: 33064548-24e4-46f1-beb1-476e3c3b3fbf
ms.openlocfilehash: 8145e0cdd97022ebdcc1a7ce38c8860a005945b0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631126"
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

