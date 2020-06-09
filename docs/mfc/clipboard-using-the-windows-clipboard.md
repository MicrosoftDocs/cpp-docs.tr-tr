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
ms.openlocfilehash: 1b11bfe18443858de0dd7032f72fecadb1d6ebdd
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626044"
---
# <a name="clipboard-using-the-windows-clipboard"></a>Pano: Windows Panosunu Kullanma

Bu konuda, MFC uygulamanızda standart Windows Pano API 'sinin nasıl kullanılacağı açıklanmaktadır.

Windows için çoğu uygulama, verileri Windows panosuna kesip panodan veri yapıştırmayı destekler. Pano veri biçimleri, uygulamalar arasında farklılık gösterir. Çerçeve, sınırlı sayıda sınıf için yalnızca sınırlı sayıda Pano biçimini destekler. Genellikle, panonuzun düzenleme menüsünde Pano ile ilgili komutları — Kes, Kopyala ve Yapıştır — ' ı uygulayacaksınız. Sınıf kitaplığı şu komutlar için komut kimliklerini tanımlar: **ID_EDIT_CUT**, **ID_EDIT_COPY**ve **ID_EDIT_PASTE**. İleti satırı istemlerinin de tanımlanması gerekir.

[Çerçevede bulunan iletiler ve komutlar](messages-and-commands-in-the-framework.md) , menü komutunu bir işleyici işlevine eşleyerek uygulamanızdaki menü komutlarının nasıl işleneceğini açıklar. Uygulamanız, düzenleme menüsündeki Pano komutları için işleyici işlevleri tanımladıkları sürece devre dışı kalır. Kes ve Kopyala komutlarının işleyici işlevlerini yazmak için, uygulamanızda seçim uygulayın. Yapıştır komutu için bir işleyici işlevi yazmak üzere, uygulamanızın kabul edebileceği bir biçimde veri içerip içermediğini görmek için panoyu sorgulayın. Örneğin, copy komutunu etkinleştirmek için, aşağıdakine benzer bir işleyici yazabilirsiniz:

[!code-cpp[NVC_MFCListView#2](../atl/reference/codesnippet/cpp/clipboard-using-the-windows-clipboard_1.cpp)]

Kes, Kopyala ve Yapıştır komutları yalnızca belirli bağlamlarda anlamlıdır. Kes ve Kopyala komutlarının yalnızca bir öğe seçildiğinde ve Yapıştır komutu yalnızca panoda olduğunda etkinleştirilmelidir. Bu davranışı, içeriğe bağlı olarak bu komutları etkinleştiren veya devre dışı bırakan güncelleştirme işleyici işlevlerini tanımlayarak sağlayabilirsiniz. Daha fazla bilgi için bkz. [Kullanıcı arabirimi nesnelerini güncelleştirme](how-to-update-user-interface-objects.md).

Microsoft Foundation Class Kitaplığı, ve sınıflarıyla metin düzenlemesi için Pano desteği sağlar `CEdit` `CEditView` . OLE sınıfları Ayrıca OLE öğeleriyle ilgili Pano işlemlerini uygulamayı da basitleştirir. OLE sınıfları hakkında daha fazla bilgi için bkz. [Pano: OLE Pano mekanizmasını kullanma](clipboard-using-the-ole-clipboard-mechanism.md).

Geri al (**ID_EDIT_UNDO**) ve yinele (**ID_EDIT_REDO**) gibi diğer düzenleme menüsü komutlarının uygulanması da sizin için de aynı. Uygulamanız bu komutları desteklemiyorsa, Visual C++ kaynak düzenleyicilerini kullanarak bunları kaynak dosyanızdaki kolayca silebilirsiniz.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Verileri kopyalama ve yapıştırma](clipboard-copying-and-pasting-data.md)

- [OLE panosu mekanizmasını kullanma](clipboard-using-the-ole-clipboard-mechanism.md)

## <a name="see-also"></a>Ayrıca bkz.

[Pano](clipboard.md)
