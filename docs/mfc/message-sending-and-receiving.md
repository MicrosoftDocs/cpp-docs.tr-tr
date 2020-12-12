---
description: 'Hakkında daha fazla bilgi edinin: Ileti gönderme ve alma'
title: İleti Gönderme ve Alma
ms.date: 11/04/2016
helpviewer_keywords:
- Windows messages [MFC], handling in MFC
- control-notification messages [MFC]
- messages [MFC], receiving
- messages [MFC], MFC
- MFC, messages
- messages [MFC], sending
ms.assetid: 9ce189cb-b259-4c3b-b6f2-9cfbed18b98b
ms.openlocfilehash: 3a61346c51ce035f6fd5a53b8c329ef81154b089
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203217"
---
# <a name="message-sending-and-receiving"></a>İleti Gönderme ve Alma

İşlemin gönderme bölümünü ve Framework 'ün nasıl yanıt verdiğini göz önünde bulundurun.

Çoğu ileti, program ile Kullanıcı etkileşiminden kaynaklanır. Komutlar, fare tıklamaları menü öğeleri veya araç çubuğu düğmeleri veya Hızlandırıcı tuş vuruşları tarafından oluşturulur. Kullanıcı, örneğin, bir pencereyi taşıyarak veya yeniden boyutlandırarak Windows iletileri de oluşturur. Windows iletileri, program başlatma veya sonlandırma gibi olaylar gerçekleştiğinde, Windows odak alır veya kaybeder gibi diğer Windows iletileri gönderilir. Denetim-bildirim iletileri, fare tıklamaları veya bir iletişim kutusunda düğme ya da liste kutusu denetimi gibi bir denetimle ilgili diğer kullanıcı etkileşimleri tarafından oluşturulur.

`Run`Sınıfının üye işlevi `CWinApp` iletileri alır ve uygun pencereye gönderir. Çoğu komut iletisi, uygulamanın ana çerçeve penceresine gönderilir. `WindowProc`Sınıf kitaplığı tarafından önceden tanımlanmış, alınan ileti kategorisine bağlı olarak iletileri alır ve farklı şekilde yönlendirir.

Şimdi işlemin alma bölümünü göz önünde bulundurun.

Bir iletinin ilk alıcısı bir pencere nesnesi olmalıdır. Windows iletileri genellikle bu pencere nesnesi tarafından doğrudan işlenir. Genellikle uygulamanın ana çerçeve penceresinde bulunan komut iletileri, [komut yönlendirme](command-routing.md)bölümünde açıklanan komut hedefi zincirine yönlendirilir.

İletileri veya komutları alan her bir nesne, işleyicisi adı ile bir ileti veya komutu çift eden kendi ileti eşlemesine sahiptir.

Bir komut hedefi nesnesi bir ileti veya komut aldığında, ileti eşlemesinde bir eşleşme arar. İleti için bir işleyici bulursa işleyiciyi çağırır. İleti eşlemelerinin nasıl arandığı hakkında daha fazla bilgi için bkz. [Framework 'Ün Ileti eşlemelerini arama şekli](how-the-framework-searches-message-maps.md). [Çerçevede şekil komutlarına](user-interface-objects-and-command-ids.md)tekrar başvurun.

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve bir Işleyiciyi nasıl çağırır](how-the-framework-calls-a-handler.md)
