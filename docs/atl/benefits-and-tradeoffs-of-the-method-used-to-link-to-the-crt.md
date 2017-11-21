---
title: "Avantajları ve bileşim CRT bağlamak için kullanılan yöntemin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: _ATL_MIN_CRT macro
ms.assetid: 49b485f7-9487-49e4-b12a-0f710b620e2b
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 13b4ef1599a5f59e1f01d551552cb03265e939ac
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt"></a>Avantajları ve bileşim CRT bağlamak için kullanılan yöntemi
Projenizi ile CRT dinamik veya statik olarak bağlayabilirsiniz. Aşağıdaki tabloda, avantajları ve hangi yöntemin kullanılacağını seçerken söz konusu bileşim özetlenmektedir.  
  
|Yöntem|Faydası|Kolaylığını|  
|------------|-------------|--------------|  
|Statik olarak CRT bağlama<br /><br /> (**Çalışma zamanı kitaplığı** kümesine **tek iş parçacıklı**)|CRT DLL görüntü çalıştırılacağı sistemde gerekli değildir.|Yaklaşık 25K başlangıç kodu yansımanıza, önemli ölçüde boyutunu artırarak eklenir.|  
|CRT dinamik olarak bağlama<br /><br /> (**Çalışma zamanı kitaplığı** kümesine **çok iş parçacıklı**)|Çok daha küçük olacak şekilde görüntünüzü CRT başlatma kodunu gerektirmez.|CRT DLL görüntüsünü çalıştıran sistemde olması gerekir.|  
  
 Konu [projenize ATL CRT bağlantılandırma](../atl/linking-to-the-crt-in-your-atl-project.md) CRT bağlamak bir şekilde seçmek nasıl ele alınmaktadır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL ve C çalışma zamanı koduyla programlama](../atl/programming-with-atl-and-c-run-time-code.md)   
 [DLL'ler ve Visual C++ çalışma zamanı kitaplığı davranışı](../build/run-time-library-behavior.md)   
 [CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md)

