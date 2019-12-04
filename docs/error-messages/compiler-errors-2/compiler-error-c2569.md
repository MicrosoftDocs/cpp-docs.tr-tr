---
title: Derleyici hatası C2569
ms.date: 11/04/2016
f1_keywords:
- C2569
helpviewer_keywords:
- C2569
ms.assetid: 092bed1e-f631-436c-9586-7750629f6fac
ms.openlocfilehash: 7299fe8daa1fa0fc6e1291bf8c683b33235e8bbf
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755531"
---
# <a name="compiler-error-c2569"></a>Derleyici hatası C2569

' EnumOrUnion ': enum/Union temel sınıf olarak kullanılamaz

Belirtilen birleşim veya Numaralandırmadaki bir tür türetmeniz gerekiyorsa, UNION veya sabit listesini bir sınıf veya yapı olarak değiştirin.

Aşağıdaki örnek C2569 oluşturur:

```cpp
// C2569.cpp
// compile with: /c
union ubase {};
class cHasPubUBase : public ubase {};   // C2569
// OK
struct sbase {};
class cHasPubUBase : public sbase {};
```
