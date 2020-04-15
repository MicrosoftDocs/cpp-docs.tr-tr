---
title: Aylık Takvim Denetiminin Gün Durumunu Ayarlama
ms.date: 11/04/2016
f1_keywords:
- MCN_GETDAYSTATE
helpviewer_keywords:
- CMonthCalCtrl class [MFC], setting day state info
- MCN_GETDAYSTATE notification [MFC]
- month calendar controls [MFC], day state info
ms.assetid: 435d1b11-ec0e-4121-9e25-aaa6af812a3c
ms.openlocfilehash: 9892f2d853687787dd76428fc9bc95f3a4f74565
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365423"
---
# <a name="setting-the-day-state-of-a-month-calendar-control"></a>Aylık Takvim Denetiminin Gün Durumunu Ayarlama

Bir aylık takvim denetiminin özniteliklerinden biri, ayın her günü için denetimin gün durumu olarak adlandırılan bilgileri depolama yeteneğidir. Bu bilgiler, görüntülenen ayın belirli tarihlerini vurgulamak için kullanılır.

> [!NOTE]
> Nesne, `CMonthCalCtrl` gün durumu bilgilerini görüntülemek için MCS_DAYSTATE stiline sahip olmalıdır.

Gün durumu bilgileri 32 bit veri türü, **MONTHDAYSTATE**olarak ifade edilir. **MONTHDAYSTATE** bit alanındaki her bit (1 ile 31 arası) bir ay daki günün durumunu gösterir. Biraz acıklıysa, ilgili gün kalın olarak görüntülenir; aksi takdirde hiçbir vurgu ile görüntülenir.

Ay takvimi denetiminin gün durumunu ayarlamak için iki yöntem vardır: açıkça [CMonthCalCtrl::SetDayState'e](../mfc/reference/cmonthcalctrl-class.md#setdaystate) yapılan bir çağrıyla veya MCN_GETDAYSTATE bildirim iletisini işleyerek.

## <a name="handling-the-mcn_getdaystate-notification-message"></a>MCN_GETDAYSTATE Bildirim İletisini Işleme

MCN_GETDAYSTATE iletisi, görünür ay içindeki günlerin nasıl görüntüleneceğini belirlemek için denetim tarafından gönderilir.

> [!NOTE]
> Denetim, önceki ve sonraki aylarda önbelleğe aldığından, görünür aya göre, bu bildirimi her yeni ay seçildiğinde alırsınız.

Bu iletiyi düzgün işlemek için, kaç ay gün durum bilgisi istendiğini belirlemeniz, uygun değerlere sahip bir dizi **MONTHDAYSTATE** yapısını başlatmanız ve ilgili yapı üyesini yeni bilgilerle başlatmanız gerekir. Gerekli adımları ayrıntılı olarak açıklayan aşağıdaki yordam, `CMonthCalCtrl` *m_monthcal* adlı bir nesne ve **MONTHDAYSTATE** nesneleri, *mdState*bir dizi varsayıyor.

#### <a name="to-handle-the-mcn_getdaystate-notification-message"></a>MCN_GETDAYSTATE bildirim iletisini işlemek için

1. Sınıf [Sihirbazı'nı](reference/mfc-class-wizard.md)kullanarak, *m_monthcal* nesneye MCN_GETDAYSTATE ileti için bir bildirim işleyicisi ekleyin [(Bkz. İşlevlere İletileri Eşleme).](../mfc/reference/mapping-messages-to-functions.md)

1. İşleyicinin gövdesine aşağıdaki kodu ekleyin:

   [!code-cpp[NVC_MFCControlLadenDialog#26](../mfc/codesnippet/cpp/setting-the-day-state-of-a-month-calendar-control_1.cpp)]

   Örnek, *pNMHDR* işaretçisini uygun türe dönüştürür ve daha sonra kaç aylık`pDayState->cDayState`bilgi istendiğini belirler ( ). Her ay için, geçerli`pDayState->prgDayState[i]`bitfield ( ) sıfıra başlanır ve sonra gerekli tarihler ayarlanır (bu durumda, her ayın 15'i).

## <a name="see-also"></a>Ayrıca bkz.

[CMonthCalCtrl Kullanma](../mfc/using-cmonthcalctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
