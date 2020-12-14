---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3277'
title: Derleyici hatası C3277
ms.date: 11/04/2016
f1_keywords:
- C3277
helpviewer_keywords:
- C3277
ms.assetid: 8ac5f476-e30c-4879-92c6-f03cdbd74045
ms.openlocfilehash: ca04074dd077c63355f7da9a6a5feabcc0d03fac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228995"
---
# <a name="compiler-error-c3277"></a>Derleyici hatası C3277

yönetilmeyen ' Enum ' numaralandırması yönetilen ' Type ' içinde tanımlanamaz

Bir numaralandırma, yönetilen bir tür içinde yanlış tanımlanmış.

Aşağıdaki örnek C3277 oluşturur:

```cpp
// C3277a.cpp
// compile with: /clr
ref class A
{
   enum E {e1,e2};   // C3277
   // try the following line instead
   // enum class E {e1,e2};
};

int main()
{
}
```
