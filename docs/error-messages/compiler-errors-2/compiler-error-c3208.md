---
title: Derleyici Hatası C3208
ms.date: 11/04/2016
f1_keywords:
- C3208
helpviewer_keywords:
- C3208
ms.assetid: 6d060bfe-52cf-4599-8f70-bdeb5a670df3
ms.openlocfilehash: fa665f17de7ff6bec00ecdaf9d1749b0626c9181
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402677"
---
# <a name="compiler-error-c3208"></a>Derleyici Hatası C3208

'function': 'class' sınıf şablonunun şablon parametre listesiyle şablon şablon parametresi 'parametresi' şablon parametre listesiyle eşleşmiyor

Şablon Şablon parametresi, aynı sayıda şablon parametreleri olarak sağlanan sınıf şablonu yok.

Aşağıdaki örnek, C3208 oluşturur:

```
// C3208.cpp
template <template <class T> class TT >
int f();

template <class T1, class T2>
struct S;

template <class T1>
struct R;

int i = f<S>();   // C3208
// try the following line instead
// int i = f<R>();
```