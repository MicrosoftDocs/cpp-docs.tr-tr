---
title: Önemli hata C1202
ms.date: 11/04/2016
f1_keywords:
- C1202
helpviewer_keywords:
- C1202
ms.assetid: c859adb8-17a7-4fa1-a1f3-5820b7bf3849
ms.openlocfilehash: 08694e8df4e72d730f19e08db7370f7bd866266e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747221"
---
# <a name="fatal-error-c1202"></a>Önemli hata C1202

özyinelemeli tür veya işlev bağımlılığı bağlamı çok karmaşık

Bir şablon tanımı özyinelemeli veya karmaşıklık limitlerinin aşılması.

## <a name="example"></a>Örnek

Aşağıdaki örnek C1202 oluşturur.

```cpp
// C1202.cpp
// processor: x86 IPF
template<int n>
class Factorial : public Factorial<n-1>  {   // C1202
public:
   operator int () {
      return Factorial <n-1>::operator int () * n;
   }
};
Factorial<7> facSeven;
```

## <a name="example"></a>Örnek

Olası çözüm.

```cpp
// C1202b.cpp
// compile with: /c
template<int n>
class Factorial : public Factorial<n-1> {
public:
   operator int () {
      return Factorial <n-1>::operator int () * n;
   }
};

template <>
class Factorial<0> {
public:
   operator int () {
      return 1;
   }
};

Factorial<7> facSeven;
```
