---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3176'
title: Derleyici hatası C3176
ms.date: 11/04/2016
f1_keywords:
- C3176
helpviewer_keywords:
- C3176
ms.assetid: 6cc8d602-8e15-47a7-b1b5-e93e5d50e271
ms.openlocfilehash: 8dda09ccbe6faa80d77f43c38b2c94427956cc3f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242047"
---
# <a name="compiler-error-c3176"></a>Derleyici hatası C3176

' Type ': yerel değer türü bildirilemez

Bir sınıf, genel kapsamda yalnızca bir değer türü olarak bildirilemez.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3176 oluşturur.

```cpp
// C3176.cpp
// compile with: /clr
int main () {
   enum class C {};   // C3176
}
```
