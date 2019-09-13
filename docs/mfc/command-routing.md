---
title: Komut Yönlendirme
ms.date: 09/06/2019
helpviewer_keywords:
- MFC, command routing
- command handling [MFC], routing commands
- handlers [MFC]
- handlers, command [MFC]
- command routing
ms.assetid: 9393a956-bdd4-47c5-9013-dbd680433f93
ms.openlocfilehash: 8d1e1e59c56439c01655a1416df645ccc6922411
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907627"
---
# <a name="command-routing"></a>Komut Yönlendirme

Komutlarla çalışma sorumluluğu,, [MFC sınıf Sihirbazı 'nı](reference/mfc-class-wizard.md)kullandığınız bir görev olan komutlar ve kendi işleyici işlevleri arasında ileti eşleme bağlantıları yapmaya sınırlandırılmıştır. Ayrıca komut işleyicileri için kod yazmanız gerekir.

Windows iletileri genellikle ana çerçeve penceresine gönderilir, ancak komut iletileri daha sonra diğer nesnelere yönlendirilir. Çerçeve komutları komut hedefi nesnelerinin standart dizisi aracılığıyla yönlendirir, bunlardan biri komut için bir işleyiciye sahip olması beklenir. Her komut hedefi nesnesi, gelen iletiyi işleyebileceğini görmek için ileti haritasını denetler.

Farklı komut hedefi sınıfları, kendi ileti haritalarını farklı zamanlarda denetler. Genellikle, bir sınıf komutu, komuta ilk şans vermek için belirli diğer nesnelere yönlendirir. Bu nesnelerden hiçbiri komutu işleiyorsa, özgün sınıf kendi ileti haritasını denetler. Ardından, işleyicinin kendisi sağlayamadıysa, komutu henüz daha fazla komut hedeflerine yönlendirebilir. Aşağıdaki tablo [standart komut yolu](#_core_standard_command_route) , sınıfların her birinin bu sırayı nasıl yapısını gösterir. Komut hedefinin bir komutun yönlendirme genel sırası:

1. Şu anda etkin olan alt komut, hedef nesne.

1. .

1. Diğer komut hedeflerine.

Bu yönlendirme mekanizması, işleyicinizin bir komuta yanıt olarak ne kadar pahalı olduğuna kıyasla, yönlendirmenin maliyeti düşüktür. Framework 'ün yalnızca Kullanıcı bir kullanıcı arabirimi nesnesiyle etkileşime geçtiğinde komutlar ürettiğini göz önünde bulundurun.

### <a name="_core_standard_command_route"></a>Standart komut yolu

|Bu türden bir nesne bir komut aldığında. biçimindeki telefon numarasıdır. biçimindeki telefon numarasıdır.|Kendisine ve diğer komut hedefi nesnelerine bu sırada komutu işleme şansı verir:|
|----------------------------------------------------------|-----------------------------------------------------------------------------------------------------|
|MDI çerçevesi penceresi (`CMDIFrameWnd`)|1.  Bkz`CMDIChildWnd`<br />2.  Bu çerçeve penceresi<br />3.  Uygulama (`CWinApp` nesne)|
|Belge çerçevesi penceresi (`CFrameWnd`, `CMDIChildWnd`)|1.  Etkin görünüm<br />2.  Bu çerçeve penceresi<br />3.  Uygulama (`CWinApp` nesne)|
|Görüntüle|1.  Bu görünüm<br />2.  Görünüme eklenen belge|
|Belge|1.  Bu belge<br />2.  Belgeye iliştirilmiş belge şablonu|
|İletişim kutusu|1.  Bu iletişim kutusu<br />2.  İletişim kutusunun sahibi olan pencere<br />3.  Uygulama (`CWinApp` nesne)|

Yukarıdaki tablonun ikinci sütununda numaralandırılmış girişlerin bir belge gibi diğer nesnelerden bahsetme yeri, ilk sütunda karşılık gelen öğeye bakın. Örneğin, görünümün bir komutu belgeye iletme ikinci sütununda okuduğunuzda, yönlendirmeyi daha fazla izlemek için ilk sütundaki "belge" girdisine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Framework'ün İşleyici Çağırması](../mfc/how-the-framework-calls-a-handler.md)
