---
description: 'Hakkında daha fazla bilgi edinin: ekli aylık takvim denetimine erişme'
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
ms.openlocfilehash: 35c715cdd84bd7921883db530c8cf36e8e5cf07e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169456"
---
# <a name="accessing-the-embedded-month-calendar-control"></a>Katıştırılmış Aylık Takvim Denetimine Erişme

Gömülü ay Takvim denetim nesnesine `CDateTimeCtrl` [GetMonthCalCtrl](reference/cdatetimectrl-class.md#getmonthcalctrl) üye işlevine yapılan bir çağrı içeren nesneden erişilebilir.

> [!NOTE]
> Gömülü ay Takvim denetimi, yalnızca tarih ve saat seçici denetiminde **DTS_UPDOWN** stili ayarlı olmadığında kullanılır.

Bu, katıştırılmış denetim görüntülenmeden önce belirli öznitelikleri değiştirmek istiyorsanız kullanışlıdır. Bunu gerçekleştirmek için **dtn_dropdown** bildirimini işleyin, aylık Takvim denetimini alın ( [CDateTimeCtrl:: GetMonthCalCtrl](reference/cdatetimectrl-class.md#getmonthcalctrl)kullanarak) ve değişikliklerinizi yapın. Ne yazık ki aylık Takvim denetimi kalıcı değil.

Diğer bir deyişle, Kullanıcı aylık takvim denetiminin görüntülenmesini istediğinde, yeni bir aylık Takvim denetimi oluşturulur ( **dtn_dropdown** bildiriminden önce). Kullanıcı tarafından çıkarıldığında denetim yok edilir ( **dtn_closeup** bildiriminden sonra). Diğer bir deyişle, katıştırılmış denetim görüntülenmeden önce değiştirdiğiniz özniteliklerin, katıştırılmış denetim çıkarıldığında kaybedildiği anlamına gelir.

Aşağıdaki örnek, **dtn_dropdown** bildirimi için bir işleyici kullanarak bu yordamı gösterir. Kod, ay Takvim denetiminin arka plan rengini, [SetMonthCalColor](reference/cdatetimectrl-class.md#setmonthcalcolor)çağrısı ile gri olarak değiştirir. Kod şu şekildedir:

[!code-cpp[NVC_MFCControlLadenDialog#5](codesnippet/cpp/accessing-the-embedded-month-calendar-control_1.cpp)]

Daha önce belirtildiği gibi, aylık takvim denetiminin özelliklerindeki tüm değişiklikler, katıştırılmış denetim çıkarıldığında iki özel durum ile kaybedilir. Aylık takvim denetiminin renkleri ilk özel durum, zaten tartışılır. İkinci özel durum, aylık Takvim denetimi tarafından kullanılan yazı tipidir. [CDateTimeCtrl:: SetMonthCalFont](reference/cdatetimectrl-class.md#setmonthcalfont)çağrısı yaparak, var olan bir yazı tipinin tanıtıcısını geçirerek varsayılan yazı tipini değiştirebilirsiniz. Aşağıdaki örnek ( `m_dtPicker` Tarih ve saat denetim nesnesi) olası bir yöntemi gösterir:

[!code-cpp[NVC_MFCControlLadenDialog#6](codesnippet/cpp/accessing-the-embedded-month-calendar-control_2.cpp)]

Yazı tipi değiştirildikten sonra, bir ' a çağrı ile `CDateTimeCtrl::SetMonthCalFont` Yeni yazı tipi depolanır ve bir ay takvimi görüntülenecek bir sonraki sefer kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[CDateTimeCtrl Kullanma](using-cdatetimectrl.md)<br/>
[Denetimler](controls-mfc.md)
