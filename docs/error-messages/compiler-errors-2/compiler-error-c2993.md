---
title: Derleyici Hatası C2993 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2993
dev_langs:
- C++
helpviewer_keywords:
- C2993
ms.assetid: 4ffd2b78-654b-46aa-95a6-b62101cf91c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 09b3c789cc15d2e146f1c5031003fc74d783e827
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081951"
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