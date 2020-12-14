---
description: 'Daha fazla bilgi edinin: kaydırıcı denetimi üye Işlevleri'
title: Kaydırıcı Denetimi Üye İşlevleri
ms.date: 11/04/2016
helpviewer_keywords:
- CSliderCtrl class [MFC], methods
- slider controls [MFC], member functions
ms.assetid: dbde49ee-7306-4d14-a6ce-d09aa198178f
ms.openlocfilehash: 57108872a779bc4876be89afd5b81008f69a0837
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216905"
---
# <a name="slider-control-member-functions"></a>Kaydırıcı Denetimi Üye İşlevleri

Bir uygulama kaydırıcı denetimi ([CSliderCtrl](../mfc/reference/csliderctrl-class.md)) hakkında bilgi almak ve özelliklerini değiştirmek için kaydırıcı denetiminin üye işlevlerini çağırabilir.

Kaydırıcının konumunu almak için (yani, kullanıcının seçtiği değer) [GetPos](../mfc/reference/csliderctrl-class.md#getpos) üye işlevini kullanın. Kaydırıcının konumunu ayarlamak için [SetPos](../mfc/reference/csliderctrl-class.md#setpos) üye işlevini kullanın. Herhangi bir zamanda, `VerifyPos` Kaydırıcının en düşük ve en yüksek değerler arasında olduğundan emin olmak için üye işlevini kullanabilirsiniz.

Kaydırıcı denetiminin aralığı, kaydırıcı denetiminin temsil ettiği bitişik değerler kümesidir. Çoğu uygulama, ilk oluşturulduğunda kaydırıcı denetiminin aralığını ayarlamak için [SetRange](../mfc/reference/csliderctrl-class.md#setrange) member işlevini kullanır. Uygulamalar, [SetRangeMax](../mfc/reference/csliderctrl-class.md#setrangemax) ve [SetRangeMin](../mfc/reference/csliderctrl-class.md#setrangemin) üye işlevleri kullanılarak kaydırıcı denetimi oluşturulduktan sonra aralığı dinamik bir şekilde değiştirebilir. Aralığın dinamik olarak değiştirilmesine izin veren bir uygulama, Kullanıcı kaydırıcı denetimiyle çalışmayı bitirdiğinde son Aralık ayarlarını alır. Bu ayarları almak için [GetRange](../mfc/reference/csliderctrl-class.md#getrange), [GetRangeMax](../mfc/reference/csliderctrl-class.md#getrangemax)ve [GetRangeMin](../mfc/reference/csliderctrl-class.md#getrangemin) üye işlevlerini kullanın.

Bir uygulama, otomatik olarak bir kaydırıcı denetiminin değer çizgilerinin görüntülenmesini sağlamak için TBS_AUTOTICKS stilini kullanabilir. Bununla birlikte, bir uygulamanın değer çizgilerinin konumunu veya sıklığını denetmeleri gerekiyorsa, bir dizi üye işlevi kullanılabilir.

Bir değer işaretinin konumunu ayarlamak için, bir uygulama [SetTic](../mfc/reference/csliderctrl-class.md#settic) üye işlevini kullanabilir. [SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq) üye işlevi, bir uygulamanın kaydırıcı denetiminin aralığında düzenli aralıklarla görünen değer çizgilerini ayarlamasına olanak tanır. Örneğin, uygulama bu üye işlevini, 1 ile 100 arasında yalnızca 10 onay işareti göstermek için kullanabilir.

Bir değer işaretine karşılık gelen aralıktaki dizini almak için [GetTic](../mfc/reference/csliderctrl-class.md#gettic) üye işlevini kullanın. [GetTicArray](../mfc/reference/csliderctrl-class.md#getticarray) üye işlevi bu dizinlerin bir dizisini alır. Değer çizgisinin konumunu almak için, istemci koordinatları ' nde [GetTicPos](../mfc/reference/csliderctrl-class.md#getticpos) üye işlevini kullanın. Bir uygulama, [Getnumtika](../mfc/reference/csliderctrl-class.md#getnumtics) üye işlevini kullanarak değer çizgilerinin sayısını alabilir.

[Clemakalens](../mfc/reference/csliderctrl-class.md#cleartics) üye işlevi, kaydırıcı denetiminin tüm değer çizgilerini kaldırır.

Kaydırıcı denetiminin çizgi boyutu, bir uygulama TB_LINEDOWN veya TB_LINEUP bildirim iletisi aldığında kaydırıcının ne kadar hareket edeceğini belirler. Benzer şekilde, sayfa boyutu, TB_PAGEDOWN ve TB_PAGEUP bildirim iletilerinin yanıtını belirler. Uygulamalar, satır ve sayfa boyut değerlerini [GetLineSize](../mfc/reference/csliderctrl-class.md#getlinesize), [SetLineSize](../mfc/reference/csliderctrl-class.md#setlinesize), [GetPageSize](../mfc/reference/csliderctrl-class.md#getpagesize)ve [SetPageSize](../mfc/reference/csliderctrl-class.md#setpagesize) üye işlevlerini kullanarak alabilir ve ayarlayabilir.

Bir uygulama, bir kaydırıcı denetiminin boyutlarını almak için üye işlevleri kullanabilir. [GetThumbRect](../mfc/reference/csliderctrl-class.md#getthumbrect) üye işlevi kaydırıcı için sınırlayıcı dikdörtgeni alır. [GetChannelRect](../mfc/reference/csliderctrl-class.md#getchannelrect) üye işlevi kaydırıcı denetiminin kanalının sınırlayıcı dikdörtgenini alır. (Kanal, kaydırıcının hareket edeceği ve bir Aralık seçildiğinde vurguyu içeren alandır.)

Kaydırıcı denetiminde TBS_ENABLESELRANGE stili varsa, Kullanıcı bundan bir ardışık değer aralığı seçebilir. Bir dizi üye işlevi seçim aralığının dinamik olarak ayarlanmasına izin verir. [SetSelection](../mfc/reference/csliderctrl-class.md#setselection) üye işlevi bir seçimin başlangıç ve bitiş konumlarını ayarlar. Kullanıcı bir seçim aralığı ayarlamayı tamamladığında, bir uygulama [GetSelection](../mfc/reference/csliderctrl-class.md#getselection) üye işlevini kullanarak ayarları alabilir. Bir kullanıcının seçimini temizlemek için [ClearSel](../mfc/reference/csliderctrl-class.md#clearsel) member işlevini kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[CSliderCtrl Kullanma](../mfc/using-csliderctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
