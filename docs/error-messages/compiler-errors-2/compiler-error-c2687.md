---
title: Derleyici hatası C2687
ms.date: 11/04/2016
f1_keywords:
- C2687
helpviewer_keywords:
- C2687
ms.assetid: 1d24b24a-cd0f-41cc-975c-b08dcfb7f402
ms.openlocfilehash: f3e728033a3230d628242aab341377be2f6670ca
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760263"
---
# <a name="compiler-error-c2687"></a>Derleyici hatası C2687

' Type ': özel durum bildirimi ' void ' olamaz veya tamamlanmamış bir tür ya da işaretçi ya da eksik bir tür için başvuru ya da başvuru içeremez

Bir türün bir özel durum bildiriminin parçası olması için, tanımlanmalıdır ve void olmalıdır.

Aşağıdaki örnek C2687 oluşturur:

```cpp
// C2687.cpp
class C;

int main() {
   try {}
   catch (C) {}   // C2687 error
}
```

Olası çözüm:

```cpp
// C2687b.cpp
// compile with: /EHsc
class C {};

int main() {
   try {}
   catch (C) {}
}
```
