---
title: "Zengin düzenleme denetimine genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: rich edit controls [MFC]
ms.assetid: ad589b9f-a3fd-4820-bf1f-6b1965997e68
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5bd43266b88d48cea0b680f97b8f498a1ff5a859
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="overview-of-the-rich-edit-control"></a>Zengin Düzenleme Denetimine Genel Bakış
> [!IMPORTANT]
>  Bir iletişim kutusunda bir zengin düzenleme denetimine kullanıyorsanız (uygulamanızın SDI, MDI, olmasına bakılmaksızın veya iletişim tabanlı), çağırmalısınız [Afxınitrichedit](../mfc/reference/application-information-and-management.md#afxinitrichedit) önce iletişim kutusu görüntülendiğinde. Bu işlevi çağırmak için bir tipik programınızın içinde yerdir `InitInstance` üye işlevi. Her zaman yalnızca ilk kez iletişim kutusunu görüntülemek için çağrı gerekmez. Çağrı gerekmez `AfxInitRichEdit` ile çalışıyorsanız `CRichEditView`.  
  
 Zengin düzenleme denetimleri ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) metin biçimlendirme için bir programlama arabirimi sağlar. Ancak, bir uygulamanın tüm biçimlendirme işlemlerini kullanıcı için kullanılabilir hale getirmek için gerekli olan kullanıcı arabirimi bileşenlerini uygulamalıdır. Diğer bir deyişle, zengin denetim destekler seçili metnin karakter veya paragraf özniteliklerini değiştirme düzenleyin. Bazı örnekler öznitelikleri karakterinin kalın, italik, yazı tipi ailesi ve nokta boyutu. Hizalama, kenar boşluklarını ve sekme durakları paragraf özniteliklerini örneklerindendir. Araç çubuğu düğmeleri, menü öğelerini veya biçimi karakter iletişim kutusu olup olmadığını ancak, kullanıcı arabirimi sağlamak için size bağlıdır. Zengin düzenleme denetimine öznitelikleri geçerli seçim için sorgu işlevleri de vardır. Bu işlevler öznitelikleri için geçerli ayarları görüntülemek için örneğin, seçim kalın karakter özniteliği biçimlendirme varsa onay işareti UI komutunda ayarı kullanın.  
  
 Karakter ve paragraf biçimlendirme hakkında daha fazla bilgi için bkz: [karakter biçimlendirme](../mfc/character-formatting-in-rich-edit-controls.md) ve [paragraf biçimlendirmesini](../mfc/paragraph-formatting-in-rich-edit-controls.md) bu konuda daha sonra.  
  
 Zengin denetimleri destek neredeyse tüm işlemleri ve çok satırlı düzenleme denetimleri ile kullanılan bildirim iletilerini düzenleyin. Bu nedenle, zaten düzenleme denetimleri kullan kolayca zengin kullanmak için değiştirilebileceği uygulamaları denetimleri düzenleyin. Ek iletiler ve bildirimler uygulamaların işlevselliğini benzersiz zengin düzenleme denetimlerinde erişimini etkinleştirin. Düzenleme denetimleri hakkında daha fazla bilgi için bkz: [CEdit](../mfc/reference/cedit-class.md).  
  
 Bildirimleri hakkında daha fazla bilgi için bkz: [bir zengin düzenleme denetiminden bildirim](../mfc/notifications-from-a-rich-edit-control.md) bu konuda daha sonra.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRichEditCtrl kullanma](../mfc/using-cricheditctrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

