---
title: Derleyici hatası C2864
ms.date: 10/04/2019
f1_keywords:
- C2864
helpviewer_keywords:
- C2864
ms.assetid: d0ca2ad9-90a6-4aef-8511-98a3b414c102
ms.openlocfilehash: 122e0455f84d8940eda04f3968e883dd1f0cd444
ms.sourcegitcommit: c51b2c665849479fa995bc3323a22ebe79d9d7ce
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/07/2019
ms.locfileid: "71998660"
---
# <a name="compiler-error-c2864"></a>Derleyici hatası C2864

> '*üye-adı*': sınıf içi başlatıcısı olan bir statik veri üyesinin geçici olmayan const integral türü olmalıdır

## <a name="remarks"></a>Açıklamalar

`volatile`,`const`olmayan veya tam sayı türü olarak tanımlanan bir `static` veri üyesini başlatmak için üye tanımı ifadesini kullanın. Bildirimde başlatılamaz.

## <a name="example"></a>Örnek

Bu örnek C2864 oluşturur:

```cpp
// C2864.cpp
// compile with: /c
class B  {
private:
   int a = 3;   // OK
   static int b = 3;   // C2864
   volatile static int c = 3;   // C2864
   volatile static const int d = 3;   // C2864
   static const long long e = 3;   // OK
   static const double f = 3.33;   // C2864
};
```

Bu örnek C2864 hatasının nasıl giderileceğini gösterir:

```cpp
// C2864b.cpp
// compile with: /c
class C  {
private:
   int a = 3;
   static int b; // = 3; C2864
   volatile static int c; // = 3; C2864
   volatile static const int d; // = 3; C2864
   static const long long e = 3;
   static const double f; // = 3.33; C2864
};

// Initialize static volatile, non-const, or non-integral
// data members when defined, not when declared:
int C::b = 3;
volatile int C::c = 3;
volatile const int C::d = 3;
const double C::f = 3.33;
```
