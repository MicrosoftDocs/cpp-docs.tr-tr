---
title: "DCOM geçmişi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Remote Automation, DCOM
- DCOM, about DCOM
- DCOM
ms.assetid: c21aa0ea-1396-4b52-b77f-88fb0fdd2a5c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9e5607fd240c7a97691189b8a3afa5e7c0171e26
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="history-of-dcom"></a>DCOM Geçmişi
Otomasyon, ilk olarak erken 1993 sunulmuştur, yalnızca aynı makinede çalışan uygulamalar arasında kullanılabilir. Rest olan OLE, COM (veya Bileşen Nesne modeli) olarak aynı bağlamasından paylaşılan olduğundan, ancak bu her zaman COM kendisini remoting özellikleri içerecek şekilde güncelleştirildiğinde, "Uzaktan erişilebilir" olacak üzere tasarlanmıştır. Dağıtılmış işlemi tamamen yerel işlemi geçiş var olan kodu çok az kayıpla veya hiç değişiklik gerekir, ayrıca planlandığı.  
  
 Yerel COM "Uzaktan" ne anlama geliyor bir arabirim tüketici bulunmasını dikte şekilde ve bu arabirimi sağlayıcısı ile aynı makinede çalıştırın. Örneğin, Microsoft Visual Basic Microsoft Excel bir kopyasını Masaüstü makinenizde denetleyebilir, ancak Excel yürütme başka bir makinede yönlendirerek yeteneğine sahip değil. Dağıtılmış COM geliştirme ile bir arabirim tüketici artık aynı makinede üzerinde arabirimi sağlayıcısı yürüten bulunması gerekir.  
  
 COM bir ağ üzerinden çalışmak için uyarlanmış sonra sonra herhangi bir yerel yürütme modeline bağlı olmayan arabirim (yerel makine tesis devralınan bağımlılık bazı arabirimine sahip, çizim, bu gibi arabirimleri yöntemlerine sahip cihaz bağlamları tanıtıcıları Parametreler) dağıtılmakta özelliği gerekir. Bir arabirim tüketici belirli bir arabirim için bir istek yapacağı; Bu arabirim bir örneği çalıştıran bir nesnenin (veya çalıştırılmak üzere) tarafından farklı bir makineye sağlanabilir. COM içinde dağıtım mekanizması şekilde sağlayıcısında tüketici bağlanacağı tüketici tarafından oluşturulan yöntemi çağrıları sağlayıcısı sonunda bunlar yürütüldüğü görünür. Tüm değerleri sonra tüketiciye geri gönderilecek döndür. İçin tüm intents ve purposes, dağıtım act tüketici ve sağlayıcı için saydamdır.  
  
 Bu tür, çeşitli COM artık yok. DCOM ("Dağıtılmış COM" için) Windows NT sürüm 4.0 başlayarak ve dahil olmak üzere Windows 2000 sürümü ile sevk edilmiş. Geç 1996 itibaren bu da Windows 9 var olan x. Her iki durumda da, hem yerel hem de uzak COM yetenekleri sağlayan bazı yardımcı programlar, bir dizi değiştirme ve ek DLL'leri DCOM oluşur. Bu nedenle artık bir devralınmış Win32 tabanlı platformlara parçasıdır ve diğer platformlarda diğer kuruluşlar tarafından zaman içinde kullanıma sunulacaktır.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Uzaktan Otomasyon nerelerde uygundur](where-does-remote-automation-fit-in-q.md)  
  
 [Uzaktan Otomasyon neler sağlar](what-does-remote-automation-provide-q.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzak Otomasyon](../mfc/remote-automation.md)
