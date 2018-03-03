---
title: "OLE arka planı: Uygulama stratejileri | Microsoft Docs"
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
- OLE [MFC], development strategy
- OLE applications [MFC], implementing OLE
- applications [OLE], implementing OLE
ms.assetid: 0875ddae-99df-488c-82c6-164074a81058
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7325cb5cb7be4750507d8694ba8bc5efc3ce8606
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ole-background-implementation-strategies"></a>OLE Arka Planı: Uygulama Stratejileri
Uygulamanızın bağlı olarak, OLE desteği eklemek için dört olası uygulama stratejileri vardır:  
  
-   Yeni bir uygulama yazıyorsanız.  
  
     Bu durum genellikle en az gerektirir çalışır. MFC Uygulama Sihirbazı'nı çalıştırın ve Gelişmiş Özellikler veya belge desteği, bileşik bir iskelet uygulama oluşturmak için seçin. Makaleyi bu seçeneklerin ve ne yaptıklarını hakkında daha fazla bilgi için bkz [bir MFC EXE Program oluşturma](../mfc/reference/mfc-application-wizard.md).  
  
-   Microsoft Foundation Class Kitaplığı ile sürüm 2.0 veya üstü OLE desteklemiyor yazılmış bir program var.  
  
     MFC Uygulama Sihirbazı daha önce belirtildiği gibi yeni bir uygulama oluşturun ve ardından kopyalayıp yeni uygulama kodundan varolan uygulamanıza yapıştırın. Bu sunucular, kapsayıcı ya da otomatik uygulamalar için çalışır. MFC bkz [KARALAMA](../visual-cpp-samples.md) bu strateji örneği için örnek.  
  
-   OLE sürüm 1.0 desteği uygulayan bir Microsoft Foundation Class Kitaplığı programı var.  
  
     Bkz: [MFC Teknik Not 41](../mfc/tn041-mfc-ole1-migration-to-mfc-ole-2.md) bu dönüştürme stratejisi için.  
  
-   Microsoft Foundation sınıflarını kullanarak yazılmadı olabilir veya OLE desteği uygulanmadı ve bir uygulamaya sahip.  
  
     Bu durum, en fazla çalışmayı gerektirir. Bir yaklaşım ise ilk stratejisi olduğu gibi yeni bir uygulama oluşturun ve sonra kopyalayın ve mevcut kodunuzu yapıştırın. Mevcut kodunuzu C'de yazılmışsa, C++ kodu olarak derleyebilirsiniz şekilde değiştirmeniz gerekebilir. Ardından C kodunuzu Windows API çağrıları, Microsoft Foundation sınıflarını kullanmak için değiştirmeniz gerekmez. Büyük olasılıkla bu yaklaşım bazı programınızın 2.0 ve Microsoft temel sınıfları daha sonraki sürümleri tarafından kullanılan belge/görünüm mimarisinin desteklemek üzere yeniden yapılandırma gerektirir. Bu mimari ile ilgili daha fazla bilgi için bkz: [Teknik Not 25](../mfc/tn025-document-view-and-frame-creation.md).  
  
 Üzerinde bir strateji karar verdikten sonra ya da okuma gereken [kapsayıcıları](../mfc/containers.md) veya [sunucuları](../mfc/servers.md) makaleler (yazma uygulama türünü bağlı olarak) veya örnek programlar veya her ikisi de inceleyin. MFC OLE örnekleri [OCLIENT](../visual-cpp-samples.md) ve [HIERSVR](../visual-cpp-samples.md) nasıl kapsayıcılar ve sunucular, çeşitli yönlerini sırasıyla uygulandığını göstermektedir. Bu makaleler boyunca çeşitli noktalarda tartışılan teknikleri örnekleri olarak bu örnekte belirli işlevler için anılacaktır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE arka planı](../mfc/ole-background.md)   
 [Kapsayıcılar: bir kapsayıcı uygulama](../mfc/containers-implementing-a-container.md)   
 [Sunucular: sunucu uygulama](../mfc/servers-implementing-a-server.md)   
 [MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md)

