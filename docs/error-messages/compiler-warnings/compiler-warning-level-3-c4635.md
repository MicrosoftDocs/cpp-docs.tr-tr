---
title: Derleyici Uyarısı (düzey 3) C4635
ms.date: 11/04/2016
f1_keywords:
- C4635
helpviewer_keywords:
- C4635
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
ms.openlocfilehash: b6fd45dc6c28c0d12eb2b2991f8a087b1841d1a9
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/19/2019
ms.locfileid: "74189140"
---
# <a name="compiler-warning-level-3-c4635"></a>Derleyici Uyarısı (düzey 3) C4635

XML belgesi Açıklama hedefi: Hatalı biçimlendirilmiş XML: Reason

Derleyici XML etiketleriyle ilgili bir sorun buldu.  Sorunu giderip yeniden derleyin

Aşağıdaki örnek C4635 oluşturur:

```cpp
// C4635.cpp
// compile with: /doc /clr /W3 /c
/// <summary>
/// The contents of the folder have changed.
/// <summary/>   // C4635

// try the following line instead
// /// </summary>
public ref class Test {};
```

Bu örneğe ilişkin çıktının şöyle göründüğünü unutmayın: **bitiş etiketi ' Member ' başlangıç etiketi ' Summary ' ile eşleşmiyor.**

Bu örnekteki sorun, \<Özet > bitiş etiketinin kötü biçimli ve derleyicinin \<Özet > bitiş etiketi olarak tanımadığı bir örnektir.  \<member > etiketi, her/doc derlemesinde derleyici tarafından. xdc dosyasına katıştırılır.  Bu nedenle buradaki sorun, \</member > bitiş etiketinin, derleyicinin işlediği önceki başlangıç etiketiyle (\<Özet >) eşleşmez.