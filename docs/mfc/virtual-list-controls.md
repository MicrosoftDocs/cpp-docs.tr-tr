---
title: Sanal Liste Denetimleri
ms.date: 11/04/2016
helpviewer_keywords:
- cache, virtual list control item data
- list controls [MFC], virtual
- list controls [MFC], List view
- virtual list controls
ms.assetid: 319f841f-e426-423a-8276-d93f965b0b45
ms.openlocfilehash: 1ade5f404e134cf6de20756dcc5af169fefdec76
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375503"
---
# <a name="virtual-list-controls"></a>Sanal Liste Denetimleri

Sanal liste denetimi, LVS_OWNERDATA stiline sahip bir liste görünümü denetimidir. Bu stil, denetimin bir öğe sayısını **DWORD'e** kadar desteklemesini sağlar (varsayılan madde sayısı yalnızca **bir int'e**kadar uzanır). Ancak, bu stil tarafından sağlanan en büyük avantajı, yalnızca herhangi bir anda bellekte veri öğeleri nin bir alt kümesine sahip olmaktır. Bu, sanal liste görünümü denetiminin, verilere erişmek için belirli yöntemlerin zaten yürürlükte olduğu büyük bilgi veritabanlarıyla kullanılmak üzere kendini ödünç almasına olanak tanır.

> [!NOTE]
> Sanal liste işlevselliği sağlamanın `CListCtrl`yanı sıra, MFC de [CListView](../mfc/reference/clistview-class.md) sınıfında aynı işlevselliği sağlar.

Sanal liste denetimleri geliştirirken dikkat edilmesi gereken bazı uyumluluk sorunları vardır. Daha fazla bilgi için Windows SDK'daki Liste Görünümü Denetimleri konusunun Uyumluluk Sorunları bölümüne bakın.

## <a name="handling-the-lvn_getdispinfo-notification"></a>LVN_GETDISPINFO Bildiriminin İşletilmesi

Sanal liste denetimleri çok az öğe bilgisi tutar. Madde seçimi ve odak bilgileri dışında, tüm madde bilgileri denetimin sahibi tarafından yönetilir. Bilgi, LVN_GETDISPINFO bir bildirim mesajı ile çerçeve tarafından istenir. İstenen bilgileri sağlamak için, sanal liste denetiminin (veya denetimin kendisi) sahibinin bu bildirimi işlemesi gerekir. Bu, [Sınıf Sihirbazı](reference/mfc-class-wizard.md) kullanılarak kolayca yapılabilir [(bkz.](../mfc/reference/mapping-messages-to-functions.md) Ortaya çıkan kod aşağıdaki örneğe benzer `CMyDialog` (sanal liste denetim nesnesinin sahibi ve iletişim kutusunun bildirimi işleme sayılacağı yer):

[!code-cpp[NVC_MFCControlLadenDialog#23](../mfc/codesnippet/cpp/virtual-list-controls_1.cpp)]

bildirim iletisi LVN_GETDISPINFO için işleyicide, ne tür bilgilerin istendiğini görmek için denetlemeniz gerekir. Olası değerler şunlardır:

- `LVIF_TEXT`*pszText* üyesi doldurulmalıdır.

- `LVIF_IMAGE`*iImage* üyesi nin doldurulması gerekir.

- `LVIF_INDENT`*IIndent* üyesi doldurulmalıdır.

- `LVIF_PARAM`*lParam* üyesi doldurulmalı. (Alt öğeler için mevcut değildir.)

- `LVIF_STATE`*Devlet* üyesinin doldurulması gerekiyor.

Daha sonra, istenen her türlü bilgiyi çerçeveye geri sağlamalısınız.

Aşağıdaki örnek (liste denetim nesnesi için bildirim işleyicisinin gövdesinden alınan) metin arabellekleri ve bir öğenin görüntüsü için bilgi sağlayarak olası bir yöntemi gösterir:

[!code-cpp[NVC_MFCControlLadenDialog#24](../mfc/codesnippet/cpp/virtual-list-controls_2.cpp)]

## <a name="caching-and-virtual-list-controls"></a>Önbelleğe Alma ve Sanal Liste Denetimleri

Bu tür bir liste denetimi büyük veri kümeleri için tasarlandığından, alma performansını artırmak için istenen madde verilerini önbelleğe almanız önerilir. Çerçeve, LVN_ODCACHEHINT bir bildirim iletisi göndererek önbelleği en iyi duruma getirmek için bir önbellek ipucu mekanizması sağlar.

Aşağıdaki örnek, işleyici işlevine geçirilen aralıkla önbelleği güncelleştirir.

[!code-cpp[NVC_MFCControlLadenDialog#25](../mfc/codesnippet/cpp/virtual-list-controls_3.cpp)]

Önbellek hazırlama ve koruma hakkında daha fazla bilgi için Windows SDK'daki Liste Görünümü Denetimleri konusunun Önbellek Yönetimi bölümüne bakın.

## <a name="finding-specific-items"></a>Belirli Öğeleri Bulma

LVN_ODFINDITEM bildirim iletisi, belirli bir liste denetim öğesinin bulunması gerektiğinde sanal liste denetimi tarafından gönderilir. Bildirim iletisi, liste görünümü denetimi hızlı anahtar erişimi aldığında veya LVM_FINDITEM bir ileti aldığında gönderilir. Arama bilgileri, **NMLVFINDITEM** yapısının bir üyesi olan **LVFINDINFO** yapısı şeklinde gönderilir. Liste denetim nesnenizin `OnChildNotify` işlevini geçersiz kılarak ve işleyicinin gövdesi içinde bu iletiyi işleyin, LVN_ODFINDITEM iletisini denetleyin. Bulunursa, uygun eylemi gerçekleştirin.

Liste görünümü denetimi tarafından verilen bilgilerle eşleşen bir öğeyi aramaya hazır olmalısınız. Başarılı olursa öğenin dizinini döndürmeniz veya eşleşen bir öğe bulunamazsa -1 döndürmeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
