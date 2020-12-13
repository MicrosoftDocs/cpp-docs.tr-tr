---
description: 'Daha fazla bilgi edinin: sanal liste denetimleri'
title: Sanal Liste Denetimleri
ms.date: 11/04/2016
helpviewer_keywords:
- cache, virtual list control item data
- list controls [MFC], virtual
- list controls [MFC], List view
- virtual list controls
ms.assetid: 319f841f-e426-423a-8276-d93f965b0b45
ms.openlocfilehash: 1d441fc74ab6b1ae395ce0b23bcba08c1703213f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331350"
---
# <a name="virtual-list-controls"></a>Sanal Liste Denetimleri

Sanal liste denetimi, LVS_OWNERDATA stili olan bir liste görünümü denetimidir. Bu stil, denetimin **DWORD** 'e kadar bir öğe sayısını desteklemesini sağlar (varsayılan öğe sayısı yalnızca bir olarak genişletilir **`int`** ). Ancak, bu stil tarafından sunulan en büyük avantaj, her seferinde bellekte yalnızca bir veri öğeleri alt kümesine sahip olabilir. Bu, sanal liste görünümü denetiminin kendisini büyük veritabanlarla kullanılmak üzere ödünç almasına olanak tanır. Bu, belirli verilere erişim yöntemlerinin zaten yerinde olduğu yerdir.

> [!NOTE]
> MFC ' de sanal liste işlevselliği sağlamaya ek olarak `CListCtrl` [Clienstview](../mfc/reference/clistview-class.md) sınıfında aynı işlevselliği de sağlar.

Sanal liste denetimleri geliştirilirken bilmeniz gereken bazı uyumluluk sorunları vardır. Daha fazla bilgi için Windows SDK List-View denetimleri konusunun uyumluluk sorunları bölümüne bakın.

## <a name="handling-the-lvn_getdispinfo-notification"></a>LVN_GETDISPINFO bildirimini işleme

Sanal liste denetimleri çok az öğe bilgilerini korur. Öğe seçimi ve odak bilgileri hariç, tüm öğe bilgileri denetimin sahibi tarafından yönetilir. Bilgi, LVN_GETDISPINFO bir bildirim iletisi aracılığıyla çerçeve tarafından istenir. İstenen bilgileri sağlamak için, sanal liste denetiminin (veya denetimin kendisi) sahibi bu bildirimi işlemelidir. Bu, [sınıf Sihirbazı](reference/mfc-class-wizard.md) kullanılarak kolayca yapılabilir (bkz. [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md)). Sonuç kodu aşağıdaki örnekteki gibi görünmelidir ( `CMyDialog` sanal liste denetim nesnesine ve iletişim kutusunun bildirimi işleme aldığı yer):

[!code-cpp[NVC_MFCControlLadenDialog#23](../mfc/codesnippet/cpp/virtual-list-controls_1.cpp)]

LVN_GETDISPINFO bildirim iletisine yönelik İşleyicide, ne tür bilgilerin istenmekte olduğunu görmeniz gerekir. Olası değerler şunlardır:

- `LVIF_TEXT`*PszText* üyesinin doldurulması gerekir.

- `LVIF_IMAGE`*IImage* üyesinin doldurulması gerekir.

- `LVIF_INDENT`*Igirintile* üyesinin doldurulması gerekir.

- `LVIF_PARAM`*LParam* üyesi doldurulmalıdır. (Alt öğeler için yok.)

- `LVIF_STATE`*Durum* üyesinin doldurulması gerekir.

Ardından, çerçeveye hangi bilgilerin geri istendiğini sağlamanız gerekir.

Aşağıdaki örnek (liste denetim nesnesi için bildirim işleyicisinin gövdesinden alınmıştır), bir öğenin metin arabellekleri ve görüntüsü için bilgi sağlayarak olası bir yöntemi gösterir:

[!code-cpp[NVC_MFCControlLadenDialog#24](../mfc/codesnippet/cpp/virtual-list-controls_2.cpp)]

## <a name="caching-and-virtual-list-controls"></a>Önbelleğe alma ve sanal liste denetimleri

Bu tür bir liste denetimi büyük veri kümelerine yönelik olduğundan, alma performansını geliştirmek için istenen öğe verilerini önbelleğe almanız önerilir. Framework, bir LVN_ODCACHEHINT bildirim iletisi göndererek önbelleğin iyileştirmesine yardımcı olmak için bir önbellek ipucu mekanizması sağlar.

Aşağıdaki örnek, önbelleği Handler işlevine geçirilen aralıkla güncelleştirir.

[!code-cpp[NVC_MFCControlLadenDialog#25](../mfc/codesnippet/cpp/virtual-list-controls_3.cpp)]

Bir önbelleği hazırlama ve sürdürme hakkında daha fazla bilgi için Windows SDK List-View denetimleri konusunun önbellek yönetimi bölümüne bakın.

## <a name="finding-specific-items"></a>Belirli öğeleri bulma

LVN_ODFINDITEM bildirim iletisi, belirli bir liste denetim öğesi bulunması gerektiğinde sanal liste denetimi tarafından gönderilir. Liste görünümü denetimi hızlı anahtar erişimi aldığında veya LVM_FINDITEM bir ileti aldığında bildirim iletisi gönderilir. Arama bilgileri, **Nmlvfindıtem** yapısının üyesi olan bir **Lvfinınfo** yapısı biçiminde gönderilir. `OnChildNotify`Liste denetim nesnenizin işlevini geçersiz kılarak ve işleyicinin gövdesinde bu iletiyi işleyin, LVN_ODFINDITEM iletisini kontrol edin. Bulunursa, uygun eylemi gerçekleştirin.

Liste görünümü denetimi tarafından verilen bilgilerle eşleşen bir öğeyi aramaya hazır olmanız gerekir. Başarılı olursa öğenin dizinini döndürmeli veya eşleşen öğe bulunmazsa-1 ' i döndürmelisiniz.

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
