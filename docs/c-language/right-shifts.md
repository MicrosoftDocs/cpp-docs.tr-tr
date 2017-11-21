---
title: "Sağ kaydırmalar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c878e97d-ea3c-4c6b-90a8-b1b24b2d5b19
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cee551dfd0dbac11110a945edee21af6636138bc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="right-shifts"></a>Sağa Kaydırmalar
Sağa kaydırma negatif değer sonucunu tam sayı türdür  
  
 Negatif bir değer sağa kaydırma yarım mutlak yuvarlanan değeri verir. Örneğin, imzalı `short` -253 (onaltılık 0xFF03, ikili 11111111 00000011) değerini gölgeye doğru bir bit üretir-127 (onaltılık 0xFF81, ikili 11111111 10000001). Pozitif 253 sağ üretir +126 kaydırılır.  
  
 Sağa kaydırmalar oturum bit imzalı tam sayı türleri korur. İmzalı bir tamsayı sağa kaydırır en önemli biti ayarlanmış olarak kalır. Örneğin, 0xF0000000 işaretli ise `int`, sağa kaydırma 0xF8000000 üretir. Negatif kaydırma `int` sağ 32 kez 0xFFFFFFFF üretir.  
  
 İşaretsiz tamsayıya sağ geçtiğinde en önemli bit işaretli değildir. Örneğin, 0xF000 imzasız ise sonucu 0x7800 olur. Kaydırma bir `unsigned` ya da pozitif `int` sağ 32 kez 0x00000000 üretir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tamsayılara](../c-language/integers.md)