---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2728'
title: Derleyici hatası C2728
ms.date: 11/04/2016
f1_keywords:
- C2728
helpviewer_keywords:
- C2728
ms.assetid: 65635f91-1cd1-46e4-9ad7-14726d0546af
ms.openlocfilehash: 7ef24dd037f8d765c072a61320da64411248dbc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245310"
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
