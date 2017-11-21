---
title: "Internet uygulamalarını test etme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Web applications [MFC], testing
- debugging Web applications [MFC], testing applications
- testing [MFC], Internet applications
- debugging [MFC], Web applications
- Internet debugging and testing
ms.assetid: ac4c74e3-d4ad-4e19-8f6c-e270de067f01
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d246c6951b397e2eb888483f8afcdf2a822fd56d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="testing-internet-applications"></a>Internet Uygulamalarını Test Etme
Özellikle bir Web sunucusu üzerinde çalışan uygulamalar için Internet üzerindeki bazı benzersiz test zorluklar mevcuttur. İlk sınamanızı büyük olasılıkla yapılır test sunucusuna bağlanan bir tek kullanıcı istemci kullanma. Bu, kodda hata ayıklama için yararlı olacaktır.  
  
 Gerçek koşullar altında test etmek istiyor musunuz: düşük hızlı seri satırları yanı sıra yüksek hızlı bağlantıları bağlı birden çok istemcileriyle modem bağlantıları dahil olmak üzere. Gerçek koşullar benzetimini yapmak zor olabilir, ancak kesinlikle zaman tasarlama olası senaryolar harcama ve bunları yürütmesini değerindedir. Mümkünse, ayrıca kapasite ve stres testleri araçları kullanmak istersiniz. Zamanlama hataları gibi hataları belirli sınıfları, bulmak ve yeniden oluşturmak için zordur.  
  
 Internet programlama zorlukları görünürlüğü biridir. Sitenize birçok erişir, sunucuyu yavaşlatabilir. Sunucunuz düzgün bir şekilde düşürmesine izin istiyor. Uygulamanız (örneğin, kayıt defterine yazılırken veya istemcide tanımlama bilgilerini yazılırken Bozulması veri) başarısız olursa, bir kullanıcının bilgisayarına zararlı olabilecek herhangi bir şey önlemek isteyebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Internet programlama görevleri](../mfc/mfc-internet-programming-tasks.md)   
 [MFC Internet Programlama temelleri](../mfc/mfc-internet-programming-basics.md)

