---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3168'
title: Derleyici hatası C3168
ms.date: 11/04/2016
f1_keywords:
- C3168
helpviewer_keywords:
- C3168
ms.assetid: 4c36fcfb-c351-48ff-b4eb-78d2aa1b4d55
ms.openlocfilehash: a6b9708ebb9c7fe3d9d6be7d73c24b92b1e8c6eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242255"
---
# <a name="compiler-error-c3168"></a>Derleyici hatası C3168

' Type ': sabit listesi için temeldeki tür geçersiz

Tür için belirttiğiniz temel tür **`enum`** geçerli değil. Temel alınan tür, bir integral C++ türü veya karşılık gelen bir CLR türü olmalıdır.

Aşağıdaki örnek C3168 oluşturur:

```cpp
// C3168.cpp
// compile with: /clr /c
ref class G{};

enum class E : G { e };   // C3168
enum class F { f };   // OK
```
