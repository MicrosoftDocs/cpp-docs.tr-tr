---
title: Derleyici Hatası C3772 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3772
dev_langs:
- C++
helpviewer_keywords:
- C3772
ms.assetid: 63e938d4-088d-41cc-a562-5881a05b5710
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: db40c71001e34cc24c19410006cd39f658718c14
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048766"
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
