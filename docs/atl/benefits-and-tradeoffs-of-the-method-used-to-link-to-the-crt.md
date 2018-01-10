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
ms.workload: cplusplus
ms.openlocfilehash: 244415a947918a836e8c4c67dbd18758ec40393c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)

