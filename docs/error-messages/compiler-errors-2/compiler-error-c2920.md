---
title: Derleyici hatası C2920
ms.date: 11/04/2016
f1_keywords:
- C2920
helpviewer_keywords:
- C2920
ms.assetid: 0a4cb2de-00a0-4209-8160-c7ce6ed7d9ab
ms.openlocfilehash: 2b744729097f7e697c7a7695a849b5ee46d7a4ab
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761038"
---
# <a name="compiler-error-c2920"></a>Derleyici hatası C2920

yeniden tanımlama: ' class ': sınıf şablonu veya genel zaten ' Type ' olarak tanımlanmış

Genel veya şablon sınıfı, eşdeğer olmayan birden çok bildirime sahiptir. Bu hatayı onarmak için farklı türler için farklı adlar kullanın veya tür adının yeniden açıklamasını kaldırın.

Aşağıdaki örnek C2920 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2920.cpp
// compile with: /c
typedef int TC1;
template <class T>
struct TC1 {};   // C2920
struct TC2 {};   // OK - fix by using a different name
```

C2920, genel türler kullanılırken de oluşabilir:

```cpp
// C2920b.cpp
// compile with: /clr /c
typedef int GC1;
generic <class T>
ref struct GC1 {};   // C2920
ref struct GC2 {};   // OK - fix by using a different name
```
