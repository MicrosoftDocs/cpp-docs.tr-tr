---
title: Zengin Düzenleme Denetimine Genel Bakış
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC]
ms.assetid: ad589b9f-a3fd-4820-bf1f-6b1965997e68
ms.openlocfilehash: 9ef696bc348dfb18b797b487224b97261020e11c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366866"
---
# <a name="overview-of-the-rich-edit-control"></a>Zengin Düzenleme Denetimine Genel Bakış

> [!IMPORTANT]
> Bir iletişim kutusunda zengin bir edit denetimi kullanıyorsanız (uygulamanız SDI, MDI veya iletişim tabanlı olup olmadığına bakılmaksızın), iletişim kutusu görüntülenmeden önce [AfxInitRichEdit'i](../mfc/reference/application-information-and-management.md#afxinitrichedit) bir kez aramanız gerekir. Bu işlevi aramak için tipik bir yer `InitInstance` programınızın üye işlevindedir. İletişim kutusunu her görüntülediğiniz zaman, yalnızca ilk kez aramanız gerekmez. Eğer çalışıyorsanız `CRichEditView`aramak `AfxInitRichEdit` zorunda değilsin.

Zengin edit denetimleri[(CRichEditCtrl)](../mfc/reference/cricheditctrl-class.md)metni biçimlendirmek için bir programlama arabirimi sağlar. Ancak, bir uygulama, biçimlendirme işlemlerini kullanıcının kullanımına açmak için gereken kullanıcı arabirimi bileşenlerini uygulamalıdır. Diğer bir arada, zengin edit denetimi seçili metnin karakter veya paragraf özniteliklerinin değiştirilmesini destekler. Karakter öznitelikleribazı örnekler kalın, italik, yazı tipi ailesi ve nokta boyutu vardır. Paragraf özniteliklerine örnek olarak hizalama, kenar boşlukları ve sekme durakları verilebilir. Ancak, ister araç çubuğu düğmeleri, ister menü öğeleri veya biçim karakter iletişim kutusu olsun, kullanıcı arabirimini sağlamak size kalmış. Geçerli seçimin öznitelikleri için zengin edit denetimini sorgulamak için işlevler de vardır. Özniteliklerin geçerli ayarlarını görüntülemek için bu işlevleri kullanın, örneğin, seçim kalın karakter biçimlendirme özniteliği varsa komut UI'de bir onay işareti ayarlayın.

Karakter ve paragraf biçimlendirme hakkında daha fazla bilgi için, bu konunun ilerleyen saatlerinde [Karakter Biçimlendirme](../mfc/character-formatting-in-rich-edit-controls.md) ve Paragraf [Biçimlendirme'ye](../mfc/paragraph-formatting-in-rich-edit-controls.md) bakın.

Zengin düzen denetimleri, çok satırlı düzen denetimleri ile kullanılan hemen hemen tüm işlemleri ve bildirim iletilerini destekler. Böylece, zaten denetimleri kullanan uygulamalar zengin edit denetimleri kullanmak için kolayca değiştirilebilir. Ek iletiler ve bildirimler, uygulamaların zengin denetim denetimlerine özgü işlevselliklere erişmesini sağlar. Denetimleri edin hakkında daha fazla bilgi için [CEdit'e](../mfc/reference/cedit-class.md)bakın.

Bildirimler hakkında daha fazla bilgi için, bu konunun ilerleyen saatlerinde [Zengin Bir Edit Denetimi'nden gelen Bildirimler'e](../mfc/notifications-from-a-rich-edit-control.md) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](../mfc/using-cricheditctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
