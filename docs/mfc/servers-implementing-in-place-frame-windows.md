---
title: "Sunucular: Yerinde çerçeve pencereleri uygulama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- frame windows [MFC], implementing
- OLE server applications [MFC], frame windows
- servers, in-place frame windows
- frame windows [MFC], in-place
- in-place frame windows
ms.assetid: 09bde4d8-15e2-4fba-8d14-9b954d926b92
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1102d6459701314c5b0d5b3e96908052504262d1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="servers-implementing-in-place-frame-windows"></a>Sunucular: Yerinde Çerçeve Pencereleri Uygulama
Bu makalede, sunucu uygulamanızı oluşturmak için Uygulama Sihirbazı'nı kullanmazsanız, görsel düzenleme server uygulamanızda yerinde çerçeve pencereleri uygulamak için yapmanız gerekir açıklanmaktadır. Bu makalede açıklanan yordamı izlemek yerine, varolan bir yerinde çerçeve pencere sınıfı Uygulama Sihirbazı tarafından oluşturulan bir uygulama veya Visual C++ ile sağlanan bir örnek kullanabilirsiniz.  
  
#### <a name="to-declare-an-in-place-frame-window-class"></a>Yerinde çerçeve pencere sınıfı bildirmek için  
  
1.  Yerinde çerçeve penceresi sınıfından türetilen `COleIPFrameWnd`.  
  
    -   Kullanım `DECLARE_DYNCREATE` makrosu sınıfı üstbilgi dosyası.  
  
    -   Kullanım `IMPLEMENT_DYNCREATE` makrosu sınıf uygulama (.cpp) dosyası. Bu çerçevesi tarafından oluşturulacak bu sınıfın nesnelerini sağlar.  
  
2.  Bildirme bir `COleResizeBar` çerçeve penceresi sınıfında üye. Sunucu uygulamalarında yerinde yeniden boyutlandırma desteklemek istiyorsanız bu gereklidir.  
  
     Bildirme bir `OnCreate` ileti işleyicisi (kullanarak **özellikleri** penceresi) ve arama **oluşturma** için `COleResizeBar` varsa, tanımlanan üye,.  
  
3.  Araç çubuğu varsa, bildirme bir `CToolBar` çerçeve penceresi sınıfında üye.  
  
     Geçersiz kılma `OnCreateControlBars` sunucu yerinde etkin olduğunda bir araç çubuğu oluşturmak için üye işlevi. Örneğin:  
  
     [!code-cpp[NVC_MFCOleServer#1](../mfc/codesnippet/cpp/servers-implementing-in-place-frame-windows_1.cpp)]  
  
     5. adım aşağıdaki bu kodu tartışması bakın.  
  
4.  Bu yerinde çerçeve pencere sınıfı için üstbilgi dosyası Main.cpp dosyanıza ekleyin.  
  
5.  İçinde `InitInstance` çağrı, uygulama sınıfı için `SetServerInfo` yerinde çerçeve penceresi açın ve yerinde düzenleme kullanılacak ve kaynakları belirtmek için belge şablonu nesnesinin işlevi.  
  
 İşlevi bir dizi çağrıları **varsa** deyimi kaynaklardan araç sağlanan server oluşturur. Bu noktada, araç kapsayıcının penceresi hiyerarşi parçasıdır. Bu araç türetildiği için `CToolBar`, sahibi değiştirmediğiniz sürece sahibi, kapsayıcı uygulamanın çerçeve penceresi, kendi iletileri geçer. İşte çağrısı `SetOwner` gereklidir. Bu çağrı komutları sunucunun yerinde çerçeve penceresi, sunucuya geçirilmesi için iletilerini neden olacak şekilde gönderildiği penceresini değiştirir. Bu, sunucunun sağladığı araç çubuğunda işlemleri tepki sağlar.  
  
 Araç çubuğu bit eşlem kimliği server uygulamanızda tanımlanan diğer yerinde kaynakları ile aynı olmalıdır. Bkz: [menüler ve kaynaklar: sunucu ekleme](../mfc/menus-and-resources-server-additions.md) Ayrıntılar için.  
  
 Daha fazla bilgi için bkz: [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md), [COleResizeBar](../mfc/reference/coleresizebar-class.md), ve [CDocTemplate::SetServerInfo](../mfc/reference/cdoctemplate-class.md#setserverinfo) içinde *sınıf kitaplığı başvurusu*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sunucuları](../mfc/servers.md)   
 [Sunucular: sunucu uygulama](../mfc/servers-implementing-a-server.md)   
 [Sunucular: Sunucu belgeleri uygulama](../mfc/servers-implementing-server-documents.md)   
 [Sunucular: Sunucu öğeleri](../mfc/servers-server-items.md)

