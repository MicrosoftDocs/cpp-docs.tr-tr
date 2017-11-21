---
title: "TN025: Belge, Görünüm ve çerçeve oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.creation
dev_langs: C++
helpviewer_keywords:
- documents [MFC], view and frame creation
- TN025
ms.assetid: 09254d72-6e1d-43db-80e9-693887dbeda2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: da86912b6d5ec1989d55cf6bffbee9732722f8e1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="tn025-document-view-and-frame-creation"></a>TN025: Belge, Görünüm ve Çerçeve Oluşturma
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
 Bu Not WinApps, DocTemplates, belgeler, çerçeve ve görünümler oluşturma ve sahipliği sorunları açıklar.  
  
## <a name="winapp"></a>WinApp  
 Bir `CWinApp` sistem nesnesi.  
  
 Bu statik olarak oluşturulur ve framework'ün iç uygulaması tarafından başlatılan `WinMain`. Öğesinden türetilmelidir `CWinApp` faydalı bir şey için (özel durum: MFC uzantı DLL'leri olmamalıdır bir `CWinApp` örneği — başlatma yapılır `DllMain` yerine).  
  
 Bir `CWinApp` nesnenin sahibi belge şablonları listesini (bir `CPtrList`). Uygulama başına bir veya birden çok belge şablonu yoktur. DocTemplates genellikle yüklenir (diğer bir deyişle, bir dize dizisi) kaynak dosyasından `CWinApp::InitInstance`.  
  
```  
pTemplate = new CDocTemplate(IDR_MYDOCUMENT, ...);

AddDocTemplate(pTemplate);
```  
  
 Bir `CWinApp` nesnenin sahibi uygulamadaki tüm çerçeve pencereleri. Uygulama için ana çerçeve penceresi depolanması gereken **CWinApp::m_pMainWnd**; genellikle ayarladığınız `m_pMainWnd` içinde `InitInstance` bunu sizin adınıza AppWizard vermez, uygulama. Tek belge arabirimi (SDI) bu biridir `CFrameWnd` yalnızca belge çerçeve penceresi yanı sıra ana uygulama çerçeve penceresi sunar. Birden çok belge arabirimi (MDI) için bir MDI çerçevesi budur (sınıfı `CMDIFrameWnd`) tüm alt içeren ana uygulama çerçeve penceresi hizmet veren `CFrameWnd`s. Her alt pencere sınıfıdır `CMDIChildWnd` (türetilmiş `CFrameWnd`) ve potansiyel olarak birçok belge çerçeve pencereleri biri olarak görev yapar.  
  
## <a name="doctemplates"></a>DocTemplates  
 `CDocTemplate` Oluşturan ve belgelerin yöneticisidir. Oluşturduğu belgeleri sahibidir. Uygulamanızın kaynak tabanlı bir yaklaşım aşağıda açıklanan kullanıyorsa, bu öğesinden türetilen gerekmez `CDocTemplate`.  
  
 SDI uygulamanın sınıfı `CSingleDocTemplate` açık bir belge izler. MDI uygulamanın sınıfı `CMultiDocTemplate` listesini tutar (bir `CPtrList`) Bu şablondan oluşturulan tüm belgelerin şu anda açık. `CDocTemplate::AddDocument`ve `CDocTemplate::RemoveDocument` sanal üye eklemek veya bir belge şablonu kaldırmak için işlevleri sağlar. `CDocTemplate`bir arkadaşınız **CDocument** böylece biz korumalı ayarlayabilirsiniz **CDocument::m_pDocTemplate** geri belge oluşturulan belge şablonu için işaret edecek şekilde geri işaretçi.  
  
 `CWinApp`varsayılan işleme `OnFileOpen` tüm belge şablonları sırayla sorgulayacak uygulama. Uygulama zaten açık belgeleri mi arıyorsunuz ve hangi yeni belgelerde açmak için biçimi karar içerir.  
  
 `CDocTemplate`belgeler ve çerçeveler için kullanıcı Arabirimi bağlama yönetir.  
  
 `CDocTemplate`adlandırılmamış belgeleri sayısını tutar.  
  
## <a name="cdocument"></a>CDocument  
 A **CDocument** tarafından sahip olunan bir `CDocTemplate`.  
  
 Dosyalarınız görünümleri açık bir listesini (türetilmiş `CView`) belgeyi görüntüleme (bir `CPtrList`).  
  
 Belgeler oluşturma/görünümleri yok değil, ancak oluşturulduktan sonra bunların birbirlerine bağlı. Bir belge kapatıldığı (diğer bir deyişle, ile Dosya/Kapat), tüm ekli görünümleri kapatılacak. Son görünümü belgesinde kapalı olduğunda (diğer bir deyişle, pencere/Kapat) belge kapatılacak.  
  
 `CDocument::AddView`, `RemoveView` Arabirimi görünüm listesini korumak için kullanılır. **CDocument** , bir arkadaşınız `CView` biz ayarlayabilirsiniz **CView::m_pDocument** geri işaretçi.  
  
## <a name="cframewnd"></a>CFrameWnd  
 A `CFrameWnd` (çerçeve olarak da bilinir) ancak şimdi MFC 1.0, olduğu gibi aynı rol oynar `CFrameWnd` sınıfı, çoğu durumda yeni bir sınıf türetme olmadan kullanılmak üzere tasarlanmıştır. Türetilen sınıflar `CMDIFrameWnd` ve `CMDIChildWnd` standart komutların çoğu zaten uygulanan şekilde de geliştirilmiştir.  
  
 `CFrameWnd` Çerçeve istemci alanında windows oluşturulmasından sorumludur. Normalde çerçeve istemci alanını doldurma bir ana penceresi yok.  
  
 Bir MDI çerçeve penceresi için istemci alanını tüm MDI alt çerçeve Pencereleri üst sırayla olan MDICLIENT denetimi ile doldurulur. SDI çerçeve penceresi veya bir MDI alt çerçeve penceresi için istemci alanını genellikle doldurulup bir `CView`-pencere nesnesi türetilmiş. Durumunda `CSplitterWnd`, görünümün istemci alanını doldurulup `CSplitterWnd` pencere nesnesi ve `CView`-türetilen pencere nesneleri (bölme bölmesinde her bir tane) alt öğe pencerelerini oluşturulur `CSplitterWnd`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)

