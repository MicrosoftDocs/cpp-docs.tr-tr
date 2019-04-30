---
title: Derleyici Uyarısı (düzey 1) C4835
ms.date: 11/04/2016
f1_keywords:
- C4835
helpviewer_keywords:
- C4835
ms.assetid: d2e44c62-7b0e-4a45-943d-97903e27ed9d
ms.openlocfilehash: 0427a97a9e368a19a40a8d1a552f7713e36f831e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62380857"
---
# <a name="compiler-warning-level-1-c4835"></a>Derleyici Uyarısı (düzey 1) C4835

'variable': dışarı aktarılan veriler için Başlatıcı, önce yönetilen kod ana bilgisayar derlemesinde yürütülene kadar çalıştırılmayacak

Yönetilen bileşenleri arasında veri erişirken değil yerel C++ alma kullanın ve dışarı aktarma mekanizması önerilir. Bunun yerine, bir yönetilen türün içinde veri üyeleri bildirme ve meta veriler ile başvuru `#using` istemci. Daha fazla bilgi için [#using yönergesi](../../preprocessor/hash-using-directive-cpp.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4835 oluşturur.

```
// C4835.cpp
// compile with: /W1 /clr /LD
int f() { return 1; }
int n = 9;

__declspec(dllexport) int m = f();   // C4835
__declspec(dllexport) int *p = &n;   // C4835
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, önceki örnekte, değişkenlerin değerini beklendiği gibi olduğunu gösteren yerleşik bileşeni kullanır.

```
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