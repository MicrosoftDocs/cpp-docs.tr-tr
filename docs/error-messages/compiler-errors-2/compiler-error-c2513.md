---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2513'
title: Derleyici hatası C2513
ms.date: 11/04/2016
f1_keywords:
- C2513
helpviewer_keywords:
- C2513
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
ms.openlocfilehash: d1238acd8dc2d56e4757ffb986d4db47c047e76b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212902"
---
# <a name="compiler-error-c2513"></a>Derleyici hatası C2513

' Type ': ' = ' öncesinde hiçbir değişken bildirilmemiş

Tür Belirleyicisi, hiçbir değişken tanımlayıcısı olmadan bildirimde görüntülenir.

Aşağıdaki örnek C2513 oluşturur:

```cpp
// C2513.cpp
int main() {
   int = 9;   // C2513
   int i = 9;   // OK
}
```

Bu hata, Visual Studio .NET 2003 için yapılan bir derleyici uygunluk işinin sonucu olarak da oluşturulabilir: typedef 'in başlatılmasına artık izin verilmiyor. Bir typedef 'in başlatılmasına standart tarafından izin verilmez ve şimdi bir derleyici hatası oluşturur.

```cpp
// C2513b.cpp
// compile with: /c
typedef struct S {
   int m_i;
} S = { 1 };   // C2513
// try the following line instead
// } S;
```

Bir alternatif **`typedef`** , toplama başlatıcısı listesiyle bir değişken tanımlamak için silinecek, ancak bu, türü ile aynı ada sahip bir değişken oluşturacak ve tür adını gizleyecek olduğundan önerilmez.
