---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2199 arasındaki'
title: Derleyici hatası C2199 arasındaki
ms.date: 11/04/2016
f1_keywords:
- C2199
helpviewer_keywords:
- C2199
ms.assetid: 6a92a1b7-7906-49e6-a31f-e8bffbc7706a
ms.openlocfilehash: e3c1daefb8a8b14c49b42e48c0d46d5a8e638953
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278433"
---
# <a name="compiler-error-c2199"></a>Derleyici hatası C2199 arasındaki

sözdizimi hatası: genel kapsamda ' Identifier (' bulundu mı?)

Belirtilen bağlam bir sözdizimi hatasına neden oldu. Yanlış bildirim söz dizimi olabilir.

Aşağıdaki örnek C2199 arasındaki oluşturur:

```cpp
// C2199.cpp
// compile with: /c
int j = int(1) int(1);   // C2199
int j = 1;   // OK
```
