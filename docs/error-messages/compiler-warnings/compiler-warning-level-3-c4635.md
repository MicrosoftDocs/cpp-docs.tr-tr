---
title: "Derleyici Uyarısı (Düzey 3) C4635 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4635
dev_langs: C++
helpviewer_keywords: C4635
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 00a831acaa172dfc24c4c39643b223ed6319a9e0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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