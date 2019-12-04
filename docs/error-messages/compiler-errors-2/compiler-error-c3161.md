---
title: Derleyici hatası C3161
ms.date: 11/04/2016
f1_keywords:
- C3161
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
ms.openlocfilehash: 7315dad7959cdd3b950ed814b13be3867399d332
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761822"
---
# <a name="compiler-error-c3161"></a>Derleyici hatası C3161

' interface ': arabirim içinde sınıf, yapı, birleşim veya arabirim iç içe geçirme geçersizdir; sınıf, yapı veya Union içinde iç içe arabirim geçersiz

Bir [__interface](../../cpp/interface.md) yalnızca genel kapsamda veya bir ad alanında yer alabilir. Bir arabirim içinde sınıf, yapı veya birleşim bulunamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3161 oluşturur.

```cpp
// C3161.cpp
// compile with: /c
__interface X {
   __interface Y {};   // C3161 A nested interface
};
```
