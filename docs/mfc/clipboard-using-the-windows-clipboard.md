---
title: 'Pano: Windows panosunu kullanma | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6063a27495d46e4b54f3133b92689e4b0faaa631
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="clipboard-using-the-windows-clipboard"></a>Pano: Windows Panosunu Kullanma
Bu konu, standart Windows panosu API'si MFC uygulamanız içinde kullanmayı açıklar.  
  
 Windows için çoğu uygulamayı kesme veya Windows panosuna veri kopyalama ve pano verilerini yapıştırma destekler. Pano veri biçimleri, uygulamalar arasında farklılık gösterir. Framework sınıfları, sınırlı sayıda için Pano biçimleri, yalnızca sınırlı sayıda destekler. Pano ilgili komutları normalde gerçekleştireceksiniz — kesme, kopyalama ve yapıştırma — görünümünüz için Düzen menüsünde. Bu komutların komut kimlikleri sınıf kitaplığı tanımlar: **ıd_edıt_cut**, **ıd_edıt_copy**, ve **ıd_edıt_paste**. Kendi ileti satırı istemleri da tanımlanır.  
  
 [İletiler ve komutlar Framework'te](../mfc/messages-and-commands-in-the-framework.md) menü komutları, uygulamanızdaki bir işleyici işlevi menü komutu eşleyerek nasıl ele alınacağını açıklar. Uygulamanızı işleyici işlevleri Pano komutları için Düzen menüsünden tanımlamıyor sürece, devre dışı kalır. İşleyici işlevleri kesme ve kopyalama komutları yazmak için uygulamanızda seçimi uygulayın. Paste komutu için bir işleyici işlevi yazmak için uygulamanızın kabul edebileceği bir biçimde veri içerip içermediğini görmek için Pano sorgu. Örneğin, Kopyala komutu etkinleştirmek için bir işleyici aşağıdakine benzer yazabilirsiniz:  
  
 [!code-cpp[NVC_MFCListView#2](../atl/reference/codesnippet/cpp/clipboard-using-the-windows-clipboard_1.cpp)]  
  
 Kes, Kopyala ve Yapıştır komutları yalnızca belirli bağlamlarda anlamlıdır. Kesme ve kopyalama komutları yalnızca bir şey seçilir ve yalnızca bir şey olduğunda Yapıştır komut Pano'da olduğunda etkinleştirilmesi gerekir. Bu davranışı etkinleştirmek veya devre dışı bağlam bağlı olarak bu komutları güncelleştirme işleyici işlevleri tanımlayarak sağlayabilir. Daha fazla bilgi için bkz: [güncelleştirme kullanıcı arabirimi nesnelerini nasıl](../mfc/how-to-update-user-interface-objects.md).  
  
 Microsoft Foundation Class Kitaplığı ile metin düzenleme için Pano destek sağlamasına `CEdit` ve `CEditView` sınıfları. OLE sınıfları ayrıca OLE öğeleri içeren uygulama Pano işlemleri basitleştirir. OLE sınıfları hakkında daha fazla bilgi için bkz: [Pano: OLE Pano mekanizmasını kullanma](../mfc/clipboard-using-the-ole-clipboard-mechanism.md).  
  
 Diğer uygulama geri alma gibi menü komutlarını Düzenle (**ıd_edıt_undo**) ve Yinele (**ıd_edıt_redo**), size ayrıca bırakılır. Uygulamanız bu komutları desteklemiyorsa, bunları Visual C++ kaynak düzenleyicileri kullanarak kaynak dosyanızdan kolayca silebilirsiniz.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Veri kopyalama ve yapıştırma](../mfc/clipboard-copying-and-pasting-data.md)  
  
-   [OLE Pano mekanizmasını kullanma](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pano](../mfc/clipboard.md)

