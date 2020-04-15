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
ms.openlocfilehash: 686d5eef4aaa67785aa56133d820b637fbf4bb86
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364748"
---
# <a name="message-categories"></a>İleti Kategorileri

Üç ana kategori için ne tür iletiler yazarsınız:

1. Windows iletileri

   Bu, WM_COMMAND hariç, **öncelikle WM_** önekiyle başlayan iletileri içerir. Windows iletileri windows ve görünümler tarafından işlenir. Bu iletiler genellikle iletinin nasıl işleyeceğini belirlemede kullanılan parametrelere sahiptir.

1. Denetim bildirimleri

   Buna denetimlerden ve diğer alt pencerelerden üst pencerelerine WM_COMMAND bildirim iletileri dahildir. Örneğin, bir edit denetimi, kullanıcı denetim denetiminde metni değiştirmiş olabilecek bir eylemde bulunduğunda, ana EN_CHANGE denetim bildirim kodunu içeren bir WM_COMMAND iletisi gönderir. İleti için pencerenin işleyicisi, bildirim iletisine denetimdeki metni almak gibi uygun bir şekilde yanıt verir.

   Çerçeve, diğer **WM_** iletileri gibi denetim bildirim iletilerini yönlendirir. Ancak bunun bir istisnası, kullanıcı bunları tıklattığında düğmeler tarafından gönderilen BN_CLICKED denetim bildirim iletisidir. Bu ileti özel olarak bir komut iletisi olarak kabul edilir ve diğer komutlar gibi yönlendirilir.

1. Komut iletileri

   Bu, kullanıcı arabirimi nesnelerinden WM_COMMAND bildirim iletilerini içerir: menüler, araç çubuğu düğmeleri ve hızlandırıcı tuşları. Çerçeve süreçleri komutları diğer iletilerden farklı olarak işler ve [Komut Hedefleri'nde](../mfc/command-targets.md)açıklandığı gibi daha fazla nesne türü tarafından işlenebilir.

## <a name="windows-messages-and-control-notification-messages"></a><a name="_core_windows_messages_and_control.2d.notification_messages"></a>Windows İletileri ve Denetim-Bildirim İletileri

Kategori 1 ve 2 'deki iletiler — Windows iletileri ve denetim bildirimleri `CWnd`— windows tarafından işlenir: sınıftan türetilen sınıfların nesneleri. Bu, `CFrameWnd` `CMDIFrameWnd`, `CMDIChildWnd` `CView`, `CDialog`, , , ve bu temel sınıflardan türetilen kendi sınıflarınızı içerir. Bu tür nesneler, Windows `HWND`penceresine bir , tutamacı kapsüller.

## <a name="command-messages"></a><a name="_core_command_messages"></a>Komut Mesajları

Kategori 3'teki iletiler —komutlar- daha çeşitli nesneler tarafından işlenebilir: belgeler, belge şablonları ve windows ve görünümlere ek olarak uygulama nesnesinin kendisi. Bir komut belirli bir nesneyi doğrudan etkilediğinde, bu nesnenin komutu işlemesi mantıklıdır. Örneğin, Dosya menüsündeki Aç komutu mantıksal olarak uygulamayla ilişkilidir: uygulama komutu aldıktan sonra belirli bir belgeyi açar. Yani Açık komutunun işleyicisi uygulama sınıfının bir üye işlevidir. Komutlar ve nesnelere nasıl yönlendirildikleri hakkında daha fazla bilgi için, [Framework Calls a Handler'ı nasıl aradığını](../mfc/how-the-framework-calls-a-handler.md)görün.

## <a name="see-also"></a>Ayrıca bkz.

[Framework'teki İletiler ve Komutlar](../mfc/messages-and-commands-in-the-framework.md)
