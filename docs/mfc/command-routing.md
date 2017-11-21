---
title: "Komut yönlendirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC, command routing
- command handling [MFC], routing commands
- handlers [MFC]
- handlers, command [MFC]
- command routing
ms.assetid: 9393a956-bdd4-47c5-9013-dbd680433f93
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 622853951c9119bb2a32e9e624966bf77579b557
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="command-routing"></a>Komut Yönlendirme
İleti eşleme bağlantıları işleyici işlevlerini Özellikler penceresini kullanın görev ve komutları arasında yapmaya komutları ile çalışırken sizin sorumluluğunuzdadır sınırlıdır. Ayrıca, çoğu komut işleyicileri yazmanız gerekir.  
  
 Windows iletileri genellikle ana çerçeve penceresi gönderilir ancak komut iletileri sonra diğer nesnelere yönlendirilir. Framework biri komutu için bir işleyici sahip olması beklenir standart bir dizi komut hedefi nesnelerin komutları yönlendirir. Her komut hedefi nesnesi gelen ileti işleme olmadığını görmek için kendi ileti eşlemesi denetler.  
  
 Farklı komut hedefi sınıfları farklı zamanlarda kendi ileti eşlemeleri denetleyin. Genellikle, bir sınıfı diğer belirli nesnelere bunları ilk komut şansı komutu yönlendirir. Bu nesnelerden hiçbirinin komutu işliyorsa, özgün sınıf kendi ileti eşlemesi denetler. Bir işleyici bilmiyorsanız, daha sonra bu komut için henüz daha fazla komut hedefleri yol. Tablo [standart komut rota](#_core_standard_command_route) aşağıda gösterilmektedir nasıl sınıfların her biri bu sırası yapıları. Komut hedefi bir komut yönlendirir genel sırası şöyledir:  
  
1.  Şu anda etkin alt komutu hedef nesnesi için.  
  
2.  Kendisi için.  
  
3.  Diğer komut hedefleri için.  
  
 Yönlendirme maliyeti, pahalı bir komutuna yanıt olarak işleyicinizi ne için bu yönlendirme ile karşılaştırıldığında mekanizmasıdır nasıl düşüktür. Yalnızca kullanıcı bir kullanıcı arabirimi nesnesi ile etkileşim olduğunda framework komutları oluşturur aklınızda size aittir.  
  
### <a name="_core_standard_command_route"></a>Standart komut yönlendirme  
  
|Ne zaman bir komutu bu tür bir nesne alır. biçimindeki telefon numarasıdır. biçimindeki telefon numarasıdır.|Kendisi ve diğer komut hedefi nesneleri bu sırada komutu işlemek için bir fırsat sunar:|  
|----------------------------------------------------------|-----------------------------------------------------------------------------------------------------|  
|MDI çerçeve penceresi (`CMDIFrameWnd`)|1.  Etkin`CMDIChildWnd`<br />2.  Bu çerçeve penceresi<br />3.  Uygulama (`CWinApp` nesne)|  
|Belge çerçeve penceresi (`CFrameWnd`, `CMDIChildWnd`)|1.  Etkin görünümü<br />2.  Bu çerçeve penceresi<br />3.  Uygulama (`CWinApp` nesne)|  
|Görüntüle|1.  Bu görünüm<br />2.  Görünüme bağlı belge|  
|Belge|1.  Bu belgede<br />2.  Belgeye ekli belge şablonu|  
|İletişim kutusu|1.  Bu iletişim kutusu<br />2.  İletişim kutusu sahibi penceresi<br />3.  Uygulama (`CWinApp` nesne)|  
  
 Önceki tabloda ikinci sütundaki numaralı girişleri Bahsediyor burada bir belge gibi diğer nesneler ilk sütununda karşılık gelen öğe bakın. Görünümü, belge için bir komut iletir ikinci sütunda okurken örneği için daha fazla yönlendirme izlemek için ilk sütunda "Belge" girişine bakın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Framework bir işleyici çağırması](../mfc/how-the-framework-calls-a-handler.md)

