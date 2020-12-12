---
description: 'Hakkında daha fazla bilgi edinin: aylık takvim denetiminin gün durumunu ayarlama'
title: Aylık Takvim Denetiminin Gün Durumunu Ayarlama
ms.date: 11/04/2016
f1_keywords:
- MCN_GETDAYSTATE
helpviewer_keywords:
- CMonthCalCtrl class [MFC], setting day state info
- MCN_GETDAYSTATE notification [MFC]
- month calendar controls [MFC], day state info
ms.assetid: 435d1b11-ec0e-4121-9e25-aaa6af812a3c
ms.openlocfilehash: e7fc06516877c54aadaef715c33abd128bbd6994
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217217"
---
# <a name="setting-the-day-state-of-a-month-calendar-control"></a>Aylık Takvim Denetiminin Gün Durumunu Ayarlama

Aylık takvim denetiminin özniteliklerinden biri, ayın her günü için denetimin gün durumu olarak adlandırılan bilgileri depolayabilme yeteneğidir. Bu bilgiler, şu anda görüntülenen aya ait belirli tarihleri vurgulamak için kullanılır.

> [!NOTE]
> `CMonthCalCtrl`Nesnenin, gün durumu bilgilerini görüntülemesi için MCS_DAYSTATE stili olmalıdır.

Gün durumu bilgileri 32 bitlik bir veri türü, **monthdaystate** olarak ifade edilir. **Monthdaystate** bit alanındaki her bir bit (1 ila 31), bir günün durumunu bir ayda temsil eder. Bir bit açık ise, karşılık gelen gün kalın olarak görüntülenir; Aksi takdirde, vurgu olmadan görüntülenir.

Aylık takvim denetiminin gün durumunu ayarlamak için iki yöntem vardır: bir [CMonthCalCtrl:: SetDayState](../mfc/reference/cmonthcalctrl-class.md#setdaystate) çağrısıyla veya mcn_getdaystate bildirim iletisini işleyerek açık olarak.

## <a name="handling-the-mcn_getdaystate-notification-message"></a>MCN_GETDAYSTATE bildirim Iletisini işleme

MCN_GETDAYSTATE ileti, görünür ayların içindeki günlerin nasıl görüntüleneceğini belirlemede denetim tarafından gönderilir.

> [!NOTE]
> Denetim, görünür aya göre önceki ve sonraki ayları önbelleğe aldığından, her yeni ay seçildiğinde bu bildirimi alırsınız.

Bu iletiyi doğru bir şekilde işlemek için, kaç aylık gün bilgilerinin istenmekte olduğunu belirlemelisiniz, doğru değerlerle **monthdaystate** yapılarını içeren bir dizi başlatabilir ve ilgili yapı üyesini yeni bilgilerle başlatabilirsiniz. Aşağıdaki yordam, gerekli adımların ayrıntılandırdığı, `CMonthCalCtrl` *m_monthcal* adlı bir nesneniz ve bir **monthdaystate** nesneleri, *mdState* dizisi olduğunu varsayar.

#### <a name="to-handle-the-mcn_getdaystate-notification-message"></a>MCN_GETDAYSTATE bildirim iletisini işlemek için

1. [Sınıf sihirbazını](reference/mfc-class-wizard.md)kullanarak, mcn_getdaystate ileti için *m_monthcal* nesnesine bir bildirim işleyicisi ekleyin (bkz. [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md)).

1. İşleyicinin gövdesinde aşağıdaki kodu ekleyin:

   [!code-cpp[NVC_MFCControlLadenDialog#26](../mfc/codesnippet/cpp/setting-the-day-state-of-a-month-calendar-control_1.cpp)]

   Örnek, *pNMHDR* işaretçisini uygun türe dönüştürür, sonra kaç ay bilgi istenmekte olduğunu ( `pDayState->cDayState` ) belirler. Her ay için geçerli bit alanından ( `pDayState->prgDayState[i]` ) sıfırdan başlatılır ve gereken tarihler ayarlanır (Bu durumda, her ayın 15 ' i).

## <a name="see-also"></a>Ayrıca bkz.

[CMonthCalCtrl Kullanma](../mfc/using-cmonthcalctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
