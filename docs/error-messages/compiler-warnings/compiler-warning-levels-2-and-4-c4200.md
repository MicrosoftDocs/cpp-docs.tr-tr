---
title: Derleyici Uyarısı (Düzey 2 ve 4) C4200
ms.date: 11/04/2016
f1_keywords:
- C4200
helpviewer_keywords:
- C4200
ms.assetid: e44d6073-937f-42b7-acc1-65e802b475c6
ms.openlocfilehash: 56a2ba641df610519949f64f6feeca18d9a99e93
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519814"
---
# <a name="compiler-warning-levels-2-and-4-c4200"></a>Derleyici Uyarısı (Düzey 2 ve 4) C4200

Standart olmayan uzantı kullanıldı: yapıda/birleşimde sıfır boyutlu dizi

Bir yapı veya birleşim sıfır boyuta sahip bir dizi içerdiğini gösterir.

Bir sıfır boyutlu dizi bildirimi bir Microsoft uzantısıdır. Bir C dosyası derlendiğinde bu C++ dosyası derlendiğinde bir düzey 2 uyarı ve düzey 4 uyarısı neden olur. C++ derlemesini Ayrıca bu uyarıyı verir: "bir sıfır boyutlu dizi UDT içeren copy ctor veya kopya atama işleci oluşturulamıyor." Bu örnek, uyarı C4200 oluşturur:

```cpp
// C4200.cpp
// compile by using: cl /W4 c4200.cpp
struct A {
    int a[0];  // C4200
};
int main() {
}
```

Bu standart olmayan uzantı, genellikle arabirimi koduna sahip bir değişken uzunluklu dış veri yapıları ile kullanılır. Bu senaryo için kodunuzu geçerliyse, uyarıyı devre dışı bırakabilirsiniz:

## <a name="example"></a>Örnek

```cpp
// C4200b.cpp
// compile by using: cl /W4 c4200a.cpp
#pragma warning(disable : 4200)
struct A {
    int a[0];
};
int main() {
}
```