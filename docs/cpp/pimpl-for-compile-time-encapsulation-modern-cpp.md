---
title: Derleme Zamanı Kapsüllemesi için Pimpl (Modern C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
ms.openlocfilehash: 6e114e2802dd4b2e5d1497867e2224be90c4752d
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220692"
---
# <a name="pimpl-for-compile-time-encapsulation-modern-c"></a>Derleme Zamanı Kapsüllemesi için Pimpl (Modern C++)

*Derleme pimpl deyim* bağlantısından en aza indirmek ve arabirimleri ayırmak için uygulama gizlemek için modern bir C++ Teknik. Derleme Pimpl kısaltması "uygulaması." işaretçisidir Zaten kavramı hakkında bilgi sahibi olmanız ancak Cheshire Cat veya derleyici güvenlik duvarı deyim gibi diğer adlarıyla bildirin.

## <a name="why-use-pimpl"></a>Derleme pimpl neden kullanmalısınız?

Derleme pimpl deyim yazılım geliştirme yaşam döngüsünün nasıl geliştireceğiniz aşağıda verilmiştir:

- Derleme bağımlılıkları küçültme.

- Arabirim ve uygulama ayrılması.

- Taşınabilirlik.

## <a name="pimpl-header"></a>Derleme Pimpl üstbilgisi

```cpp
// my_class.h
class my_class {
   //  ... all public and protected stuff goes here ...
private:
   class impl; unique_ptr<impl> pimpl; // opaque type here
};
```

Derleme pimpl deyim yeniden basamaklar ve kırılgan nesne düzeni önler. De (Geçişli) popüler türleri için de uygundur.

## <a name="pimpl-implementation"></a>Derleme Pimpl uygulama

Tanımlama `impl` .cpp dosyası sınıfta.

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

## <a name="best-practices"></a>Önerilen uygulamalar

Oluşturmayan takas özelleştirmesi için destek eklenip eklenmeyeceğini göz önünde bulundurun.

## <a name="see-also"></a>Ayrıca bkz.

[C++'a (Modern C++) Tekrar Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)
