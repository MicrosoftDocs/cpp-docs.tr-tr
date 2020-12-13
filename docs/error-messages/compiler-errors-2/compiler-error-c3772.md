---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3772'
title: Derleyici hatası C3772
ms.date: 11/04/2016
f1_keywords:
- C3772
helpviewer_keywords:
- C3772
ms.assetid: 63e938d4-088d-41cc-a562-5881a05b5710
ms.openlocfilehash: 679c5bc47e9b31ebf085dec63a46549a10484cac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340131"
---
# <a name="compiler-error-c3772"></a>Derleyici hatası C3772

"ad": geçersiz arkadaş şablonu bildirimi

Bir sınıf şablonu özelleştirmesi arkadaşını bildirmek geçersizdir. Bir sınıf şablonunun açık veya kısmi özelleştirmesi bildiremezsiniz ve aynı ifadede bu özelleşmenin arkadaşını bildirin. *Ad* yer tutucusu geçersiz bildirimi tanımlar.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Bir sınıf şablonu özelleştirmesi arkadaşını bildirme.

- Uygulamanız için uygunsa, sınıf şablonunun bir arkadaşını bildirin veya belirli bir kısmi veya açık özelleşmenin arkadaşını bildirin.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, bir sınıf şablonunun kısmi özelleştirmesi için bir arkadaş bildirdiği için başarısız olur.

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

## <a name="see-also"></a>Ayrıca bkz.

[Şablonlar](../../cpp/templates-cpp.md)<br/>
[Şablon özelleştirmesi](../../cpp/template-specialization-cpp.md)
