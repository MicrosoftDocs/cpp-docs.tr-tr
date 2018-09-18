---
title: Derleyici Hatası C2728 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2728
dev_langs:
- C++
helpviewer_keywords:
- C2728
ms.assetid: 65635f91-1cd1-46e4-9ad7-14726d0546af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fe901a5798028378e6d84a807826b42cae0d64d8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036175"
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
