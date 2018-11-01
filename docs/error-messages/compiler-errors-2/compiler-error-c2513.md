---
title: Derleyici Hatası C2513
ms.date: 11/04/2016
f1_keywords:
- C2513
helpviewer_keywords:
- C2513
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
ms.openlocfilehash: 13840246a5dc6a1c1bdbcb55dc47f212ee353d81
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50561209"
---
# <a name="compiler-error-c2513"></a>Derleyici Hatası C2513

'type': hiçbir değişken bildirimi '=' öncesinde

Tür tanımlayıcısına sahip hiçbir değişken tanımlayıcının bildirimini görüntülenir.

Aşağıdaki örnek, C2513 oluşturur:

```
// C2513.cpp
int main() {
   int = 9;   // C2513
   int i = 9;   // OK
}
```

Bu hata, Visual Studio .NET 2003'te yapılan bir derleyici uyumluluğu iş sonucu olarak da oluşturulabilir: başlatma artık izin verilen bir TypeDef. Bir TypeDef başlatma standart tarafından izin verilmiyor ve artık bir derleyici hatasına neden olur.

```
// C2513b.cpp
// compile with: /c
typedef struct S {
   int m_i;
} S = { 1 };   // C2513
// try the following line instead
// } S;
```

Silmek için bir alternatif olabilir `typedef` bu tür olarak aynı ada sahip bir değişken oluşturun ve tür adı gizlemek için toplu başlatıcı listesi, ancak bu bir değişkeni tanımlamak için önerilmez.