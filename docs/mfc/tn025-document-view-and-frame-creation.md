---
title: 'TN025: Belge, Görünüm ve çerçeve oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.creation
dev_langs:
- C++
helpviewer_keywords:
- documents [MFC], view and frame creation
- TN025
ms.assetid: 09254d72-6e1d-43db-80e9-693887dbeda2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6a5fd603fdb45ac0f754858384df1455f559222e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383057"
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
  
 SDI uygulamanın sınıfı `CSingleDocTemplate` açık bir belge izler. MDI uygulamanın sınıfı `CMultiDocTemplate` listesini tutar (bir `CPtrList`) Bu şablondan oluşturulan tüm belgelerin şu anda açık. `CDocTemplate::AddDocument` ve `CDocTemplate::RemoveDocument` sanal üye eklemek veya bir belge şablonu kaldırmak için işlevleri sağlar. `CDocTemplate` bir arkadaşınız **CDocument** böylece biz korumalı ayarlayabilirsiniz **CDocument::m_pDocTemplate** geri belge oluşturulan belge şablonu için işaret edecek şekilde geri işaretçi.  
  
 `CWinApp` varsayılan işleme `OnFileOpen` tüm belge şablonları sırayla sorgulayacak uygulama. Uygulama zaten açık belgeleri mi arıyorsunuz ve hangi yeni belgelerde açmak için biçimi karar içerir.  
  
 `CDocTemplate` belgeler ve çerçeveler için kullanıcı Arabirimi bağlama yönetir.  
  
 `CDocTemplate` adlandırılmamış belgeleri sayısını tutar.  
  
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
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

