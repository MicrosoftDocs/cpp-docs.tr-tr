---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2920'
title: Derleyici hatası C2920
ms.date: 11/04/2016
f1_keywords:
- C2920
helpviewer_keywords:
- C2920
ms.assetid: 0a4cb2de-00a0-4209-8160-c7ce6ed7d9ab
ms.openlocfilehash: 08c11832fc2241fb8fbebf7bda56db29bf181022
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270335"
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
