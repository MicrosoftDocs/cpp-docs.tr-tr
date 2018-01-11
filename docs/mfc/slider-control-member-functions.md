---
title: "Kaydırıcı denetimi üye işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CSliderCtrl class [MFC], methods
- slider controls [MFC], member functions
ms.assetid: dbde49ee-7306-4d14-a6ce-d09aa198178f
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1bd6c1d05ce7b137e6153ad2ea3fc5df99565a52
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="slider-control-member-functions"></a>Kaydırıcı Denetimi Üye İşlevleri
Bir uygulama kaydırıcıyı kaydırıcı denetimi hakkında bilgi almak için denetimin üye işlevleri çağırabilir ([CSliderCtrl](../mfc/reference/csliderctrl-class.md)) ve onun özelliklerini değiştirmek için.  
  
 (Diğer bir deyişle, değeri kullanıcı seçilir) kaydırıcı konumunu almak için kullanmak [GetPos](../mfc/reference/csliderctrl-class.md#getpos) üye işlevi. Kaydırıcı konumunu ayarlamak için kullanın [SetPos](../mfc/reference/csliderctrl-class.md#setpos) üye işlevi. Herhangi bir zamanda kullandığınız `VerifyPos` üye işlevi kaydırıcıyı minimum ve maksimum değerleri arasında olduğundan emin olun.  
  
 Kaydırıcı denetimi aralığını kaydırıcı denetimi gösterebilir bitişik değerler kümesidir. Çoğu uygulama kullanır [SetRange](../mfc/reference/csliderctrl-class.md#setrange) ilk oluşturulduğunda kaydırıcı denetimi aralığını ayarlamak için üye işlevi. Uygulamalar dinamik olarak alter aralığı kaydırıcı denetimi kullanarak oluşturulduktan sonra [SetRangeMax](../mfc/reference/csliderctrl-class.md#setrangemax) ve [SetRangeMin](../mfc/reference/csliderctrl-class.md#setrangemin) üye işlevleri. Kullanıcı kaydırıcı denetimi ile çalışmayı bitirdiğinde dinamik olarak genellikle değiştirilecek aralığı sağlayan bir uygulama son aralığı ayarlarını alır. Bu ayarları almak için kullanmak [GetRange](../mfc/reference/csliderctrl-class.md#getrange), [GetRangeMax](../mfc/reference/csliderctrl-class.md#getrangemax), ve [GetRangeMin](../mfc/reference/csliderctrl-class.md#getrangemin) üye işlevleri.  
  
 Bir uygulamanın kullanabileceği `TBS_AUTOTICKS` otomatik olarak görüntülenen bir kaydırıcı denetimin çizgisi stili. Ancak, bir uygulama, konum veya çizgilerinin sıklığını denetlemek gerekirse, üye işlevleri kullanılabilir.  
  
 Değer çizgisi konumunu belirlemek için bir uygulamanın kullanabileceği [SetTic](../mfc/reference/csliderctrl-class.md#settic) üye işlevi. [SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq) üye işlevi kaydırıcı denetimin aralıktaki düzenli aralıklarla görünen işaretleri değer ayarlamak bir uygulama sağlar. Örneğin, uygulama, bu üye işlevi yalnızca 10 çizgilerinin 1 ile 100 aralığında görüntülemek için kullanabilirsiniz.  
  
 Karşılık gelen bir değer çizgisi aralığı dizine almak kullanın [GetTic](../mfc/reference/csliderctrl-class.md#gettic) üye işlevi. [GetTicArray](../mfc/reference/csliderctrl-class.md#getticarray) üye işlevi bu dizinler dizisini alır. İstemci koordinatları değer çizgisi konumunu almak için [GetTicPos](../mfc/reference/csliderctrl-class.md#getticpos) üye işlevi. Bir uygulama kullanarak çizgilerinin sayısı alabilirsiniz [GetNumTics](../mfc/reference/csliderctrl-class.md#getnumtics) üye işlevi.  
  
 [ClearTics](../mfc/reference/csliderctrl-class.md#cleartics) üye işlevi tüm kaydırıcı denetimin çizgilerinin kaldırır.  
  
 Kaydırıcı denetim satır boyutu uygulama aldığında, kaydırıcıyı ne kadar taşır belirler bir **TB_LINEDOWN** veya **TB_LINEUP** bildirim iletisi. Benzer şekilde, sayfa boyutu yanıta belirler **TB_PAGEDOWN** ve **TB_PAGEUP** bildirim iletileri. Uygulamaları alabilir ve satır ve sayfa boyutu değerleri kullanarak ayarlayın [GetLineSize](../mfc/reference/csliderctrl-class.md#getlinesize), [SetLineSize](../mfc/reference/csliderctrl-class.md#setlinesize), [GetPageSize](../mfc/reference/csliderctrl-class.md#getpagesize), ve [SetPageSize](../mfc/reference/csliderctrl-class.md#setpagesize) üye işlevleri.  
  
 Bir uygulama üye işlevleri kaydırıcı denetimi boyutlarını almak için kullanabilirsiniz. [GetThumbRect](../mfc/reference/csliderctrl-class.md#getthumbrect) üye işlevi kaydırıcı için sınırlayıcı dikdörtgenini alır. [GetChannelRect](../mfc/reference/csliderctrl-class.md#getchannelrect) üye işlevi kaydırıcı denetim kanalı için sınırlayıcı dikdörtgenini alır. (Kanal, kaydırıcıyı hareket eder ve bir aralığı seçili değilken Vurgu içeren üzerinden alandır.)  
  
 Kaydırıcı denetimi varsa `TBS_ENABLESELRANGE` stili, kullanıcı bitişik değerleri aralığı seçebilirsiniz. Üye işlevleri dinamik olarak ayarlanacak seçim aralığı izin verir. [SetSelection](../mfc/reference/csliderctrl-class.md#setselection) üye işlevi, başlangıç ve bitiş seçimi konumlarını ayarlar. Kullanıcı bir seçim aralığı ayarını tamamlandığında, bir uygulama ayarlarını kullanarak alabilirsiniz [GetSelection](../mfc/reference/csliderctrl-class.md#getselection) üye işlevi. Bir kullanıcının seçimini silmek için kullanın [ClearSel](../mfc/reference/csliderctrl-class.md#clearsel) üye işlevi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSliderCtrl kullanma](../mfc/using-csliderctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

