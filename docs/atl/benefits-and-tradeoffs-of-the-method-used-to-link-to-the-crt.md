---
title: Avantajları ve bileşim CRT bağlamak için kullanılan yöntemin | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 49b485f7-9487-49e4-b12a-0f710b620e2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b2835e88da11b8d8332226080eb860afd41c0702
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32355393"
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

