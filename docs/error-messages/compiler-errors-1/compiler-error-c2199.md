---
title: Derleyici hatası C2199 arasındaki
ms.date: 11/04/2016
f1_keywords:
- C2199
helpviewer_keywords:
- C2199
ms.assetid: 6a92a1b7-7906-49e6-a31f-e8bffbc7706a
ms.openlocfilehash: 8bd6d587d28b8e7c190f7d3d58448fda501796cf
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758989"
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
