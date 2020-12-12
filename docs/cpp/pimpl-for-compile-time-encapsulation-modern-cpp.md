---
description: Daha fazla bilgi Için bkz. Compile-Time kapsülleme Için Pımpl (Modern C++)
title: Derleme Zamanı Kapsüllemesi için Pimpl (Modern C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
ms.openlocfilehash: 95d1ca4f377cc911e862885e86f846d8536d3b1f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145892"
---
# <a name="pimpl-for-compile-time-encapsulation-modern-c"></a>Derleme Zamanı Kapsüllemesi için Pimpl (Modern C++)

*Pımpl iDom* , uygulamayı gizlemek, kuponu en aza indirmek ve arabirimleri ayırmak için modern bir C++ tekniğidir. Pımpl, "uygulama işaretçisi" için kısadır. Kavramı zaten biliyor, ancak Chesişe Al veya derleyici güvenlik duvarı deyimidir gibi diğer adlara göre de biliyor olabilirsiniz.

## <a name="why-use-pimpl"></a>Pımpl neden kullanılmalıdır?

Pımpl iDom 'nin yazılım geliştirme yaşam döngüsünü nasıl iyileştirebileceğimizi aşağıda bulabilirsiniz:

- Derleme bağımlılıklarının en az seçimi.

- Arabirim ve uygulamanın ayrımı.

- Taşınabilirlik.

## <a name="pimpl-header"></a>Pımpl üstbilgisi

```cpp
// my_class.h
class my_class {
   //  ... all public and protected stuff goes here ...
private:
   class impl; unique_ptr<impl> pimpl; // opaque type here
};
```

Pımpl iDom, basamaklı des ve Brittle nesne düzenlerini yeniden derlemeyi önler. Popüler türler (geçişli) için oldukça uygundur.

## <a name="pimpl-implementation"></a>Pımpl uygulama

`impl`Sınıfını. cpp dosyasında tanımlayın.

```cpp
// my_class.cpp
class my_class::impl {  // defined privately here
  // ... all private data and functions: all of these
  //     can now change without recompiling callers ...
};
my_class::my_class(): pimpl( new impl )
{
  // ... set impl values ...
}
```

## <a name="best-practices"></a>En iyi uygulamalar

Oluşturma olmayan takas özelleştirmesi için destek eklenip eklenmeyeceğini düşünün.

## <a name="see-also"></a>Ayrıca bkz.

[C++ ' a geri hoş geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ dil başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ standart kitaplığı](../standard-library/cpp-standard-library-reference.md)
