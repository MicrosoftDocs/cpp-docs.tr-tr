---
title: "Giriş akış Manipülatörleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- input streams, manipulators
- input stream objects
ms.assetid: 0addcacb-7b7b-4d70-9775-a59abc400fb3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ce3f1b99fe44d07a8793501c800f32077509ec0d
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="input-stream-manipulators"></a>Giriş Akış Manipülatörleri
Birçok manipülatörleri gibi [setprecision](../standard-library/iomanip-functions.md#setprecision), tanımlanmış `ios` sınıfı ve bu nedenle akışları giriş uygulanır. Birkaç manipülatörleri, ancak gerçekte Giriş akışı nesneleri etkiler. Sayı tabanını manipülatörleri içeriğiyle yapan, en önemli olan `dec`, `oct`, ve `hex`, giriş akışından numaralarıyla kullanılan dönüştürme temel belirleyin.  
  
 Ayıklama üzerinde `hex` manipulator çeşitli giriş biçimleri işlenmesini sağlar. Örneğin, c C 0xc, 0xC, 0Xc ve 0XC tüm yorumlanacağını ondalık tamsayı olarak 12. Herhangi bir karakter dışında 0-9, A-F, a ile f, x ve X sayısal dönüşüm sonlandırır. Bu nedenle dizisi `"124n5"` numarasıyla 124 dönüştürülür [basic_ios::fail](../standard-library/basic-ios-class.md#fail) biti ayarlanmamış.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Giriş Akışları](../standard-library/input-streams.md)

