---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4835'
title: Derleyici Uyarısı (düzey 1) C4835
ms.date: 11/04/2016
f1_keywords:
- C4835
helpviewer_keywords:
- C4835
ms.assetid: d2e44c62-7b0e-4a45-943d-97903e27ed9d
ms.openlocfilehash: ee5d91883bafcac3412962f7e314f2ee00ea8278
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197991"
---
# <a name="compiler-warning-level-1-c4835"></a>Derleyici Uyarısı (düzey 1) C4835

' değişken ': içe aktarılmış verilerin başlatıcısı, yönetilen kod ilk ana bilgisayar derlemesinde yürütülene kadar çalıştırılmayacak

Yönetilen bileşenler arasında verilere erişirken, yerel C++ içeri ve dışarı aktarma mekanizmalarını kullanmanız önerilmez. Bunun yerine, veri üyelerinizi yönetilen bir tür içinde bildirin ve istemcideki meta verilere başvurun `#using` . Daha fazla bilgi için bkz. [#using yönergesi](../../preprocessor/hash-using-directive-cpp.md).

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C4835 oluşturur.

```cpp
// C4835.cpp
// compile with: /W1 /clr /LD
int f() { return 1; }
int n = 9;

__declspec(dllexport) int m = f();   // C4835
__declspec(dllexport) int *p = &n;   // C4835
```

Aşağıdaki örnek, önceki örnekte oluşturulmuş bileşeni kullanır ve bu da değişkenlerin değerinin beklenen şekilde olduğunu gösterir.

```cpp
// C4835_b.cpp
// compile with: /clr C4835.lib
#include <stdio.h>
__declspec(dllimport) int m;
__declspec(dllimport) int *p;

int main() {
   printf("%d\n", m);
   printf("%d\n", p);
}
```

```Output
0
268456008
```
