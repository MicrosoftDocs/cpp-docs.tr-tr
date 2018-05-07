---
title: Zengin düzenleme denetimine genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rich edit controls [MFC]
ms.assetid: ad589b9f-a3fd-4820-bf1f-6b1965997e68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 143fc93fb07d9ac7c4e803bbce426c114c02bfeb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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
 [Denetimler](../mfc/controls-mfc.md)

