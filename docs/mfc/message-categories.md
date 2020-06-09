---
title: İleti Kategorileri
ms.date: 11/04/2016
helpviewer_keywords:
- messages [MFC], categories
- control-notification messages [MFC]
- Windows messages [MFC], categories
- controls [MFC], notifications
- command messages [MFC]
- messages [MFC], Windows
- message handling [MFC], message types
ms.assetid: 68e1db75-9da6-4a4d-b2c2-dc4d59f8d87b
ms.openlocfilehash: 3875a6931b4380f0531e4c1786de6dddfccb76ca
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625464"
---
# <a name="message-categories"></a>İleti Kategorileri

İşleyiciler için ne tür iletiler yazarsanız, üç ana kategori vardır:

1. Windows iletileri

   Bu, öncelikle WM_COMMAND hariç **WM_** önekiyle başlayan iletileri içerir. Windows iletileri Windows ve görünümler tarafından işlenir. Bu iletilerde genellikle iletinin nasıl işleneceğini belirlemede kullanılan parametreler bulunur.

1. Denetim bildirimleri

   Bu, denetimlerden ve diğer alt pencerelerin üst pencereleri arasında WM_COMMAND bildirim iletileri içerir. Örneğin, bir düzenleme denetimi, Kullanıcı düzenleme denetiminde metin değiştirmiş olabilecek bir eylem gerçekleştirmediğinde, EN_CHANGE denetim-bildirim kodu içeren üst öğe WM_COMMAND iletisini gönderir. Pencerenin ileti işleyicisi, bildirim iletisine, denetimdeki metni alma gibi bazı uygun bir şekilde yanıt verir.

   Framework, denetim bildirimi iletilerini diğer **WM_** iletileri gibi yönlendirir. Ancak tek bir özel durum, Kullanıcı onlara tıkladığında düğme tarafından gönderilen BN_CLICKED denetim-bildirim iletisidir. Bu ileti, özel olarak komut iletisi olarak değerlendirilir ve diğer komutlar gibi yönlendirilir.

1. Komut iletileri

   Bu, Kullanıcı arabirimi nesnelerinden WM_COMMAND bildirim iletileri içerir: menüler, araç çubuğu düğmeleri ve hızlandırıcı tuşları. Çerçeve komutları diğer iletilerden farklı işler ve [komut hedefleri](command-targets.md)bölümünde açıklandığı gibi daha fazla nesne türü tarafından işlenebilirler.

## <a name="windows-messages-and-control-notification-messages"></a><a name="_core_windows_messages_and_control.2d.notification_messages"></a>Windows Iletileri ve denetim bildirimi Iletileri

Kategoriler 1 ve 2 ' deki iletiler; Windows iletileri ve denetim bildirimleri — Windows tarafından işlenir: sınıfından türetilmiş sınıfların nesneleri `CWnd` . Bu `CFrameWnd` temel sınıflardan türetilmiş,,,, `CMDIFrameWnd` `CMDIChildWnd` `CView` `CDialog` ve kendi sınıflarınızı içerir. Bu tür nesneler `HWND` , bir Windows penceresine yönelik bir tutamacı kapsülleyin.

## <a name="command-messages"></a><a name="_core_command_messages"></a>Komut Iletileri

Kategori 3 (komutları) içindeki iletiler, Windows ve görünümlere ek olarak, birçok farklı nesne tarafından işlenebilir: belgeler, belge şablonları ve uygulama nesnesi. Bir komut belirli bir nesneyi doğrudan etkiliyorsa, bu nesnenin komutu işlemesi mantıklı olur. Örneğin, Dosya menüsündeki Aç komutu, uygulamayla mantıksal olarak ilişkilendirilir: uygulama, komutu aldıktan sonra belirtilen bir belgeyi açar. Bu nedenle, Open komutuna yönelik işleyici, uygulama sınıfının bir üye işlevidir. Komutlar ve nesnelere nasıl yönlendirildiği hakkında daha fazla bilgi için, bkz. [Framework nasıl bir Işleyiciyi çağırır](how-the-framework-calls-a-handler.md).

## <a name="see-also"></a>Ayrıca bkz.

[Framework'teki İletiler ve Komutlar](messages-and-commands-in-the-framework.md)
