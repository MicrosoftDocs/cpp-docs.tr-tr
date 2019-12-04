---
title: Derleyici hatası C2513
ms.date: 11/04/2016
f1_keywords:
- C2513
helpviewer_keywords:
- C2513
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
ms.openlocfilehash: 093a5856fdcfa6311fcef93214672b035c91b4fc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746532"
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

Diğer bir seçenek de toplu Başlatıcı listesi olan bir değişken tanımlamak üzere `typedef` silinecek, ancak bu, türü ile aynı ada sahip bir değişken oluşturacak ve tür adını gizleyecek olduğundan önerilmez.
