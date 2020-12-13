---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2993'
title: Derleyici hatası C2993
ms.date: 11/04/2016
f1_keywords:
- C2993
helpviewer_keywords:
- C2993
ms.assetid: 4ffd2b78-654b-46aa-95a6-b62101cf91c8
ms.openlocfilehash: 2c43d4f3e54378d419f1945b1f6b38e9ee4d9758
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136428"
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

Bu hata, Visual Studio .NET 2003 ' de gerçekleştirilen derleyici uyumluluğu işinin sonucu olarak da oluşturulacaktır: kayan nokta türü olmayan şablon parametrelerine artık izin verilmez. C++ standardı kayan nokta türünde olmayan şablon parametrelerine izin vermez.

Bir işlev şablonuysa, kayan nokta türünde olmayan şablon parametresini geçirmek için bir işlev bağımsız değişkeni kullanın (Bu kod Visual Studio .NET 2003 ve Visual C++ Visual Studio .NET sürümlerinde geçerli olur). Bu bir sınıf şablonsa, kolay bir geçici çözüm yoktur.

```cpp
// C2993b.cpp
// compile with: /c
template<class T, float f> void func(T) {}   // C2993

// OK
template<class T>   void func2(T, float) {}
```
