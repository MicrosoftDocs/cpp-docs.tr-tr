---
title: Derleyici hatası C3233
ms.date: 11/04/2016
f1_keywords:
- C3233
helpviewer_keywords:
- C3233
ms.assetid: a9210830-1136-4f02-ba41-030c85f93547
ms.openlocfilehash: 110d1ef84ca2f558f597afadadbede61a89da20c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751111"
---
# <a name="compiler-error-c3233"></a>Derleyici hatası C3233

' Type ': genel tür parametresi zaten kısıtlanmış

Birden fazla `where` yan tümcesindeki genel bir parametreyi kısıtlamak geçerli değildir.

Aşağıdaki örnek C3233 oluşturur:

```cpp
// C3233.cpp
// compile with: /clr /LD

interface struct C {};
interface struct D {};

generic <class T>
where T : C
where T : D
ref class E {};   // C3233
```
