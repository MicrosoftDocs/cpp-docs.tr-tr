---
title: Derleyici hatası C2937
ms.date: 11/04/2016
f1_keywords:
- C2937
helpviewer_keywords:
- C2937
ms.assetid: 95671ca3-79f7-4b56-a5f2-a92296da1629
ms.openlocfilehash: 615b4fbb639249179d34f0d92b4891aadc0ff3a8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233411"
---
# <a name="compiler-error-c2937"></a>Derleyici hatası C2937

' class ': tür sınıfı kimliği genel bir typedef olarak yeniden tanımlandı

Genel veya şablon sınıfını küresel olarak kullanamazsınız **`typedef`** .

Aşağıdaki örnek C2937 oluşturur:

```cpp
// C2937.cpp
// compile with: /c
template<class T>
struct TC { };
typedef int TC<int>;   // C2937
typedef TC<int> c;   // OK
```

C2937, genel türler kullanılırken de oluşabilir:

```cpp
// C2937b.cpp
// compile with: /clr
generic<class T>
ref struct GC { };
typedef int GC<int>;   // C2937
typedef GC<int> xx;   // OK
```
