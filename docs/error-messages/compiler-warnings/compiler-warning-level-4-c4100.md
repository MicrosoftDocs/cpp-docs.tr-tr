---
title: Derleyici Uyarısı (düzey 4) C4100
ms.date: 11/04/2016
f1_keywords:
- C4100
helpviewer_keywords:
- C4100
ms.assetid: 478ed97d-e502-49e4-9afb-ac2a6c61194b
ms.openlocfilehash: bcd51c66359d0553b7657d85f5b45ee22d4648ff
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991653"
---
# <a name="compiler-warning-level-4-c4100"></a>Derleyici Uyarısı (düzey 4) C4100

"tanımlayıcı" : başvurulmayan biçimsel parametre

Biçimsel parametreye işlev gövdesinde başvurulmuyor. Başvurulmayan parametre yok sayıldı.

Teme öğe türünün başka bir başvurulmayan parametresinde kod, bir yok edici çağırdığında C4100 de görünebilir.  Bu, Microsoft C++ derleyicisi kısıtlamasıdır.

Şu örnek C4100 oluşturur:

```cpp
// C4100.cpp
// compile with: /W4
void func(int i) {   // C4100, delete the unreferenced parameter to
                     //resolve the warning
   // i;   // or, add a reference like this
}

int main()
{
   func(1);
}
```
