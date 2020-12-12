---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4518'
title: Derleyici Uyarısı (düzey 1) C4518
ms.date: 11/04/2016
f1_keywords:
- C4518
helpviewer_keywords:
- C4518
ms.assetid: 4ad21004-f076-43fd-99f4-4bf1f9be4c0b
ms.openlocfilehash: 1a04dbcdc62e6758e2b65c6b0ef5aa99a1823ef0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212304"
---
# <a name="compiler-warning-level-1-c4518"></a>Derleyici Uyarısı (düzey 1) C4518

' belirtici ': burada depolama sınıfı veya tür belirticileri beklenmiyor; LIP

Aşağıdaki örnek C4518 oluşturur:

```cpp
// C4518.cpp
// compile with: /c /W1
_declspec(dllexport) extern "C" void MyFunction();   // C4518

extern "C" void MyFunction();   // OK
```
