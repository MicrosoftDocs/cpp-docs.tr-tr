---
title: Derleyici Hatası C3168
ms.date: 11/04/2016
f1_keywords:
- C3168
helpviewer_keywords:
- C3168
ms.assetid: 4c36fcfb-c351-48ff-b4eb-78d2aa1b4d55
ms.openlocfilehash: f39160cc09825c6d87d56ff5ba80d21a35f41e12
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174167"
---
# <a name="compiler-error-c3168"></a>Derleyici Hatası C3168

'type': numaralandırma için temeldeki tür geçersiz

Arka plandaki için belirtilen türü `enum` türü geçerli değildi. Temel alınan türü bir tamsayı C++ türü veya karşılık gelen bir CLR türü olması gerekir.

Aşağıdaki örnek, C3168 oluşturur:

```
// C3168.cpp
// compile with: /clr /c
ref class G{};

enum class E : G { e };   // C3168
enum class F { f };   // OK
```
