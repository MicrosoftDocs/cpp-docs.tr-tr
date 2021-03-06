---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2864'
title: Derleyici hatası C2864
ms.date: 10/04/2019
f1_keywords:
- C2864
helpviewer_keywords:
- C2864
ms.assetid: d0ca2ad9-90a6-4aef-8511-98a3b414c102
ms.openlocfilehash: 763e70fd3ac988cca94f71feeab975e8b8630402
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305370"
---
# <a name="compiler-error-c2864"></a>Derleyici hatası C2864

> '*üye-adı*': sınıf içi başlatıcısı olan bir statik veri üyesinin geçici olmayan const integral türü olmalıdır

## <a name="remarks"></a>Açıklamalar

**`static`** Tamsayı türü olarak tanımlanan, veya olmayan bir veri üyesini başlatmak için **`volatile`** **`const`** üye tanımı ifadesini kullanın. Bildirimde başlatılamaz.

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
