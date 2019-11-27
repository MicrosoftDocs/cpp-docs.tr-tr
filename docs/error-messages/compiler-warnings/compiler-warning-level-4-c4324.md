---
title: Derleyici Uyarısı (düzey 4) C4324
ms.date: 11/04/2016
f1_keywords:
- C4324
helpviewer_keywords:
- C4324
ms.assetid: 420fa929-d9c0-40b4-8808-2d8ad3ca8090
ms.openlocfilehash: 02803e165255b563df5a8b6136198f1f49e9f65d
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541081"
---
# <a name="compiler-warning-level-4-c4324"></a>Derleyici Uyarısı (düzey 4) C4324

' struct_name ': __declspec nedeniyle yapı dolduruldu (align ())

Bir yapının sonuna doldurma eklendi Çünkü bir [__declspec (align)](../../cpp/align-cpp.md) değeri belirttiniz.

Örneğin, aşağıdaki kod C4324 oluşturur:

```cpp
// C4324.cpp
// compile with: /W4
struct __declspec(align(32)) A
{
   char a;
};   // C4324

int main()
{
}
```