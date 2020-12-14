---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2529'
title: Derleyici hatası C2529
ms.date: 11/04/2016
f1_keywords:
- C2529
helpviewer_keywords:
- C2529
ms.assetid: 73a99e55-b91e-488d-9b72-cc80faaeb436
ms.openlocfilehash: 007fa64332e9f7b5eb993f722e66924584d9c342
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302276"
---
# <a name="compiler-error-c2529"></a>Derleyici hatası C2529

' name ': başvuruya başvuru geçersizdir

Bu hata, işaretçi sözdizimi kullanılarak ve bir işaretçiye başvuru bildirerek düzeltilebilir.

Aşağıdaki örnek C2529 oluşturur:

```cpp
// C2529.cpp
// compile with: /c
int i;
int &ri = i;
int &(&rri) = ri;   // C2529
```
