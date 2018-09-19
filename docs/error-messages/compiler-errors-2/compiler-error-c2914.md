---
title: Derleyici Hatası C2914 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2914
dev_langs:
- C++
helpviewer_keywords:
- C2914
ms.assetid: fc6a0592-f53e-4f5a-88cb-780bbed4acf2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7fddc7d479e743162a43a96a80b8d362678bf51f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027797"
---
# <a name="compiler-error-c2914"></a>Derleyici Hatası C2914

'identifier': işlev bağımsız değişkeni belirsiz olduğundan, tür bağımsız değişkeni çıkarılamıyor

Derleyici, genel veya şablon bağımsız değişkeni için kullanılacak işlev aşırı belirlenemiyor.

Aşağıdaki örnek, C2914 oluşturur:

```
// C2914.cpp
// compile with: /c
void f(int);
void f(double);
template<class T> void g(void (*) (T));
void h() { g(f); }   // C2914
// try the following line instead
// void h() { g<int>(f); }
```

C2914, genel türler kullanırken da meydana gelebilir.  Aşağıdaki örnek, C2914 oluşturur:

```
// C2914b.cpp
// compile with: /clr /c
void f(int);
void f(double);

template<class T>
void gf(void (*) (T));

void h() { gf(f);}   // C2914
// try the following line instead
void h() { gf<int>(f); }
```