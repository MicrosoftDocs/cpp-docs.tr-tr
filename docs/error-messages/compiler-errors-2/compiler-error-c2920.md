---
title: Derleyici Hatası C2920 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2920
dev_langs:
- C++
helpviewer_keywords:
- C2920
ms.assetid: 0a4cb2de-00a0-4209-8160-c7ce6ed7d9ab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd8d28cf0f201b3042fe3d7a13d28e56150c976e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021609"
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