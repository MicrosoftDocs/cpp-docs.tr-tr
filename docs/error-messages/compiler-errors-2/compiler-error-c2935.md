---
title: Derleyici Hatası C2935 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2935
dev_langs:
- C++
helpviewer_keywords:
- C2935
ms.assetid: e11ef90d-0756-4e43-8a09-4974c6aa72a3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c37719276ccb6e541b192873429c0876256bf9b3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088312"
---
# <a name="compiler-error-c2935"></a>Derleyici Hatası C2935

'class': türü sınıf kimliği için genel bir işlev yeniden tanımlandı

Genel veya Şablon sınıfı, genel bir işlev kullanamazsınız.

Küme ayraçları yanlış eşleşirse bu hataya neden olabilir.

Aşağıdaki örnek, C2935 oluşturur:

```
// C2935.cpp
// compile with: /c
template<class T>
struct TC {};
void TC<int>() {}   // C2935

// OK
struct TC2 {};
void TC2() {}
```

C2935, genel türler kullanırken da meydana gelebilir:

```
// C2935b.cpp
// compile with: /clr /c
generic<class T>
ref struct GC { };
void GC<int>() {}   // C2935
void GC() {}   // OK
```