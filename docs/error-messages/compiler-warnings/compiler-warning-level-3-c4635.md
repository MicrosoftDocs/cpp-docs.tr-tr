---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4635'
title: Derleyici Uyarısı (düzey 3) C4635
ms.date: 11/04/2016
f1_keywords:
- C4635
helpviewer_keywords:
- C4635
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
ms.openlocfilehash: e885c501e4f10719618bb552c153dc13a481332d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168338"
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

Bu örnekteki sorun, için bitiş etiketinin \<summary> Hatalı biçimlendirilmiş olması ve derleyicinin onu bitiş etiketi olarak tanımadığı bir örnektir \<summary> .  \<member>Etiketi, her/doc derlemesinde derleyici tarafından. xdc dosyasına katıştırılır.  Bu nedenle, buradaki sorun bitiş etiketinin \</member> derleyicinin işlediği önceki başlangıç etiketiyle eşleşmemesi ( \<summary> .
