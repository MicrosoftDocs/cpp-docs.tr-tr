---
title: Derleyici Hatası C2728
ms.date: 11/04/2016
f1_keywords:
- C2728
helpviewer_keywords:
- C2728
ms.assetid: 65635f91-1cd1-46e4-9ad7-14726d0546af
ms.openlocfilehash: 1fbbc3d63386ebe98a447de8b7166a5263d2168f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59778793"
---
# <a name="compiler-error-c2728"></a>Derleyici Hatası C2728

'type': yerel bir dizi bu türü içeremez

Dizi oluşturma sözdizimi, bir dizi oluşturmak için kullanılan yönetilen veya WinRT nesneleri. Bir dizi oluşturamazsınız yönetilen veya yerel bir dizi söz dizimini kullanarak WinRT nesneleri.

Daha fazla bilgi için [dizi](../../extensions/arrays-cpp-component-extensions.md).

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
