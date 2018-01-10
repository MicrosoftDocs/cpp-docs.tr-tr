---
title: 'Sunucular: sunucu uygulama | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- servers, implementing
- OLE server applications [MFC], implementing OLE servers
ms.assetid: 5bd57e8e-3b23-4f23-9597-496fac2d24b5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 148a3da3c904f5c314c75fb71deede3c92163cc6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="servers-implementing-a-server"></a>Sunucular: Sunucu Uygulama
Bu makalede, MFC Uygulama Sihirbazı'nı görsel düzenleme sunucu uygulaması için oluşturduğu kodu açıklanmaktadır. Uygulama Sihirbazı'nı kullanmıyorsanız, bu makalede, bir sunucu uygulaması uygulamak için kod yazmanız gerekir alanlarını listeler.  
  
 Yeni bir sunucu uygulaması oluşturmak için Uygulama Sihirbazı'nı kullanıyorsanız, sizin için sunucuya özgü kodu önemli miktarda sağlar. Varolan bir uygulamaya görsel düzenleme sunucusu işlevselliği ekliyorsanız, gerekli sunucu kodu kalan eklemeden önce Uygulama Sihirbazı'nı sağlamış kod yinelenen gerekir.  
  
 Uygulama Sihirbazı'nı sağlayan sunucu kodu birkaç kategoride toplanabilir:  
  
-   Sunucu kaynaklarını tanımlama:  
  
    -   Sunucunun kendi penceresinde katıştırılmış bir öğe düzenlenirken kullanılan menü kaynağı.  
  
    -   Sunucu yerinde etkin olduğunda kullanılan menü ve araç çubuğu kaynakları.  
  
     Bu kaynaklar hakkında daha fazla bilgi için bkz: [menüler ve kaynaklar: sunucu ekleme](../mfc/menus-and-resources-server-additions.md).  
  
-   Bir öğe sınıfı tanımlama türetilen `COleServerItem`. Sunucu öğeleri hakkında daha fazla ayrıntı için bkz: [sunucular: sunucu öğeleri](../mfc/servers-server-items.md).  
  
-   Belge sınıfına temel sınıfını değiştirme `COleServerDoc`. Daha fazla ayrıntı için bkz: [sunucular: sunucu belgeleri uygulama](../mfc/servers-implementing-server-documents.md).  
  
-   Çerçeve pencere sınıfı tanımlama türetilen `COleIPFrameWnd`. Daha fazla ayrıntı için bkz: [sunucular: yerinde çerçeve pencereleri uygulama](../mfc/servers-implementing-in-place-frame-windows.md).  
  
-   Sunucu uygulaması için bir giriş Windows kayıt veritabanı'nda oluşturma ve OLE sistemiyle sunucunun yeni bir örneğini kaydetme. Bu konu hakkında daha fazla bilgi için bkz: [kayıt](../mfc/registration.md).  
  
-   Başlatma ve sunucu uygulaması başlatılıyor. Bu konu hakkında daha fazla bilgi için bkz: [kayıt](../mfc/registration.md).  
  
 Daha fazla bilgi için bkz: [COleServerItem](../mfc/reference/coleserveritem-class.md), [COleServerDoc](../mfc/reference/coleserverdoc-class.md), ve [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md) içinde *sınıf kitaplığı başvurusu*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sunucuları](../mfc/servers.md)   
 [Kapsayıcıları](../mfc/containers.md)   
 [Menüler ve kaynaklar (OLE)](../mfc/menus-and-resources-ole.md)   
 [Kayıt](../mfc/registration.md)

