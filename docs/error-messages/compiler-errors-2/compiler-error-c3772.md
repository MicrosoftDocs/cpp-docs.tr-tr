---
title: Derleyici Hatası C3772
ms.date: 11/04/2016
f1_keywords:
- C3772
helpviewer_keywords:
- C3772
ms.assetid: 63e938d4-088d-41cc-a562-5881a05b5710
ms.openlocfilehash: 9a72cb9ee5d1d839f6ca5d113c25795f83dab811
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595682"
---
# <a name="compiler-error-c3772"></a>Derleyici Hatası C3772

"name": Geçersiz arkadaş şablonu bildirimi

Bir sınıf şablonu uzmanlığı olan bir arkadaş bildirmek için geçersiz. Bir sınıf şablonunun bir açık veya kısmı özelleştirmesine bildirmek ve aynı deyimde, özelleştirme, bir arkadaş bildirin. *Adı* yer tutucu geçersiz bildirimi tanımlar.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Bir sınıf şablonu uzmanlığı olan bir arkadaş bildirmeyin.

- Uygun, uygulamanız için bir arkadaş sınıf şablonu bildirmek veya belirli bir kısmi veya açık uzmanlığı olan bir arkadaş bildirin.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, bir arkadaş sınıf şablonu kısmi özelleştirmesi, bildirdiğinden başarısız olur.

```cpp
// c3772.cpp
// compile with: /c

// A class template.
    template<class T> class A {};

// A partial specialization of the class template.
    template<class T> class A<T*> {};

// An explicit specialization.
    template<> class A<char>;

class X {
// Invalid declaration of a friend of a partial specialization.
    template<class T> friend class A<T*>; // C3772

// Instead, if it is appropriate for your application, declare a
// friend of the class template. Consequently, all specializations
// of the class template are friends:
//    template<class T> friend class A;
// Or declare a friend of a particular partial specialization:
//    friend class A<int*>;
// Or declare a friend of a particular explicit specialization:
//    friend class A<char>;
};
```

## <a name="see-also"></a>Ayrıca Bkz.

[Şablonlar](../../cpp/templates-cpp.md)<br/>
[Şablon Uzmanlığı](../../cpp/template-specialization-cpp.md)
