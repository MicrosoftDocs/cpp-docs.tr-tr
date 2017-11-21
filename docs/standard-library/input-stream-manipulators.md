---
title: "Giriş akış Manipülatörleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- input streams, manipulators
- input stream objects
ms.assetid: 0addcacb-7b7b-4d70-9775-a59abc400fb3
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4aaea7ac729eeb34c224e55883fe4397b97d3e62
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="input-stream-manipulators"></a>Giriş Akış Manipülatörleri
[Setprecision]--brokenlink--gibi birçok manipülatörleri (.. / Topic/not%20found:3ddde610-70cc-4cfa-8a89-3e83d1d356a8.md#setprecision), tanımlanan `ios` sınıfı ve bu nedenle akışları giriş uygulanır. Birkaç manipülatörleri, ancak gerçekte Giriş akışı nesneleri etkiler. Sayı tabanını manipülatörleri içeriğiyle yapan, en önemli olan `dec`, `oct`, ve `hex`, giriş akışından numaralarıyla kullanılan dönüştürme temel belirleyin.  
  
 Ayıklama üzerinde `hex` manipulator çeşitli giriş biçimleri işlenmesini sağlar. Örneğin, c C 0xc, 0xC, 0Xc ve 0XC tüm yorumlanacağını ondalık tamsayı olarak 12. Herhangi bir karakter dışında 0-9, A-F, a ile f, x ve X sayısal dönüşüm sonlandırır. Bu nedenle dizisi `"124n5"` numarasıyla 124 dönüştürülür [basic_ios::fail](../standard-library/basic-ios-class.md#fail) biti ayarlanmamış.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Giriş akışları](../standard-library/input-streams.md)

