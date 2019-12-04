---
title: Derleyici hatası C2993
ms.date: 11/04/2016
f1_keywords:
- C2993
helpviewer_keywords:
- C2993
ms.assetid: 4ffd2b78-654b-46aa-95a6-b62101cf91c8
ms.openlocfilehash: 5aa0d27b2d469f53ec521f587172398b7d4c2d1b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761237"
---
# <a name="compiler-error-c2993"></a>Derleyici hatası C2993

' tanımlayıcı ': tür olmayan şablon parametresi ' Parameter ' için geçersiz tür

Yapı veya birleşim bağımsız değişkeniyle bir şablon bildiremezsiniz. Yapıları ve birleşimleri şablon parametreleri olarak geçirmek için işaretçiler kullanın.

Aşağıdaki örnek C2993 oluşturur:

```cpp
// C2993.cpp
// compile with: /c
// C2993 expected
struct MyStruct {
   int a;char b;
};

template <class T, struct MyStruct S>   // C2993

// try the following line instead
// template <class T, struct MyStruct * S>
class CMyClass {};
```

Bu hata, Visual Studio .NET 2003 ' de gerçekleştirilen derleyici uyumluluğu işinin sonucu olarak da oluşturulacaktır: kayan nokta türü olmayan şablon parametrelerine artık izin verilmez. Standart C++ , kayan nokta türünde olmayan şablon parametrelerine izin vermez.

Bir işlev şablonuysa, kayan nokta türünde olmayan şablon parametresini geçirmek için bir işlev bağımsız değişkeni kullanın (Visual Studio .NET 2003 ve Visual Studio .NET sürümlerinde bu kod geçerli olur C++). Bu bir sınıf şablonsa, kolay bir geçici çözüm yoktur.

```cpp
// C2993b.cpp
// compile with: /c
template<class T, float f> void func(T) {}   // C2993

// OK
template<class T>   void func2(T, float) {}
```
