---
title: Derleyici Hatası C2942 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2942
dev_langs:
- C++
helpviewer_keywords:
- C2942
ms.assetid: 13abf744-8fa1-450d-886d-e5717c04956e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 024557750def49151d835545eec62bfc6f4727e0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033205"
---
# <a name="compiler-error-c2942"></a>Derleyici Hatası C2942

'class': türü sınıf kimliği bir işlevin biçimsel bağımsız değişken yeniden tanımlandı

Genel veya Şablon sınıfı bir biçimsel bağımsız değişken olarak kullanamazsınız. Doğrudan genel Oluşturucusu veya Şablon sınıfı bir bağımsız değişken geçiremezsiniz.

Aşağıdaki örnek, C2942 oluşturur:

```

// C2942.cpp
// compile with: /c
template<class T>
struct TC {};
void f(int TC<int>) {}   // C2942

// OK
struct TC2 {};
void f(TC2 i) {}
```

C2942, genel türler kullanırken da meydana gelebilir:

```
// C2942b.cpp
// compile with: /clr /c
generic<class T>
ref struct GC {};
void f(int GC<int>) {}   // C2942
ref struct GC2 { };
void f(int GC2) {}
```