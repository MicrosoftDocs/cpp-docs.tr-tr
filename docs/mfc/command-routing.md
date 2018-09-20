---
title: Komut yönlendirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, command routing
- command handling [MFC], routing commands
- handlers [MFC]
- handlers, command [MFC]
- command routing
ms.assetid: 9393a956-bdd4-47c5-9013-dbd680433f93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 543b9e34c881285c295fb7ab7ee2107e36c99a9c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418326"
---
# <a name="command-routing"></a>Komut Yönlendirme

İleti eşleme bağlantıları komutları ve Özellikler penceresini kullanın görev bunların işleyici işlevlerine arasında yapmaya komutları ile çalışırken sizin sorumluluğunuzdadır sınırlıdır. Ayrıca, çoğu komut işleyicisi yazmanız gerekir.

Windows iletileri, genellikle ana çerçeve penceresine gönderilir, ancak komut iletilerini sonra diğer nesnelere yönlendirilir. Framework biri de komut için bir işleyici sahip olması bekleniyor standart bir dizi komut hedefi nesnelerin komutları yönlendirir. Her komut hedefi nesnesi gelen ileti başa durumunda görmek için ileti eşlemesi denetler.

Farklı komut hedefi sınıfları, farklı zamanlarda, kendi ileti eşlemeleri denetleyin. Genellikle, bir sınıf, diğer bazı nesnelere bunları komutunun ilk şans verin komutu yönlendirir. Bu nesneler hiçbiri komutu işliyorsa, özgün sınıf kendi ileti eşlemesi denetler. Bir işleyici bilmiyorsanız, ardından, bu komut için henüz daha fazla komut hedefleri yol. Tablo [standart komut yönlendirme](#_core_standard_command_route) aşağıda sınıfların her birini nasıl bu dizisi yapıları gösterir. İçinde komut hedefi bir komut yolları genel sırası şöyledir:

1. Şu anda etkin alt komut hedef nesnesi için.

1. Kendisi için.

1. Diğer komut hedefleri için.

Yönlendirme maliyeti, pahalı bir komutuna yanıt olarak işleyicinizi yaptığı için yönlendirme Bu mekanizma ile karşılaştırıldığında ne düşüktür. Aklınızda yalnızca kullanıcı bir kullanıcı arabirimi nesnesi ile etkileşim kurduğunda framework komutları oluşturur size aittir.

### <a name="_core_standard_command_route"></a> Standart komut yönlendirme

|Bu türde bir nesne bir komutunu aldığında. biçimindeki telefon numarasıdır. biçimindeki telefon numarasıdır.|Kendisi ve diğer komut hedef nesnesi bu sırayla komutunu işlemek için bir fırsat sunar:|
|----------------------------------------------------------|-----------------------------------------------------------------------------------------------------|
|MDI çerçeve penceresinin (`CMDIFrameWnd`)|1.  Etkin `CMDIChildWnd`<br />2.  Bu çerçeve penceresi<br />3.  Uygulama (`CWinApp` nesne)|
|Belge çerçeve penceresi (`CFrameWnd`, `CMDIChildWnd`)|1.  Etkin görünüm<br />2.  Bu çerçeve penceresi<br />3.  Uygulama (`CWinApp` nesne)|
|Görüntüle|1.  Bu görünüm<br />2.  Görünüme iliştirilmiş belgeye|
|Belge|1.  Bu belge<br />2.  Belgeye ekli belge şablonu|
|İletişim kutusu|1.  Bu iletişim kutusu<br />2.  İletişim kutusuna sahip penceresi<br />3.  Uygulama (`CWinApp` nesne)|

Önceki tablonun ikinci sütunda numaralı girişleri bahsetmek burada ilk sütununda karşılık gelen öğe bir belge gibi diğer nesneler bakın. Örneğin, ikinci sütun, görünüm, belge için bir komut iletir okurken, daha fazla yönlendirme izlemek için ilk sütunda "Belge" girdisine bakın.

## <a name="see-also"></a>Ayrıca Bkz.

[Framework'ün İşleyici Çağırması](../mfc/how-the-framework-calls-a-handler.md)

