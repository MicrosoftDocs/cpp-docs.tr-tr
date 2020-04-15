---
title: Katıştırılmış Aylık Takvim Denetimine Erişme
ms.date: 11/04/2016
helpviewer_keywords:
- DateTimePicker control [MFC], accessing month calendar
- CDateTimeCtrl class [MFC], accessing embedded control
- month calendar controls [MFC], embedded in date/time picker
- CMonthCalCtrl class [MFC], changing the font
- month calendar controls [MFC], changing the font
- DateTimePicker control [MFC]
ms.assetid: 355e97ed-cf81-4df3-a2f8-9ddbbde93227
ms.openlocfilehash: 69270cc5663406f2c5d38ffccdbd35f39298a3d5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354191"
---
# <a name="accessing-the-embedded-month-calendar-control"></a>Katıştırılmış Aylık Takvim Denetimine Erişme

Katıştılı ay takvim denetim nesnesine `CDateTimeCtrl` [GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl) üye işlevine çağrı ile nesneden erişilebilir.

> [!NOTE]
> Katıştırılmış ay takvim denetimi yalnızca tarih ve saat seçici denetimi **DTS_UPDOWN** stili kümesi yoksa kullanılır.

Katıştırılmış denetim görüntülenmeden önce belirli öznitelikleri değiştirmek istiyorsanız bu yararlıdır. Bunu gerçekleştirmek **için, DTN_DROPDOWN** bildirimini gerçekleştirin, ay takvimi denetimini alın [(CDateTimeCtrl::GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl)kullanarak) ve değişikliklerinizi yapın. Ne yazık ki, ay takvim denetimi kalıcı değildir.

Başka bir deyişle, kullanıcı ay takvim denetiminin görüntülenmesini istediğinde, yeni bir ay takvim denetimi oluşturulur **(DTN_DROPDOWN** bildiriminden önce). Denetim kullanıcı tarafından kapatıldığında **(DTN_CLOSEUP** bildiriminden sonra) yok edilir. Bu, katıştırılmış denetim görüntülenmeden önce değiştirdiğiniz özniteliklerin, katıştırılmış denetim kapatıldığında kaybolduğu anlamına gelir.

Aşağıdaki örnek, **DTN_DROPDOWN** bildirimi için bir işleyici kullanarak bu yordamı gösterir. Kod, [SetMonthCalColor'a](../mfc/reference/cdatetimectrl-class.md#setmonthcalcolor)yapılan bir çağrıyla ay takvimi denetiminin arka plan rengini griye değiştirir. Kod aşağıdaki gibidir:

[!code-cpp[NVC_MFCControlLadenDialog#5](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_1.cpp)]

Daha önce belirtildiği gibi, katıştırılmış denetim kapatıldığında, iki istisna dışında, ayın takvim denetimiözelliklerinde yapılan tüm değişiklikler kaybolur. İlk istisna, ayın takvim denetiminin renkleri zaten tartışıldı. İkinci özel durum, ay takvimi denetimi tarafından kullanılan yazı tipidir. [CDateTimeCtrl::SetMonthCalFont](../mfc/reference/cdatetimectrl-class.md#setmonthcalfont), varolan bir yazı tipinin tutamacını geçerek bir arama yaparak varsayılan yazı tipini değiştirebilirsiniz. Aşağıdaki örnek (tarih ve saat denetim nesnesi nerede) `m_dtPicker` olası bir yöntemi gösterir:

[!code-cpp[NVC_MFCControlLadenDialog#6](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_2.cpp)]

Yazı tipi değiştirildikten sonra, yeni `CDateTimeCtrl::SetMonthCalFont`yazı tipi bir sonraki kez bir ay takvimi görüntülenir saklanır ve kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[CDateTimeCtrl Kullanma](../mfc/using-cdatetimectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
