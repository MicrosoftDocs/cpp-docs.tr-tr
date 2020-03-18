---
title: Derleyici hatası C3446
ms.date: 07/21/2017
f1_keywords:
- C3446
helpviewer_keywords:
- C3446
ms.assetid: 33064548-24e4-46f1-beb1-476e3c3b3fbf
ms.openlocfilehash: 0f9ebd274a90dffe00b0e8375cc374acf46e7a08
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447112"
---
# <a name="compiler-error-c3446"></a>Derleyici hatası C3446

>'*Class*': değer sınıfının bir üyesi için varsayılan üye başlatıcıya izin verilmez

Visual Studio 2015 ve önceki sürümlerde, derleyici bir değer sınıfının üyesi için varsayılan üye başlatıcısını (ancak yok sayılır) izin verilir. Değer sınıfının varsayılan başlatması her zaman sıfır-üyeleri başlatır; varsayılan oluşturucuya izin verilmez. Visual Studio 2017 ' de, varsayılan üye başlatıcıları aşağıdaki örnekte gösterildiği gibi bir derleyici hatası yükseltir:

## <a name="example"></a>Örnek

Aşağıdaki örnek, Visual Studio 2017 ve sonraki sürümlerde C3446 oluşturur:

```cpp
// C3446.cpp
value struct V
{
       int i = 0; // error C3446: 'V::i': a default member initializer
                  // is not allowed for a member of a value class
       int j {0}; // C3446
};
```

Hatayı düzeltmek için başlatıcıyı kaldırın:

```cpp
// C3446b.cpp
value struct V
{
       int i;
       int j;
};
```

