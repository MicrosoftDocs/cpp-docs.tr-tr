---
title: Derleme Zamanı Kapsüllemesi için Pimpl (Modern C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
ms.openlocfilehash: f1eb06ad3a52be486f085babf699677951b1ee71
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245183"
---
# <a name="pimpl-for-compile-time-encapsulation-modern-c"></a>Derleme Zamanı Kapsüllemesi için Pimpl (Modern C++)

*Pımpl iDom* , uygulamayı gizlemek, C++ kuponu en aza indirmek ve arabirimleri ayırmak için modern bir tekniktir. Pımpl, "uygulama işaretçisi" için kısadır. Kavramı zaten biliyor, ancak Chesişe Al veya derleyici güvenlik duvarı deyimidir gibi diğer adlara göre de biliyor olabilirsiniz.

## <a name="why-use-pimpl"></a>Pımpl neden kullanılmalıdır?

Pımpl iDom 'nin yazılım geliştirme yaşam döngüsünü nasıl iyileştirebileceğimizi aşağıda bulabilirsiniz:

- Derleme bağımlılıklarının en az seçimi.

- Arabirim ve uygulamanın ayrımı.

- Kolaylığı.

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

. Cpp dosyasında `impl` sınıfını tanımlayın.

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

[Uygulamasına geri hoş geldinizC++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)
