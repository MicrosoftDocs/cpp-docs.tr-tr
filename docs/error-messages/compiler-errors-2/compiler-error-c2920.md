---
title: Derleyici Hatası C2920
ms.date: 11/04/2016
f1_keywords:
- C2920
helpviewer_keywords:
- C2920
ms.assetid: 0a4cb2de-00a0-4209-8160-c7ce6ed7d9ab
ms.openlocfilehash: 28bbbd30bcb16e2ea5fc14fe0f48f86814ee13c4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50616484"
---
# <a name="compiler-error-c2920"></a>Derleyici Hatası C2920

yeniden tanımlama: 'class': sınıf şablonu veya genel zaten bildirildi 'türü olarak'

Bir genel veya Şablon sınıfı, eşdeğer olan birden fazla bildirimi sahiptir. Bu hatayı düzeltmek için farklı türleri için farklı adlar kullanın veya yeniden tanımlanması, tür adı'nı kaldırın.

Aşağıdaki örnek, C2920 oluşturur ve bu sorunun nasıl gösterir:

```
// C2920.cpp
// compile with: /c
typedef int TC1;
template <class T>
struct TC1 {};   // C2920
struct TC2 {};   // OK - fix by using a different name
```

C2920, genel türler kullanırken da meydana gelebilir:

```
// C2920b.cpp
// compile with: /clr /c
typedef int GC1;
generic <class T>
ref struct GC1 {};   // C2920
ref struct GC2 {};   // OK - fix by using a different name
```