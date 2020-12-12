---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4324'
title: Derleyici Uyarısı (düzey 4) C4324
ms.date: 11/04/2016
f1_keywords:
- C4324
helpviewer_keywords:
- C4324
ms.assetid: 420fa929-d9c0-40b4-8808-2d8ad3ca8090
ms.openlocfilehash: 96554085fa63f4a4f91b954c1f32960b19f1dc6c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294554"
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
