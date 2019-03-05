---
title: Kaydırıcı Denetimi Üye İşlevleri
ms.date: 11/04/2016
helpviewer_keywords:
- CSliderCtrl class [MFC], methods
- slider controls [MFC], member functions
ms.assetid: dbde49ee-7306-4d14-a6ce-d09aa198178f
ms.openlocfilehash: a88dd1a49eb928261393a4473ee7eb53628c607a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57296910"
---
# <a name="slider-control-member-functions"></a>Kaydırıcı Denetimi Üye İşlevleri

Bir uygulama kaydırıcı denetimi üye işlevleri kaydırıcı denetimi ile ilgili bilgi almak için çağırabilir ([CSliderCtrl](../mfc/reference/csliderctrl-class.md)) ve özelliklerini değiştirmek için.

(Diğer bir deyişle, kullanıcının seçilen değer) kaydırıcı konumunu almak için kullanın [GetPos](../mfc/reference/csliderctrl-class.md#getpos) üye işlevi. Kaydırıcı konumunu ayarlamak için kullanın [SetPos](../mfc/reference/csliderctrl-class.md#setpos) üye işlevi. Herhangi bir zamanda kullandığınız `VerifyPos` kaydırıcı minimum ve maksimum değerler arasında olduğundan emin olmak için üye işlevi.

Bir kaydırıcı denetimi aralığı kaydırıcı denetimi gösterebilir bitişik değerler kümesidir. Çoğu uygulama kullanır [SetRange](../mfc/reference/csliderctrl-class.md#setrange) ilk oluşturulduğunda bir kaydırıcı denetimi aralığını ayarlamak için üye işlevi. Uygulamalar dinamik olarak alter aralık kaydırıcı denetimi kullanarak oluşturulduktan sonra [SetRangeMax](../mfc/reference/csliderctrl-class.md#setrangemax) ve [SetRangeMin](../mfc/reference/csliderctrl-class.md#setrangemin) üye işlevleri. Kullanıcı kaydırıcı denetimi ile çalışmayı bitirdiğinde dinamik olarak genellikle değiştirilecek aralığı sağlayan bir uygulama son aralığı ayarlarını alır. Bu ayarları almak için kullanın [GetRange](../mfc/reference/csliderctrl-class.md#getrange), [GetRangeMax](../mfc/reference/csliderctrl-class.md#getrangemax), ve [GetRangeMin](../mfc/reference/csliderctrl-class.md#getrangemin) üye işlevleri.

Bir uygulamayı otomatik olarak görüntülenen bir kaydırıcı denetiminin çizgisi TBS_AUTOTICKS stilini kullanabilirsiniz. Ancak, bir uygulamanın konumuna veya değer çizgilerinin sıklığını denetlemek gerekiyorsa, çok sayıda üye işlev kullanılabilir.

Onay işareti konumunu ayarlamak için bir uygulama kullanabilirsiniz [SetTic](../mfc/reference/csliderctrl-class.md#settic) üye işlevi. [SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq) üye işlevi değer çizgisi kaydırıcı denetiminin aralıktaki düzenli aralıklarla görünen işaretleri ayarlamak bir uygulama sağlar. Örneğin, uygulama 1 ile 100 arası bir dizi yalnızca 10 çizgilerini görüntülemek için bu üye işlevi kullanabilirsiniz.

Karşılık gelen bir değer çizgisi için aralığı dizine almaya [GetTic](../mfc/reference/csliderctrl-class.md#gettic) üye işlevi. [GetTicArray](../mfc/reference/csliderctrl-class.md#getticarray) üye işlevi, bu dizinler dizisini alır. İstemci koordinatları, bir onay işareti konumunu almak için kullanın [GetTicPos](../mfc/reference/csliderctrl-class.md#getticpos) üye işlevi. Bir uygulama kullanarak değer çizgileri sayısı alabilir [GetNumTics](../mfc/reference/csliderctrl-class.md#getnumtics) üye işlevi.

[ClearTics](../mfc/reference/csliderctrl-class.md#cleartics) üye işlevi bir kaydırıcı denetiminin çizgilerinin tümünün kaldırır.

Ne kadar uygulama TB_LINEDOWN veya TB_LINEUP bir bildirim iletisi aldığında kaydırıcıyı hareket edeceği bir kaydırıcı denetiminin satır boyutunu belirler. Benzer şekilde, yanıt TB_PAGEDOWN ve TB_PAGEUP bildirim iletileri için sayfa boyutunu belirler. Uygulamaları alabilir ve satır ve sayfa boyutu değerleri kullanarak ayarlayın [GetLineSize](../mfc/reference/csliderctrl-class.md#getlinesize), [SetLineSize](../mfc/reference/csliderctrl-class.md#setlinesize), [GetPageSize](../mfc/reference/csliderctrl-class.md#getpagesize), ve [SetPageSize](../mfc/reference/csliderctrl-class.md#setpagesize) üye işlevleri.

Bir uygulama, üye işlevleri, bir kaydırıcı denetimi boyutlarını almak için kullanabilirsiniz. [GetThumbRect](../mfc/reference/csliderctrl-class.md#getthumbrect) üye işlevi, kaydırıcı için sınırlayıcı dikdörtgeni alır. [GetChannelRect](../mfc/reference/csliderctrl-class.md#getchannelrect) üye işlevi, kaydırıcı denetim kanalı için sınırlayıcı dikdörtgeni alır. (Kanal kaydırıcı taşıyan ve aralığı seçildiğinde vurgulama içeren üzerinden alandır.)

Bir kaydırıcı denetimi TBS_ENABLESELRANGE stili varsa, kullanıcı bitişik değer aralığını seçebilirsiniz. Üye işlevleri sayısını dinamik olarak ayarlanacak seçenek aralığındaki izin verin. [SetSelection](../mfc/reference/csliderctrl-class.md#setselection) üye işlevi, başlangıç ve bitiş konumları seçilen ayarlar. Kullanıcı bir seçim aralığını ayarlama tamamlandığında, uygulama ayarlarını kullanarak alabilirsiniz [GetSelection](../mfc/reference/csliderctrl-class.md#getselection) üye işlevi. Bir kullanıcının seçiminin silmek için kullanın [ClearSel](../mfc/reference/csliderctrl-class.md#clearsel) üye işlevi.

## <a name="see-also"></a>Ayrıca bkz.

[CSliderCtrl Kullanma](../mfc/using-csliderctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
