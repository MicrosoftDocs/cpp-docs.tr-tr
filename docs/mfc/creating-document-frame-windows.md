---
title: "Belge çerçeve pencereleri oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- frame windows [MFC], creating
- document templates [MFC], and document frame windows
- windows [MFC], creating
- runtime, class information
- run-time class [MFC], and document frame window creation
- document frame windows [MFC], creating
- MFC, frame windows
ms.assetid: 8671e239-b76f-4dea-afa8-7024e6e58ff5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9098026c1a38f8e60093415ba1c5a2b3678b64d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-document-frame-windows"></a>Belge Çerçeve Pencereleri Oluşturma
[Belge/görünüm oluşturma](../mfc/document-view-creation.md) gösterir nasıl [CDocTemplate](../mfc/reference/cdoctemplate-class.md) nesne düzenler Çerçeve penceresi, belge ve görünüm oluşturma ve tüm birbirine bağlama. Üç [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) bağımsız değişkenleri `CDocTemplate` Oluşturucusu belirtin çerçeve penceresi, belge ve belge şablonu yanıt olarak yeni bir komut dosyasındaki gibi kullanıcı komutları dinamik olarak oluşturur. görünüm sınıfları menü veya bir MDI Pencere menüsünden Yeni Pencere komutu. Bir görünüm ve belge için bir çerçeve penceresi oluşturduğunda, belge şablonu daha sonra kullanmak için bu bilgileri depolar.  
  
 İçin [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) doğru türetilmiş çalışması için bir mekanizma çerçeve penceresi sınıfları bildirilen, ile [DECLARE_DYNCREATE](../mfc/reference/run-time-object-model-services.md#declare_dyncreate) makrosu. Belge çerçeve pencereleri sınıfının dinamik yapım mekanizmasını kullanarak oluşturmak için framework gerek duyduğu olmasıdır `CObject`.  
  
 Kullanıcı bir belge oluşturur komutu seçtiğinde framework belge nesnesi, kendi Görünüm ve görünümde görüntülenecek çerçeve penceresi oluşturmak için belge şablonu çağırır. Belge çerçeve penceresi oluşturur, belge şablonu uygun sınıfın bir nesnesi oluşturur — öğesinden türetilmiş bir sınıf [CFrameWnd](../mfc/reference/cframewnd-class.md) SDI uygulamanın veya gelen [Cmdıchildwnd](../mfc/reference/cmdichildwnd-class.md) MDI için uygulama. Framework sonra çerçeve penceresi çağıran [LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) üye işlevi kaynaklardan oluşturma bilgi almak için ve Windows penceresi oluşturulamadı. Çerçeve pencere tanıtıcının çerçeve penceresi nesnesine ekler. Daha sonra belge çerçeve penceresi alt pencere olarak görünümü oluşturur.  
  
 Karar dikkatli [başlatılacağı zaman](../mfc/when-to-initialize-cwnd-objects.md) , `CWnd`-türetilmiş bir nesne içermelidir.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [(Dinamik oluşturma mekanizması kendi) CObject'ten sınıf türetme](../mfc/deriving-a-class-from-cobject.md)  
  
-   [Belge/görünüm oluşturma (şablonları ve çerçeve penceresi oluşturma)](../mfc/document-view-creation.md)  
  
-   [Çerçeve pencerelerini yok etme](../mfc/destroying-frame-windows.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çerçeve Pencerelerini Kullanma](../mfc/using-frame-windows.md)

