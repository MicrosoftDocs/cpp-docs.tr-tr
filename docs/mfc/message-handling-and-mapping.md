---
title: "İleti işleme ve eşleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC, messages
- message handling [MFC]
- message maps [MFC]
ms.assetid: 62fe2a1b-944c-449d-a0f0-63c11ee0a3cb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1e6c13ed0bb19ef1ed2864378e151c6be8d98887
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="message-handling-and-mapping"></a>İleti İşleme ve Eşleme
Bu makale ailesi iletiler ve komutlar MFC çerçevesi tarafından nasıl işleneceğini ve bağlamadan nasıl işleyici işlevlerini açıklar.  
  
 Windows için geleneksel programlarda Windows iletilerini pencere yordamı büyük SWITCH deyiminde işlenir. MFC yerine kullanır [ileti eşlemeleri](../mfc/message-categories.md) ayrı sınıf üyesi işlevleri için doğrudan ileti eşlemesi için. İleti eşlemeleri sanal işlevler daha verimli bu amaçla ve iletilerin en uygun C++ nesne tarafından işlenmesine izin ver-uygulama, belge, Görünüm ve benzeri. Kimlikleri denetlemek ya da tek bir ileti veya iletiler, komut kimlikleri aralığını eşleyin.  
  
 **WM_COMMAND** iletileri — genellikle menüler, araç çubuğu düğmeleri veya Hızlandırıcıları tarafından oluşturulan — de ileti eşleme mekanizması kullanır. MFC tanımlayan bir standart [yönlendirme](../mfc/command-routing.md) penceresi, Görünüm ve etkin belgeler programınızın uygulama arasında komut iletileri çerçeve. Gerekirse bu yönlendirme geçersiz kılabilirsiniz.  
  
 İleti eşlemeleri (örneğin, menüleri ve araç çubuğu düğmeleri) kullanıcı arabirimi nesnelerini güncelleştirme için bir yol da sağlamanız etkinleştirerek veya geçerli bağlamı uyacak şekilde devre dışı.  
  
 İletileri ve ileti kuyrukları Windows hakkında genel bilgi için bkz: [iletileri ve ileti kuyrukları](http://msdn.microsoft.com/library/windows/desktop/ms632590) Windows SDK'sındaki.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Framework'teki İletiler ve Komutlar](../mfc/messages-and-commands-in-the-framework.md)  
  
-   [Bir ileti işleyicisini framework çağırması](../mfc/how-the-framework-calls-a-handler.md)  
  
-   [Framework'ün İleti Eşlemelerini Araması](../mfc/how-the-framework-searches-message-maps.md)  
  
-   [İleti İşleyici İşlevlerini Bildirme](../mfc/declaring-message-handler-functions.md)  
  
-   [İletileri İşlevlere Eşleme](../mfc/reference/mapping-messages-to-functions.md)  
  
-   [Durum çubuğunda komut bilgilerini görüntüleme](../mfc/how-to-display-command-information-in-the-status-bar.md)  
  
-   [Dinamik güncelleştirme kullanıcı arabirimi nesneleri](../mfc/how-to-update-user-interface-objects.md)  
  
-   [Nasıl yapılır: Bir Şablon Sınıfı için İleti Eşlemesi Oluşturma](../mfc/how-to-create-a-message-map-for-a-template-class.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../mfc/mfc-concepts.md)   
 [Genel MFC konuları](../mfc/general-mfc-topics.md)   
 [CWnd sınıfı](../mfc/reference/cwnd-class.md)   
 [CCmdTarget Sınıfı](../mfc/reference/ccmdtarget-class.md)
