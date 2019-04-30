---
title: Derleyici Hatası C2995
ms.date: 11/04/2016
f1_keywords:
- C2995
helpviewer_keywords:
- C2995
ms.assetid: a57cdfe0-b40b-4a67-a95c-1a49ace4842b
ms.openlocfilehash: 56bd012457fe17cec7d46095ba7c98658d030b14
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404279"
---
# <a name="compiler-error-c2995"></a>Derleyici Hatası C2995

'function': işlev şablon zaten tanımlanmış

Her üye işlev için yalnızca bir tanımı bir şablonlu sınıfın olduğundan emin olun.

Aşağıdaki örnek, C2995 oluşturur:

```
// C2995.cpp
// compile with: /c
template <class T>
void Test(T x){}

template <class T> void Test(T x){}   // C2995
template <class T> void Test2(T x){}   // OK
```