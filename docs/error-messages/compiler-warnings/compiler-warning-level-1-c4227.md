---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4227'
title: Derleyici Uyarısı (düzey 1) C4227
ms.date: 11/04/2016
f1_keywords:
- C4227
helpviewer_keywords:
- C4227
ms.assetid: 78f98374-c00b-4000-aefa-1b1c67b4666b
ms.openlocfilehash: f919f3765836548b7aa7410002facd942b942395
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266332"
---
# <a name="compiler-warning-level-1-c4227"></a>Derleyici Uyarısı (düzey 1) C4227

anakronizm kullanıldı: başvuru üzerindeki niteleyiciler yoksayıldı

C++ başvuruları gibi niteleyicilerin kullanılması **`const`** **`volatile`** , süresi geçmiş bir uygulamadır.

## <a name="example"></a>Örnek

```cpp
// C4227.cpp
// compile with: /W1 /c
int j = 0;
int &const i = j;   // C4227
```
