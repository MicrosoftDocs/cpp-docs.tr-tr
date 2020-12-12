---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2470'
title: Derleyici hatası C2470
ms.date: 11/04/2016
f1_keywords:
- C2470
helpviewer_keywords:
- C2470
ms.assetid: e17d2cb8-b84c-447c-976a-625f0c96f3fe
ms.openlocfilehash: 90a57f02022044aca7b4062ea287eae213c26f74
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164516"
---
# <a name="compiler-error-c2470"></a>Derleyici hatası C2470

' function ': işlev tanımı gibi görünüyor ancak hiçbir parametre listesi yok; görünen gövde atlanıyor

Bir işlev tanımında bağımsız değişken listesi eksik.

Aşağıdaki örnek C2470 oluşturur:

```cpp
// C2470.cpp
int MyFunc {};  // C2470
void MyFunc2() {};  //OK

int main(){
   MyFunc();
   MyFunc2();
}
```
