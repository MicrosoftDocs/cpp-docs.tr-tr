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
ms.openlocfilehash: 6c92660c67fa91c27bb094111cebfef57904cdc7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62359000"
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

## <a name="see-also"></a>Ayrıca bkz.

[İleti İşleyici İşlevlerini Bildirme](../mfc/declaring-message-handler-functions.md)
