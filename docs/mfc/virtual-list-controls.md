---
title: Sanal liste denetimleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- cache, virtual list control item data
- list controls [MFC], virtual
- list controls [MFC], List view
- virtual list controls
ms.assetid: 319f841f-e426-423a-8276-d93f965b0b45
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0b580e455aab7ff95beb85c02b8e3ca79dfa8a46
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="virtual-list-controls"></a>Sanal Liste Denetimleri
Sanal liste denetimi sahip bir liste görünümü denetimi olan **LVS_OWNERDATA** stili. Bu stili bir öğe sayısı kadar desteklemek denetim sağlayan bir `DWORD` (varsayılan öğe sayısı için yalnızca genişleten bir `int`). Ancak, bu stili tarafından sağlanan en büyük avantajı veri öğelerin alt kümesine herhangi bir zamanda bellekte yeterlidir yeteneğidir. Bu bilgi, büyük veritabanları ile kullanmak için kendisini ödünç vermek sanal liste görünümü denetimi verilerine erişme belirli yöntemleri zaten yerinde nerede sağlar.  
  
> [!NOTE]
>  Sanal liste işlevselliği sağlayan yanı sıra `CListCtrl`, MFC de aynı işlevleri sağlar [CListView](../mfc/reference/clistview-class.md) sınıfı.  
  
 Sanal liste denetimleri geliştirirken bilmeniz gereken bazı uyumluluk sorunları vardır. Daha fazla bilgi için Windows SDK'sı liste görünümü denetimleri konusundaki uyumluluk sorunları bölümüne bakın.  
  
## <a name="handling-the-lvngetdispinfo-notification"></a>LVN_GETDISPINFO bildirimini işleme  
 Sanal liste denetimleri çok az öğe bilgilerini korur. Öğe seçimi ve odak bilgi hariç, tüm öğesi bilgisi denetim sahibi tarafından yönetilir. Bilgi framework tarafından istenen bir **LVN_GETDISPINFO** bildirim iletisi. İstenen bilgileri sağlamak için sanal liste denetimi (veya Denetim) sahibi bu bildirim işlemelidir. Bu kolayca yapılabilir Özellikler penceresini kullanarak (bkz [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md)). Sonuç kodu aşağıdaki örnekteki gibi görünmelidir (burada `CMyDialog` sanal liste denetim nesnenin sahibi ve iletişim bildirimini işleme):  
  
 [!code-cpp[NVC_MFCControlLadenDialog#23](../mfc/codesnippet/cpp/virtual-list-controls_1.cpp)]  
  
 İşleyicisindeki **LVN_GETDISPINFO** bildirim iletisi, gerekir hangi tür bilgileri istenen olmadığını denetleyin. Olası değerler şunlardır:  
  
-   `LVIF_TEXT` `pszText` Üye doldurulmalıdır.  
  
-   `LVIF_IMAGE` `iImage` Üye doldurulmalıdır.  
  
-   **LVIF_INDENT** *iIndent* üye doldurulmalıdır.  
  
-   `LVIF_PARAM` *LParam* üye doldurulmalıdır. (Alt öğelerini yoktur.)  
  
-   `LVIF_STATE` *Durumu* üye doldurulmalıdır.  
  
 Ardından Framework'e istenen hangi bilgilerin vermeniz gerekir.  
  
 (Liste denetim nesnesi için bildirim işleyicisi gövdesinden alınan) aşağıdaki örnekte, bir öğenin resim ve metin arabelleği için bilgileri sağlayarak bir olası yöntem gösterilmektedir:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#24](../mfc/codesnippet/cpp/virtual-list-controls_2.cpp)]  
  
## <a name="caching-and-virtual-list-controls"></a>Önbelleğe alma ve sanal liste denetimleri  
 Bu tür bir liste denetimini büyük veri kümeleri için tasarlandığından, istenen öğe veri alma performansını artırmak için önbelleğe önerilir. Framework önbellek göndererek iyileştirme yardımcı olması için önbellek ipuçları bir mekanizma sağlar bir **LVN_ODCACHEHINT** bildirim iletisi.  
  
 Aşağıdaki örnek önbelleğini işleyici işlevine geçirilen aralığı ile güncelleştirir.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#25](../mfc/codesnippet/cpp/virtual-list-controls_3.cpp)]  
  
 Hazırlama ve önbellek bakımı hakkında daha fazla bilgi için Windows SDK'sı liste görünümü denetimleri konusunda önbellek yönetimi bölümüne bakın.  
  
## <a name="finding-specific-items"></a>Belirli öğeleri bulma  
 **LVN_ODFINDITEM** bildirim iletisi belirli liste denetim öğesi bulunamadı gerektiğinde sanal liste denetim tarafından gönderilir. Bildirim iletisi liste görünümü denetimi hızlı anahtar erişimi aldığında veya, aldığında gönderilen bir **LVM_FINDITEM** ileti. Arama bilgilerini biçiminde gönderilen bir **LVFINDINFO** üyesi olduğu yapısı, **NMLVFINDITEM** yapısı. Geçersiz kılarak bu iletiyi işlemek `OnChildNotify` listenizin işlevi kontrol nesne ve işleyici gövdesi içinde denetle **LVN_ODFINDITEM** ileti. Varsa bulunan, uygun eylemi gerçekleştirin.  
  
 Liste Görünümü denetimi tarafından verilen bilgileri eşleşen bir öğe aramak hazırlıklı olmalıdır. Eşleşen öğe yok bulunursa başarılı olursa öğe veya -1 dizinini döndürmelidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CListCtrl kullanma](../mfc/using-clistctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

