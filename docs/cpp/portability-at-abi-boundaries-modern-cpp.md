---
title: ABI Sınırlarında Taşınabilirlik (Modern C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: abbd405e-3038-427c-8c24-e00598f0936a
ms.openlocfilehash: 12f60b92e71c15a94546e5b099c3b49e3685b68b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549961"
---
# <a name="portability-at-abi-boundaries-modern-c"></a>ABI Sınırlarında Taşınabilirlik (Modern C++)

İkili arabirimi sınırlarında yeterince Taşınabilir türler ve kuralları kullanın. Bir "taşınabilir" C yerleşik bir tür ya da yalnızca C yerleşik türler içeren bir yapı türüdür. Sınıf türleri yalnızca çağırma kuralı, vb. Düzen, çağıran ve çağrılan kabul ettiğinizde kullanılabilir. Bu yalnızca her ikisi de aynı derleyici ve derleyici ayarları ile derlendiğinde mümkündür.

## <a name="how-to-flatten-a-class-for-c-portability"></a>Bir sınıf C taşınabilirliği için düzleştirilecek nasıl

Ne zaman çağıranlar başka bir derleyici/dili ile derlenmiş ve ardından "dönüştürme" bir **extern "C"** API'si ile belirli bir çağırma kuralı:

```cpp
// class widget {
//   widget();
//   ~widget();
//   double method( int, gadget& );
// };
extern "C" {        // functions using explicit "this"
   struct widget;   // opaque type (forward declaration only)
   widget* STDCALL widget_create();      // constructor creates new "this"
   void STDCALL widget_destroy(widget*); // destructor consumes "this"
   double STDCALL widget_method(widget*, int, gadget*); // method uses "this"
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ tekrar Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)