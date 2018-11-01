---
title: Derleyici Hatası C2728
ms.date: 11/04/2016
f1_keywords:
- C2728
helpviewer_keywords:
- C2728
ms.assetid: 65635f91-1cd1-46e4-9ad7-14726d0546af
ms.openlocfilehash: 3e3584d5e9166bb57e3be56e33f0198cacace7c1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615182"
---
# <a name="compiler-error-c2728"></a>Derleyici Hatası C2728

'type': yerel bir dizi bu türü içeremez

Dizi oluşturma sözdizimi, bir dizi oluşturmak için kullanılan yönetilen veya WinRT nesneleri. Bir dizi oluşturamazsınız yönetilen veya yerel bir dizi söz dizimini kullanarak WinRT nesneleri.

Daha fazla bilgi için [dizi](../../windows/arrays-cpp-component-extensions.md).

Aşağıdaki örnek, C2728 oluşturur ve bu sorunun nasıl gösterir:

```
// C2728.cpp
// compile with: /clr

int main() {
   int^ arr[5];   // C2728

   // try the following line instead
   array<int>^arr2;
}
```
