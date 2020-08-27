---
title: Derleyici hatası C2705
description: Microsoft C/C++ derleyicisi hata C2705 açıklar.
ms.date: 08/25/2020
f1_keywords:
- C2705
helpviewer_keywords:
- C2705
ms.assetid: 29249ea3-4ea7-4105-944b-bdb83e8d6852
ms.openlocfilehash: 40d0f70ee379f5d1347b7443817713a53e097f89
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898751"
---
# <a name="compiler-error-c2705"></a>Derleyici hatası C2705

> '*etiket*': ' Exception Handler bloğu ' kapsamına geçersiz zıplama

## <a name="remarks"></a>Açıklamalar

Yürütme **`try`** / **`catch`** ,, **`__try`** / **`__except`** veya **`__try`** / **`__finally`** blok içindeki bir etikete atlar. Derleyici bu davranışa izin vermez. Daha fazla bilgi için bkz. [özel durum işleme](../../cpp/exception-handling-in-visual-cpp.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C2705 oluşturur:

```cpp
// C2705.cpp
int main() {
goto trouble;
   __try {
      trouble: ;   // C2705
   }
   __finally {}

   // try the following line instead
   // trouble: ;
}
```
