---
title: Derleyici Uyarısı (Düzey 3) C4635 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4635
dev_langs:
- C++
helpviewer_keywords:
- C4635
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7651012d4c48d420734a9c6ec2ff051718f82007
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038119"
---
# <a name="compiler-warning-level-3-c4635"></a>Derleyici Uyarısı (Düzey 3) C4635

XML belgesi yorum hedef: hatalı oluşturulmuş XML: nedeni

Derleyicinin, XML etiketleri ile ilgili bazı sorunlar bulundu.  Yeniden derleyin ve sorunu düzeltin

Aşağıdaki örnek, C4635 oluşturur:

```
// C4635.cpp
// compile with: /doc /clr /W3 /c
/// <summary>
/// The contents of the folder have changed.
/// <summary/>   // C4635

// try the following line instead
// /// </summary>
public ref class Test {};
```

Bu örnek için çıktıyı diyor dikkat edin: **'member' bitiş etiketi 'Özet' başlangıç etiketiyle eşleşmiyor.**

Bu örnekte sorun için bitiş etiketi olan \<Özet > kötü biçimlendirilmiş ve derleyici olarak algılamaz \<Özet > bitiş etiketi.  \<Member > etiketi, her/doc derlemede derleyici tarafından .xdc dosyasında gömülüdür.  Bu nedenle, burada sorun bitiş etiketi \</member >, derleyicinin işlenen önceki başlangıç etiketiyle eşleşmiyor (\<Özet >.