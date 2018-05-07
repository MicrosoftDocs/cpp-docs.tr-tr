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
ms.openlocfilehash: 2dcc4b7466ed53a187b7f34ec45084a94adb59b4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4635"></a>Derleyici Uyarısı (Düzey 3) C4635
XML Belge açıklama hedef: hatalı biçimlendirilmiş XML: nedeni  
  
 Derleyici XML etiketleri ile ilgili bazı sorunlar bulundu.  Derleme ve sorunu düzeltin  
  
 Aşağıdaki örnek C4635 oluşturur:  
  
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
  
 Bitiş etiketi için olan bu örnek sorun \<Özet > düzgün biçimlendirildiğinden ve derleyici olarak tanımıyor \<Özet > bitiş etiketi.  \<Üye > etiketi gömülü .xdc dosyasında her/doc derlemede derleyici tarafından.  Bu nedenle, burada sorun bitiş etiketi \</member >, derleyici işlenen önceki başlangıç etiketiyle eşleşmiyor (\<Özet >.