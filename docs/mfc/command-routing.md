---
description: 'Daha fazla bilgi edinin: komut yönlendirme'
title: Komut Yönlendirme
ms.date: 09/06/2019
helpviewer_keywords:
- MFC, command routing
- command handling [MFC], routing commands
- handlers [MFC]
- handlers, command [MFC]
- command routing
ms.assetid: 9393a956-bdd4-47c5-9013-dbd680433f93
ms.openlocfilehash: 4004f74413f236599c5cdd14f6593bc5d2bd26b8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283452"
---
# <a name="command-routing"></a>Komut Yönlendirme

Komutlarla çalışma sorumluluğu,, [MFC sınıf Sihirbazı 'nı](reference/mfc-class-wizard.md)kullandığınız bir görev olan komutlar ve kendi işleyici işlevleri arasında ileti eşleme bağlantıları yapmaya sınırlandırılmıştır. Ayrıca komut işleyicileri için kod yazmanız gerekir.

Windows iletileri genellikle ana çerçeve penceresine gönderilir, ancak komut iletileri daha sonra diğer nesnelere yönlendirilir. Çerçeve komutları komut hedefi nesnelerinin standart dizisi aracılığıyla yönlendirir, bunlardan biri komut için bir işleyiciye sahip olması beklenir. Her komut hedefi nesnesi, gelen iletiyi işleyebileceğini görmek için ileti haritasını denetler.

Farklı komut hedefi sınıfları, kendi ileti haritalarını farklı zamanlarda denetler. Genellikle, bir sınıf komutu, komuta ilk şans vermek için belirli diğer nesnelere yönlendirir. Bu nesnelerden hiçbiri komutu işleiyorsa, özgün sınıf kendi ileti haritasını denetler. Ardından, işleyicinin kendisi sağlayamadıysa, komutu henüz daha fazla komut hedeflerine yönlendirebilir. Aşağıdaki tablo [standart komut yolu](#_core_standard_command_route) , sınıfların her birinin bu sırayı nasıl yapısını gösterir. Komut hedefinin bir komutun yönlendirme genel sırası:

1. Şu anda etkin olan alt komut, hedef nesne.

1. .

1. Diğer komut hedeflerine.

Bu yönlendirme mekanizması, işleyicinizin bir komuta yanıt olarak ne kadar pahalı olduğuna kıyasla, yönlendirmenin maliyeti düşüktür. Framework 'ün yalnızca Kullanıcı bir kullanıcı arabirimi nesnesiyle etkileşime geçtiğinde komutlar ürettiğini göz önünde bulundurun.

### <a name="standard-command-route"></a><a name="_core_standard_command_route"></a> Standart komut yolu

|Bu türden bir nesne bir komut aldığında. . .|Kendisine ve diğer komut hedefi nesnelerine bu sırada komutu işleme şansı verir:|
|----------------------------------------------------------|-----------------------------------------------------------------------------------------------------|
|MDI çerçevesi penceresi ( `CMDIFrameWnd` )|1. etkin `CMDIChildWnd`<br />2. bu çerçeve penceresi<br />3. uygulama ( `CWinApp` nesne)|
|Belge çerçevesi penceresi ( `CFrameWnd` , `CMDIChildWnd` )|1. etkin görünüm<br />2. bu çerçeve penceresi<br />3. uygulama ( `CWinApp` nesne)|
|Görüntüle|1. Bu görünüm<br />2. görünüme Ekli belge|
|Belge|1. Bu belge<br />2. belgeye ekli belge şablonu|
|İletişim kutusu|1. bu iletişim kutusu<br />2. iletişim kutusunun sahibi olan pencere<br />3. uygulama ( `CWinApp` nesne)|

Yukarıdaki tablonun ikinci sütununda numaralandırılmış girişlerin bir belge gibi diğer nesnelerden bahsetme yeri, ilk sütunda karşılık gelen öğeye bakın. Örneğin, görünümün bir komutu belgeye iletme ikinci sütununda okuduğunuzda, yönlendirmeyi daha fazla izlemek için ilk sütundaki "belge" girdisine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve bir Işleyiciyi nasıl çağırır](how-the-framework-calls-a-handler.md)
