---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2569'
title: Derleyici hatası C2569
ms.date: 11/04/2016
f1_keywords:
- C2569
helpviewer_keywords:
- C2569
ms.assetid: 092bed1e-f631-436c-9586-7750629f6fac
ms.openlocfilehash: bf6b0670cfd90cadc939010a75f9faa9c7c25c30
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209041"
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
