---
title: Zengin Düzenleme Denetimine Genel Bakış
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC]
ms.assetid: ad589b9f-a3fd-4820-bf1f-6b1965997e68
ms.openlocfilehash: c45cb638ec860bb803c7de32065606dc3cc176b2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287719"
---
# <a name="overview-of-the-rich-edit-control"></a>Zengin Düzenleme Denetimine Genel Bakış

> [!IMPORTANT]
>  İletişim kutusunda bir zengin düzenleme denetimi kullanıyorsanız (SDI, MDI, uygulamanızın olmasına bakılmaksızın veya iletişim kutusu tabanlı), çağırmanız gerekir [Afxınitrichedit](../mfc/reference/application-information-and-management.md#afxinitrichedit) sonra önce iletişim kutusu görüntülenir. Bu işlevi çağırmak için tipik bir yerde programınıza ait olduğu `InitInstance` üye işlevi. Her zaman yalnızca uygulamayı ilk kez iletişim kutusunu görüntülemek için çağrı gerekmez. Çağrı gerekmez `AfxInitRichEdit` ile çalışıyorsanız `CRichEditView`.

Zengin düzenleme denetimleri ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) metin biçimlendirmesi için bir programlama arabirimi sağlar. Ancak, bir uygulamanın tüm biçimlendirme işlemlerini kullanıcı tarafından kullanılabilir hale getirmek için gerekli olan kullanıcı arabirimi bileşenleri uygulamalıdır. Diğer bir deyişle, seçili metni karakter veya paragraf özniteliklerini değiştirme denetimi destekleyen zengin düzenleme. Bazı örnekler öznitelikler karakterin kalın, italik yazı tipi ailesi ve nokta boyutu. Hizalama, kenar boşlukları ve sekme durakları paragraf öznitelikleri örnekleridir. Araç çubuğu düğmeleri, menü öğeleri ve bir biçim karakteri iletişim kutusu olup olmadığını ancak kullanıcı arabirimi sağlayan size olur. Zengin Düzenleme denetiminin öznitelikleri geçerli seçimi, sorgu işlevleri vardır. Bu işlevler öznitelikler için geçerli ayarları görüntülemek için örneğin, öznitelik biçimlendirme kalın karakter seçimi varsa, bir onay işareti komutu kullanıcı Arabirimi ayarı kullanın.

Karakter ve paragraf biçimlendirme hakkında daha fazla bilgi için bkz. [karakter biçimlendirme](../mfc/character-formatting-in-rich-edit-controls.md) ve [paragraf biçimlendirme](../mfc/paragraph-formatting-in-rich-edit-controls.md) bu konuda.

Zengin denetimleri destek neredeyse tüm işlemleri ve çok satırlı düzenleme denetimleri ile kullanılan bildirim iletilerini düzenleyin. Bu nedenle, denetimleri zaten kullanım düzenleme denetimleriyle kolayca zengin kullanmak için değiştirilebileceği uygulamaları düzenleyin. Ek iletileri ve bildirimleri uygulamaların işlevselliğini benzersiz zengin düzenleme denetimlerinde erişimini etkinleştirin. Düzenleme denetimleri hakkında daha fazla bilgi için bkz. [CEdit](../mfc/reference/cedit-class.md).

Bildirimleri hakkında daha fazla bilgi için bkz. [bir zengin düzenleme denetiminden bildirim](../mfc/notifications-from-a-rich-edit-control.md) bu konuda.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](../mfc/using-cricheditctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
