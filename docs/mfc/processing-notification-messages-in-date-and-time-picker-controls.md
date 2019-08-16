---
title: Tarih ve Saat Seçici Denetimlerinde Bildirim İletilerini İşleme
ms.date: 11/04/2016
f1_keywords:
- DTN_CLOSEUP
- DTN_DATETIMECHANGE
- DTN_DROPDOWN
helpviewer_keywords:
- DTN_DROPDOWN notification [MFC]
- DTN_DATETIMECHANGE notification [MFC]
- DTN_CLOSEUP notification [MFC]
- DateTimePicker control [MFC], handling notifications
- CDateTimeCtrl class [MFC], handling notifications
- DTN_FORMAT notification [MFC]
- DateTimePicker control [MFC]
ms.assetid: ffbe29ab-ff80-4609-89f7-260b404439c4
ms.openlocfilehash: fead5643299aee4beace55abde0b6a6c801a324f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507886"
---
# <a name="processing-notification-messages-in-date-and-time-picker-controls"></a>Tarih ve Saat Seçici Denetimlerinde Bildirim İletilerini İşleme

Kullanıcılar tarih ve saat seçici denetimiyle etkileşecek şekilde, denetim (),`CDateTimeCtrl`ana penceresine (genellikle bir görünüm veya iletişim nesnesi) bildirim iletileri gönderir. Yanıtta bir şey yapmak istiyorsanız bu iletileri işleyin. Örneğin, Kullanıcı katıştırılmış ay Takvim denetimini göstermek için tarih ve saat seçicisini açtığında, DTN_DROPDOWN bildirimi gönderilir.

Uygulamak istediğiniz iletilerin üst sınıfına bildirim işleyicileri eklemek için Özellikler penceresi kullanın.

Aşağıdaki listede tarih ve saat seçici denetimi tarafından gönderilen çeşitli bildirimler açıklanmaktadır.

- DTN_DROPDOWN, gömülü ay Takvim denetiminin görüntülenmek üzere olduğunu üst öğeye bildirir. Bu bildirim yalnızca DTS_UPDOWN stili ayarlanmamışsa gönderilir. Bu bildirim hakkında daha fazla bilgi için bkz. [katıştırılmış ay Takvim denetimine erişme](../mfc/accessing-the-embedded-month-calendar-control.md).

- DTN_CLOSEUP, gömülü ay Takvim denetiminin kapatılmak üzere olduğunu üst öğeye bildirir. Bu bildirim yalnızca DTS_UPDOWN stili ayarlanmamışsa gönderilir.

- DTN_DATETIMECHANGE, üst öğeye denetimde bir değişikliğin oluştuğunu bildirir.

- DTN_FORMAT, metnin bir geri çağırma alanında görüntülenmesi için gerekli olduğunu bildirir. Bu bildirim ve geri çağırma alanları hakkında daha fazla bilgi için bkz. [bir tarih ve saat seçici denetiminde geri çağırma alanları kullanma](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).

- DTN_FORMATQUERY, bir geri çağırma alanında görüntülenecek olan dizenin izin verilen en büyük boyutunu sağlamak için üst öğeyi Ister. Bu bildirimin işlenmesi, denetimin ekran içindeki titreşimi azaltmak için her zaman çıktıyı düzgün şekilde görüntülemesine olanak tanır. Bu bildirim hakkında daha fazla bilgi için bkz. [Tarih ve saat seçici denetiminde geri çağırma alanları kullanma](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).

- DTN_USERSTRING, üst öğeye kullanıcının tarih ve saat seçici denetiminin içeriğini düzenlemesini tamamladığını bildirir. Bu bildirim yalnızca DTS_APPCANPARSE stili ayarlandığında gönderilir.

- DTN_WMKEYDOWN, Kullanıcı bir geri çağırma alanına yazdığında üst öğeye bildirir. Tarih ve saat seçici denetiminde geri çağırma olmayan alanlar için desteklenen klavye yanıtını öykünmek için bu bildirimi işleyin. Bu bildirim hakkında daha fazla bilgi için bkz. Windows SDK [BIR DTP denetimindeki geri çağırma alanlarını destekleme](/windows/win32/Controls/date-and-time-picker-controls) .

## <a name="see-also"></a>Ayrıca bkz.

[CDateTimeCtrl Kullanma](../mfc/using-cdatetimectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
