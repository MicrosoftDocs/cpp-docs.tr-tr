---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 2 ve 4) C4200'
title: Derleyici Uyarısı (düzey 2 ve 4) C4200
ms.date: 11/04/2016
f1_keywords:
- C4200
helpviewer_keywords:
- C4200
ms.assetid: e44d6073-937f-42b7-acc1-65e802b475c6
ms.openlocfilehash: 7068e98303049db4e64e46abbd9dae14c11395f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234351"
---
# <a name="compiler-warning-levels-2-and-4-c4200"></a>Derleyici Uyarısı (düzey 2 ve 4) C4200

Standart olmayan uzantı kullanıldı: yapıda/birleşimde Sıfır boyutlu dizi

Bir yapının veya birleşimin sıfır boyutuna sahip bir dizi içerdiğini belirtir.

Sıfır boyutlu bir dizi bildirimi Microsoft uzantısıdır. Bu, bir C++ dosyası derlendiğinde düzey 2 uyarısına ve C dosyası derlendiğinde düzey 4 uyarısına neden olur. C++ derlemesi de şu uyarıyı veriyor: "UDT Sıfır boyutlu dizi içerdiğinde Copy-ctor veya kopya atama işleci üretilemiyor." Bu örnek, C4200 uyarı oluşturur:

```cpp
// C4200.cpp
// compile by using: cl /W4 c4200.cpp
struct A {
    int a[0];  // C4200
};
int main() {
}
```

Bu standart olmayan uzantı genellikle değişken uzunlukta olan dış veri yapıları ile kod arayüzü için kullanılır. Bu senaryo kodunuza geçerliyse, uyarıyı devre dışı bırakabilirsiniz:

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
