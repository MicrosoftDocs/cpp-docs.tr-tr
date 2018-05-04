---
title: Sağ kaydırmalar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: c878e97d-ea3c-4c6b-90a8-b1b24b2d5b19
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c2eac057bbf8164915ff645cca098bbbf7c1995a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="right-shifts"></a>Sağa Kaydırmalar
Sağa kaydırma negatif değer sonucunu tam sayı türdür  
  
 Negatif bir değer sağa kaydırma yarım mutlak yuvarlanan değeri verir. Örneğin, imzalı `short` -253 (onaltılık 0xFF03, ikili 11111111 00000011) değerini gölgeye doğru bir bit üretir-127 (onaltılık 0xFF81, ikili 11111111 10000001). Pozitif 253 sağ üretir +126 kaydırılır.  
  
 Sağa kaydırmalar oturum bit imzalı tam sayı türleri korur. İmzalı bir tamsayı sağa kaydırır en önemli biti ayarlanmış olarak kalır. Örneğin, 0xF0000000 işaretli ise `int`, sağa kaydırma 0xF8000000 üretir. Negatif kaydırma `int` sağ 32 kez 0xFFFFFFFF üretir.  
  
 İşaretsiz tamsayıya sağ geçtiğinde en önemli bit işaretli değildir. Örneğin, 0xF000 imzasız ise sonucu 0x7800 olur. Kaydırma bir `unsigned` ya da pozitif `int` sağ 32 kez 0x00000000 üretir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tam Sayılar](../c-language/integers.md)