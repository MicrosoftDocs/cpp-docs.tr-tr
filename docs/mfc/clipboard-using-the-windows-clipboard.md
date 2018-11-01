---
title: 'Pano: Windows Panosunu Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- Clipboard commands
- Cut/Copy and Paste command handler functions [MFC]
- handler functions, Cut/Copy and Paste commands
- Clipboard [MFC], commands
- commands [MFC], implementing Edit
- Clipboard commands [MFC], implementing
- Windows Clipboard [MFC]
- Clipboard [MFC], Windows Clipboard API
ms.assetid: 24415b42-9301-4a70-b69a-44c97918319f
ms.openlocfilehash: 67bc337af2cf55a4f39698f730ce14a3369ef742
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460703"
---
# <a name="clipboard-using-the-windows-clipboard"></a>Pano: Windows Panosunu Kullanma

Bu konuda, standart Windows panosu API'si MFC uygulamanızda kullanmayı açıklar.

Çoğu uygulama için Windows kesme veya Windows panosuna veri kopyalama ve pano verilerini yapıştırma destekler. Pano veri biçimlerini, uygulamalar arasında farklılık gösterir. Framework, sınırlı sayıda sınıfları için yalnızca sınırlı sayıda Pano biçimlerini destekler. Pano ile ilgili komutları normalde uygular — Kes, Kopyala ve Yapıştır — görünümünüz için Düzen menüsünde. Komut kimlikleri bu komutları için sınıf kitaplığı tanımlar: **ıd_edıt_cut**, **ıd_edıt_copy**, ve **ıd_edıt_paste**. Kendi ileti satırı yönergeleri de tanımlanır.

[İletiler ve komutlar Framework](../mfc/messages-and-commands-in-the-framework.md) menü komutları, uygulamanızdaki bir işleyici işlevi için menü komutunu eşleyerek nasıl ele alınacağını açıklar. Uygulamanızın Düzen menüsündeki Pano komutları için işleyici işlevleri tanımlamıyor sürece devre dışı kalır. Kesme ve kopyalama komutları için işleyici işlevleri yazmak için uygulamanızda seçimi uygulayın. Paste komutu için bir işleyici işlevi yazmak için uygulamanızın kabul edebilen bir biçimde veri içerip içermediğini görmek için Pano sorgulayın. Örneğin, kopyalama komutu etkinleştirmek için bir işleyici aşağıdakine benzer bir şey yazabiliriz:

[!code-cpp[NVC_MFCListView#2](../atl/reference/codesnippet/cpp/clipboard-using-the-windows-clipboard_1.cpp)]

Kes, Kopyala ve Yapıştır komutları yalnızca belirli bağlamlarda anlamlıdır. Yalnızca bir şey seçilidir ve Paste komutu yalnızca bir şey, panoya Kes ve Kopyala komutlarını etkinleştirilmesi gerekir. Güncelleştirme işleyici işlevleri, etkinleştirme veya devre dışı bağlama bağlı olarak bu komutları tanımlayarak bu davranışı sağlayabilir. Daha fazla bilgi için [kullanıcı arabirimi nesnelerini güncelleştirme](../mfc/how-to-update-user-interface-objects.md).

Microsoft Foundation Class Kitaplığı ile metin düzenleme için Pano destek sağlar `CEdit` ve `CEditView` sınıfları. OLE sınıfları da OLE öğeleri içeren uygulama yönelik pano işlemlerini basitleştirin. OLE sınıfları hakkında daha fazla bilgi için bkz. [Pano: OLE Pano mekanizmasını kullanma](../mfc/clipboard-using-the-ole-clipboard-mechanism.md).

Menü komutları, geri alma gibi diğer uygulama Düzenle (**ıd_edıt_undo**) ve yineleme (**ıd_edıt_redo**), aynı zamanda size bırakılır. Uygulamanız bu komutları desteklemiyorsa, bunları Visual C++ kaynak düzenleyicileri kullanarak kaynak dosyasından kolayca silebilirsiniz.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Veri kopyalama ve yapıştırma](../mfc/clipboard-copying-and-pasting-data.md)

- [OLE Pano mekanizmasını kullanma](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Pano](../mfc/clipboard.md)

