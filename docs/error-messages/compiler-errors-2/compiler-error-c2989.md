---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2989'
title: Derleyici hatası C2989
ms.date: 11/04/2016
f1_keywords:
- C2989
helpviewer_keywords:
- C2989
ms.assetid: 936303d8-eb3b-4746-82ec-2f18020a6f64
ms.openlocfilehash: 38838630f5be23698de099d8c40f7e9b96bc2b13
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338601"
---
# <a name="compiler-error-c2989"></a>Derleyici hatası C2989

' class ': sınıf türü zaten sınıf olmayan bir tür olarak tanımlanmış

Genel veya şablon sınıfı, şablon olmayan veya genel olmayan bir sınıfı tanımlar. Üst bilgi dosyalarını çakışmalar için denetleyin.

Aşağıdaki örnek C2989 oluşturur:

```cpp
// C2989.cpp
// compile with: /c
class C{};

template <class T>
class C{};  // C2989
class C2{};
```

C2989, genel türler kullanılırken de oluşabilir:

```cpp
// C2989b.cpp
// compile with: /clr /c
ref class GC1;

generic <typename T> ref class GC1;   // C2989
template <typename T> ref class GC2;

generic <typename T> ref class GC2;   // C2989
generic <typename T> ref class GCb;
template <typename T> ref class GC2;
generic <typename T> ref class GCc;
```
