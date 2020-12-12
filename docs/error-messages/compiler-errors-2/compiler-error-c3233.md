---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3233'
title: Derleyici hatası C3233
ms.date: 11/04/2016
f1_keywords:
- C3233
helpviewer_keywords:
- C3233
ms.assetid: a9210830-1136-4f02-ba41-030c85f93547
ms.openlocfilehash: 825269c96e596a53b9f1852ce50741f9a5d70e6c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312000"
---
# <a name="compiler-error-c3233"></a>Derleyici hatası C3233

' Type ': genel tür parametresi zaten kısıtlanmış

Bir genel parametrenin birden fazla yan tümce içinde sınırlandırılmasına yönelik geçerli değildir `where` .

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
