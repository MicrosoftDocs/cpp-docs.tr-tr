---
title: Derleyici hatası C2728
ms.date: 11/04/2016
f1_keywords:
- C2728
helpviewer_keywords:
- C2728
ms.assetid: 65635f91-1cd1-46e4-9ad7-14726d0546af
ms.openlocfilehash: ac9efa88fc4ab17a656172c44de2e49e82108108
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755674"
---
# <a name="compiler-error-c2728"></a>Derleyici hatası C2728

' Type ': yerel bir dizi bu türü içeremez

Dizi oluşturma sözdizimi yönetilen veya WinRT nesnelerinin bir dizisini oluşturmak için kullanıldı. Yerel dizi sözdizimini kullanarak yönetilen veya WinRT nesnelerinden oluşan bir dizi oluşturamazsınız.

Daha fazla bilgi için bkz. [dizi](../../extensions/arrays-cpp-component-extensions.md).

Aşağıdaki örnek C2728 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2728.cpp
// compile with: /clr

int main() {
   int^ arr[5];   // C2728

   // try the following line instead
   array<int>^arr2;
}
```
