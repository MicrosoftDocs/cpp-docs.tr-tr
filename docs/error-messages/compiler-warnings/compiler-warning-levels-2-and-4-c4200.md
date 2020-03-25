---
title: Derleyici Uyarısı (düzey 2 ve 4) C4200
ms.date: 11/04/2016
f1_keywords:
- C4200
helpviewer_keywords:
- C4200
ms.assetid: e44d6073-937f-42b7-acc1-65e802b475c6
ms.openlocfilehash: 4b0750fe50e18214e0841eff6b3459438e9a6aec
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197957"
---
# <a name="compiler-warning-levels-2-and-4-c4200"></a>Derleyici Uyarısı (düzey 2 ve 4) C4200

Standart olmayan uzantı kullanıldı: yapıda/birleşimde Sıfır boyutlu dizi

Bir yapının veya birleşimin sıfır boyutuna sahip bir dizi içerdiğini belirtir.

Sıfır boyutlu bir dizi bildirimi Microsoft uzantısıdır. Bu, bir C++ dosya derlendiğinde bir düzey 2 uyarısı ve bir C dosyası derlendiğinde bir düzey 4 uyarısı oluşmasına neden olur. C++derleme ayrıca şu uyarıyı verir: "UDT Sıfır boyutlu dizi içerdiğinde Copy-ctor veya Copy-atama işleci üretilemiyor." Bu örnek, C4200 uyarı oluşturur:

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
