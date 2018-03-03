---
title: "Bit kaydırma işleçleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], bitwise
- shift operators, bitwise
- bitwise-shift operators
- operators [C++], shift
ms.assetid: d0485785-5c72-47e1-a7c0-0adde03ade23
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e13e65e42febf2256e11bcb428e98805cdd6550f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="bitwise-shift-operators"></a>Bit Düzeyinde Kaydırma İşleçleri
İlk işlenen sola kaydırma işleçleri shift (`<<`) sağa (`>>`) ikinci işlenen konumlar numarasıyla belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
 *Shift ifade*:  
 *ADDITIVE ifade*  
  
 *Shift ifade*`<<`*ADDITIVE ifade shift-ifade*`>>`*ADDITIVE ifade*   
  
 Her iki işlenen tam sayı değerleri olmalıdır. Bu işleçlere olağan aritmetik dönüştürmeler; yine de gerçekleştir istiyor musunuz? Sonuç türü dönüştürmeden sonra sol işleneni türüdür.  
  
 Leftward kaydırmalar için vacated doğru bit 0 olarak ayarlanır. Rightward kaydırmalar için vacated sol BITS ilk işlenen türüne göre dönüştürmeden sonra doldurulur. Tür ise `unsigned`, 0 olarak ayarlayın. Aksi takdirde, bunlar oturum bit kopyalarını ile doldurulur. Taşma, deyim olmadan sola kaydırma işleçleri  
  
```  
expr1 << expr2   
```  
  
 çarpma 2 eşdeğerdir<sup>expr2</sup>. Sağa kaydırma işleçleri  
  
```  
expr1 >> expr2   
```  
  
 2 bölme eşdeğerdir<sup>expr2</sup> varsa `expr1` imzasız veya negatif olmayan bir değere sahip.  
  
 Bir kaydırma işleminin sonucu ikinci işlenen negatifse ya da sıfırdan büyük veya eşit genişliği yükseltilen sol işleneni bit sağ işleneni tanımlanmamıştır.  
  
 Dönüşümler gerçekleştirilen bu yana tarafından kaydırma işleçleri için taşma sağlamaz veya shift işleminin sonucu dönüştürmeden sonra ilk işlenen türünde gösterilemezse underflow koşullar, bilgiler kaybolmuş olabilir.  
  
```  
unsigned int x, y, z;  
  
x = 0x00AA;  
y = 0x5500;  
  
z = ( x << 8 ) + ( y >> 8 );  
```  
  
 Bu örnekte, `x` sekiz konumlar sol gölgeye ve `y` ötelenen sağ sekiz konumlar olduğu. 0xAA55 vermiş ve atanan ötelenen değerleri eklenir `z`.  
  
 Negatif bir değer sağa kaydırma yuvarlanan özgün yarım değeri verir. Örneğin,-253 (ikili 11111111 00000011) doğru bir bit üretir-127 (ikili 11111111 10000001) kaydırılır. Bir pozitif 253 kaydırmalar sağ +126 üretmek için.  
  
 Sağa kaydırmalar oturum bit korur. İmzalı bir tamsayı sağa kaydırır en önemli biti ayarlanmış olarak kalır. İşaretsiz tamsayıya sağ geçtiğinde en önemli bit işaretli değildir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sol Kaydırma ve Sağ Kaydırma İşleçleri (>> ve <<)](../cpp/left-shift-and-right-shift-operators-input-and-output.md)