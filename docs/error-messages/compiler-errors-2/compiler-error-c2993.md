---
title: Derleyici Hatası C2993
ms.date: 11/04/2016
f1_keywords:
- C2993
helpviewer_keywords:
- C2993
ms.assetid: 4ffd2b78-654b-46aa-95a6-b62101cf91c8
ms.openlocfilehash: 5be4836332f67f2064f60a3b058db159a18ca1e0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605034"
---
# <a name="compiler-error-c2993"></a>Derleyici Hatası C2993

'identifier': tür olmayan şablon parametresi 'parametresi' için geçersiz tür

Bir yapı veya birleşim bağımsız değişkeni bir şablonla bildiremezsiniz. Yapılar ve birleşimler şablon parametreleri olarak geçirmek için işaretçiler kullanma.

Aşağıdaki örnek, C2993 oluşturur:

```
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

Bu hata ayrıca Visual Studio .NET 2003'te yapıldığı derleyici uyumluluğu iş sonucu olarak oluşturulacak: kayan nokta tür olmayan şablon parametreleri artık izin verilir. C++ Standart kayan nokta tür olmayan şablon parametreleri izin vermez.

Bir işlev şablonu ise, kullanmak kayan geçirmek için bir işlev bağımsız değişkeni tür olmayan şablon parametresi (Bu kod Visual C++ Visual Studio .NET 2003 ve Visual Studio sürümlerinde geçerli olacaktır) üzerine gelin. Bir sınıf şablonunun ise, kolay geçici çözüm yoktur.

```
// C2993b.cpp
// compile with: /c
template<class T, float f> void func(T) {}   // C2993

// OK
template<class T>   void func2(T, float) {}
```