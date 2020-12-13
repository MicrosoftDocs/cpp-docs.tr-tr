---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4600'
title: Derleyici Uyarısı (düzey 1) C4600
ms.date: 11/04/2016
f1_keywords:
- C4600
helpviewer_keywords:
- C4600
ms.assetid: f023a2a1-7fc4-463f-a434-dc93fcd3f4e9
ms.openlocfilehash: d09aff9137647543cd3e71c0fa1794b37fac83f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341782"
---
# <a name="compiler-warning-level-1-c4600"></a>Derleyici Uyarısı (düzey 1) C4600

\#pragma ' makro adı ': geçerli bir boş olmayan dize bekleniyor

[Pop_macro](../../preprocessor/pop-macro.md) veya [push_macro](../../preprocessor/push-macro.md)bir makro adı gönderdiğinizde ya da seçtiğinizde boş bir dize belirtemezsiniz.

Aşağıdaki örnek C4600 oluşturur:

```cpp
// C4600.cpp
// compile with: /W1
int main()
{
   #pragma push_macro("")   // C4600 passing an empty string
}
```
