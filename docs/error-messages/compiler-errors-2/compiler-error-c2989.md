---
title: Derleyici Hatası C2989
ms.date: 11/04/2016
f1_keywords:
- C2989
helpviewer_keywords:
- C2989
ms.assetid: 936303d8-eb3b-4746-82ec-2f18020a6f64
ms.openlocfilehash: e5f03d644ab6c25b7eb0da0dc1684c7de5c2e6a8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366140"
---
# <a name="compiler-error-c2989"></a>Derleyici Hatası C2989

'class': sınıf türü zaten sınıf olmayan türü olarak bildirildi

Genel bir sınıf veya şablonu bir şablon olmayan veya genel olmayan sınıf yeniden tanımlar. Çakışmaları için üst bilgi dosyaları denetleyin.

Aşağıdaki örnek, C2989 oluşturur:

```cpp
// C2989.cpp
// compile with: /c
class C{};

template <class T>
class C{};  // C2989
class C2{};
```

C2989, genel türler kullanırken da meydana gelebilir:

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