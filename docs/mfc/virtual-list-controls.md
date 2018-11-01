---
title: Sanal Liste Denetimleri
ms.date: 11/04/2016
helpviewer_keywords:
- cache, virtual list control item data
- list controls [MFC], virtual
- list controls [MFC], List view
- virtual list controls
ms.assetid: 319f841f-e426-423a-8276-d93f965b0b45
ms.openlocfilehash: b9da918017d300d7af61b1fd3ab27869e136bb8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50573697"
---
# <a name="virtual-list-controls"></a>Sanal Liste Denetimleri

Sanal liste LVS_OWNERDATA stilde bir liste görünümü denetimi denetimidir. Denetim öğesi sayısı kadar desteklemek bu stil sağlayan bir **DWORD** (varsayılan öğe sayısı yalnızca için genişleten bir **int**). Ancak, bu stil tarafından sağlanan en büyük avantajı özelliği yalnızca bir alt veri öğelerinin bellekte herhangi bir zamanda sahip olur. Veri erişimi belirli yöntemleri zaten yerinde olduğu bu bilgi, büyük veritabanları ile kullanmak için kendi ödünç vermek sanal liste görünümü denetimi sağlar.

> [!NOTE]
>  Sanal liste işlevselliği sağlayan yanı sıra `CListCtrl`, MFC de aynı işlevi sağlar [CListView](../mfc/reference/clistview-class.md) sınıfı.

Sanal liste denetimleri geliştirirken bilmeniz gereken bazı uyumluluk sorunları vardır. Daha fazla bilgi için Windows SDK'sı liste görünümü denetimi konusundaki uyumluluk sorunları bölümüne bakın.

## <a name="handling-the-lvngetdispinfo-notification"></a>LVN_GETDISPINFO bildirimini işleme

Sanal liste denetimleri çok az öğesi bilgilerini koruyun. Öğe seçimi ve odak bilgileri dışında tüm öğesi bilgilerini denetim sahibi tarafından yönetilir. Bilgi LVN_GETDISPINFO bildirim iletisi aracılığıyla framework tarafından istenir. Sanal liste denetim (veya Denetim) sahibi, istenen bilgileri sağlamak için bu bildirim işlemesi gerekir. Bu kolayca yapılabilir Özellikler penceresinden (bkz [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md)). Sonuç kodu aşağıdaki örnek gibi görünmelidir (burada `CMyDialog` sanal liste denetim nesnenin sahibi ve iletişim, bildirim işleme):

[!code-cpp[NVC_MFCControlLadenDialog#23](../mfc/codesnippet/cpp/virtual-list-controls_1.cpp)]

LVN_GETDISPINFO bildirim iletisi işleyicisinde hangi tür bilgileri istenen görmek için denetlemelisiniz. Olası değerler şunlardır:

- `LVIF_TEXT` *PszText* üye doldurulmalıdır.

- `LVIF_IMAGE` *İImage* üye doldurulmalıdır.

- `LVIF_INDENT` *İIndent* üye doldurulmalıdır.

- `LVIF_PARAM` *LParam* üye doldurulmalıdır. (Alt öğelerini yok.)

- `LVIF_STATE` *Durumu* üye doldurulmalıdır.

Ardından, hangi bilgileri geri framework istenen sunmalıdır.

(Liste denetim nesnesi bildirimi işleyicisi gövdesinden taken) aşağıdaki örnek, bir öğenin resim ve metin arabelleği için bilgi sağlayarak olası bir yöntemi gösterir:

[!code-cpp[NVC_MFCControlLadenDialog#24](../mfc/codesnippet/cpp/virtual-list-controls_2.cpp)]

## <a name="caching-and-virtual-list-controls"></a>Önbelleğe alma ve sanal liste denetimleri

Bu tür bir liste denetimini büyük veri kümeleri için tasarlandığından, istenen öğe veri alımı performansını artırmak için önbelleğe önerilir. Framework, önbelleğin bir LVN_ODCACHEHINT bildirim iletisi göndererek en iyi duruma getirme yardımcı olmak için önbellek ipucu bir mekanizma sağlar.

Aşağıdaki örnek, işleyici işlevine geçirilen aralıkla önbelleği güncelleştirir.

[!code-cpp[NVC_MFCControlLadenDialog#25](../mfc/codesnippet/cpp/virtual-list-controls_3.cpp)]

Hazırlama ve önbellek bakımı hakkında daha fazla bilgi için Windows SDK'sı liste görünümü denetimi konusundaki önbellek Yönetim bölümüne bakın.

## <a name="finding-specific-items"></a>Belirli öğeleri bulma

Belirli listesi denetim öğesini bulunması gerektiğinde LVN_ODFINDITEM bildirim iletisi sanal liste denetim tarafından gönderilir. Liste Görünümü denetimi hızlı anahtar erişimi aldığında veya bir LVM_FINDITEM iletisi aldığında bildirim iletisi gönderilir. Arama bilgilerini biçiminde gönderilen bir **LVFINDINFO** üye yapısı, **NMLVFINDITEM** yapısı. Geçersiz kılarak bu iletiyi işlemek `OnChildNotify` listenize işlevi denetim nesnesi ve işleyici gövdesi içinde için LVN_ODFINDITEM iletisine bakın. Varsa bulunan, uygun eylemi gerçekleştirin.

Liste Görünümü denetimi tarafından verilen bilgileri eşleşen bir öğeyi aramak hazırlıklı olmalıdır. Eşleşen hiçbir öğe bulunamazsa öğesi başarılı olursa veya -1 dizinini döndürmelidir.

## <a name="see-also"></a>Ayrıca Bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

