---
description: 'Daha fazla bilgi edinin: zengin düzenleme denetimine genel bakış'
title: Zengin Düzenleme Denetimine Genel Bakış
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC]
ms.assetid: ad589b9f-a3fd-4820-bf1f-6b1965997e68
ms.openlocfilehash: 9971eb7340ddf270c6094d239737c89cff66e6e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205973"
---
# <a name="overview-of-the-rich-edit-control"></a>Zengin Düzenleme Denetimine Genel Bakış

> [!IMPORTANT]
> İletişim kutusunda bir zengin düzenleme denetimi kullanıyorsanız (uygulamanızın SDI, MDI veya iletişim kutusu tabanlı olmasına bakılmaksızın), iletişim kutusu görüntülenmeden önce [AfxInitRichEdit](reference/application-information-and-management.md#afxinitrichedit) çağrısı yapmanız gerekir. Bu işlevi çağırmak için tipik bir yer, programınızın `InitInstance` üye işlevisiniz. İletişim kutusunu her görüntülediğinizde, yalnızca ilk kez bir kez çağırmanız gerekmez. İle çalışıyorsanız çağırmak zorunda değilsiniz `AfxInitRichEdit` `CRichEditView` .

Zengin düzenleme denetimleri ([CRichEditCtrl](reference/cricheditctrl-class.md)) metin biçimlendirme için bir programlama arabirimi sağlar. Ancak, bir uygulamanın biçimlendirme işlemlerini Kullanıcı için kullanılabilir hale getirmek için gereken herhangi bir kullanıcı arabirimi bileşenini uygulaması gerekir. Diğer bir deyişle, zengin düzenleme denetimi seçili metnin karakter veya paragraf özniteliklerinin değiştirilmesini destekler. Karakter özniteliklerine bazı örnekler kalın, italik, yazı tipi ailesi ve nokta boyutudur. Paragraf özniteliklerine örnek olarak hizalama, kenar boşlukları ve sekme duraklar dahildir. Ancak, bu, araç çubuğu düğmeleri, menü öğeleri veya Biçim karakteri iletişim kutusu olsun, Kullanıcı arabirimini sağlamak sizin için en iyisidir. Ayrıca, geçerli seçimin öznitelikleri için zengin düzenleme denetimini sorgulamak için işlevler de vardır. Bu işlevleri, özniteliklerin geçerli ayarlarını göstermek için kullanın, örneğin, seçimde kalın karakter biçimlendirme özniteliği varsa, komut Kullanıcı arabiriminde onay işareti ayarlama.

Karakter ve paragraf biçimlendirme hakkında daha fazla bilgi için bu konunun ilerleyen kısımlarında yer alan [karakter biçimlendirme](character-formatting-in-rich-edit-controls.md) ve [paragraf biçimlendirme](paragraph-formatting-in-rich-edit-controls.md) bölümüne bakın.

Zengin düzenleme denetimleri, çok satırlı düzenleme denetimleriyle kullanılan tüm işlemleri ve bildirim iletilerini destekler. Bu nedenle, düzenleme denetimlerini kullanan uygulamalar zengin düzenleme denetimleri kullanmak üzere kolayca değiştirilebilir. Ek iletiler ve bildirimler, uygulamaların zengin düzenleme denetimlerine özgü işlevlere erişmesini sağlar. Düzenleme denetimleri hakkında daha fazla bilgi için bkz. [Cedıt](reference/cedit-class.md).

Bildirimler hakkında daha fazla bilgi için bu konunun ilerleyen kısımlarında yer alan [bir zengin düzenleme denetiminden bildirimler](notifications-from-a-rich-edit-control.md) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](using-cricheditctrl.md)<br/>
[Denetimler](controls-mfc.md)
