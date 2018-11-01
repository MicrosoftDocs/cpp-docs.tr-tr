---
title: Komutlar ve Denetim Bildirimleri için İşleyiciler
ms.date: 11/04/2016
helpviewer_keywords:
- commands [MFC], handlers for
- functions [MFC], handler
- handlers [MFC]
- controls [MFC], notifications
- handlers [MFC], control notification [MFC]
- notifications [MFC], handlers for control
- handlers [MFC], command
ms.assetid: 20f57f4a-f577-4c09-80a2-43faf32a1c2e
ms.openlocfilehash: 28bed2937409cd1df5ee8d295e466609232e0e91
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622059"
---
# <a name="handlers-for-commands-and-control-notifications"></a>Komutlar ve Denetim Bildirimleri için İşleyiciler

Komutları veya denetim bildirimi iletileri için hiçbir varsayılan işleyicileri vardır. Bu nedenle, bu iletileri kategoriler için İşleyicileriniz adlandırma, yalnızca kural tarafından bağlıdır. Komut veya denetim bildirimi için bir işleyici eşlemesini özellikleri windows komut kimliği veya denetim bildirimi koduna göre adları önerir. Önerilen adını kabul edin veya değiştirin.

Her iki kategoriye işleyicileri için kullanıcı arabirimi nesnesi temsil ettikleri ad kuralı önerir. Bu nedenle Düzen menüsünde Cut komutu için bir işleyici adlandırılmış olabilir

[!code-cpp[NVC_MFCMessageHandling#4](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_1.h)]

Cut komutu uygulamalarında yaygın olarak bu nedenle uygulandığından framework kesme komutu için komut Kimliğini önceden belirler **ıd_edıt_cut**. Tüm önceden tanımlanmış komut kimlikleri listesi için ' % s'dosyasına AFXRES bakın. H Daha fazla bilgi için [standart komutlar](../mfc/standard-commands.md).

Ayrıca, kural için bir işleyici önerir **BN_CLICKED** "Düğmem" etiketli bir düğme bildirim iletisinden adlandırılmış

[!code-cpp[NVC_MFCMessageHandling#5](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_2.h)]

Bu komut kimliği atayabilirsiniz **IDC_MY_BUTTON** uygulamaya özel kullanıcı arabirimi nesneye eşdeğer olduğundan.

Her iki türdeki iletileri bağımsız değişken almaz ve herhangi bir değer döndürür.

## <a name="see-also"></a>Ayrıca Bkz.

[İleti İşleyici İşlevlerini Bildirme](../mfc/declaring-message-handler-functions.md)
