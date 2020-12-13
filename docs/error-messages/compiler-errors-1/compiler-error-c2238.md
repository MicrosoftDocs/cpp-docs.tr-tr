---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2238'
title: Derleyici hatası C2238
ms.date: 11/04/2016
f1_keywords:
- C2238
helpviewer_keywords:
- C2238
ms.assetid: 3d53060c-d6b7-4603-b9cf-d7c65eb64cd2
ms.openlocfilehash: 90c5eb840c300aa18b06f49a7e160c6cb7bd8e9e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338750"
---
# <a name="compiler-error-c2238"></a>Derleyici hatası C2238

' token ' öncesinde beklenmeyen belirteç (ler)

Yanlış bir belirteç bulundu.

Aşağıdaki örnek C2238 oluşturur:

```cpp
// C2238.cpp
// compile with: /c
class v {
virtual: int vvv;   // C2238
};
```
