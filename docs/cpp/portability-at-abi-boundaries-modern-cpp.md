---
title: ABı sınırlarındaki taşınabilirlik
description: Arabirimleri C++ , ikili arabirim sınırlarında C çağırma kuralları için düzleştirin.
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: abbd405e-3038-427c-8c24-e00598f0936a
ms.openlocfilehash: b3b2b217739ff5900c8ef0329ff3e8909a3fe036
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303312"
---
# <a name="portability-at-abi-boundaries"></a>ABı sınırlarındaki taşınabilirlik

İkili arabirim sınırlarında yeterli taşınabilir türler ve kurallar kullanın. "Taşınabilir tür", C yerleşik türü veya yalnızca C yerleşik türlerini içeren bir struct. Sınıf türleri yalnızca, çağıran ve çağrılan düzen, çağırma kuralı vb. için kabul edildiğinde kullanılabilir. Bu yalnızca, her ikisi de aynı derleyici ve derleyici ayarlarıyla derlendiğinde mümkündür.

## <a name="how-to-flatten-a-class-for-c-portability"></a>C taşınabilirlik için bir sınıfı düzleştirme

Çağıranlar başka bir derleyici/dille derleniyorsa, belirli bir çağırma kuralına sahip bir **extern "C"** API 'sine "Düzleştir":

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

[Uygulamasına geri hoş geldinizC++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)
