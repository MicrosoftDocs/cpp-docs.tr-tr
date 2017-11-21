---
title: "Belgeler, görünümler ve çerçeve | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- document templates [MFC], template objects
- applications [MFC]
- MFC, application framework
- application objects [MFC], relation to other MFC objects
- documents [MFC]
- MFC, documents
- document objects [MFC], in relation to other MFC objects
- view objects [MFC], relation to other MFC objects
- MFC, views
- document/view architecture [MFC], about document/view architecture
- objects [MFC], MFC applications
- MFC object relationships
- thread objects [MFC]
ms.assetid: 409ddd9b-66ad-4625-84f7-bf55a41d697b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b6034dc13c554769ab62b37bd1ca143527b5f82e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="documents-views-and-the-framework"></a>Belgeler, Görünümler ve Çerçeve
MFC çerçevesi Kalp belge ve görünüm kavramlarını ' dir. Hangi kullanıcı düzenleme oturumunda etkileşimde bulunan bir veri nesnesi bir belgedir. Tarafından oluşturulan `New` veya **açık** komutunu **dosya** menü ve genellikle bir dosyaya kaydedilir. (Standart MFC belgeleri, sınıfından türetilen **CDocument**, etkin belgeler ve OLE bileşik belgeler farklıdır.) Bir görünüm üzerinden kullanıcı bir belge ile etkileşime giren bir pencere nesnesidir.  
  
 Çalışan bir uygulama anahtar nesneleri şunlardır:  
  
-   Belge veya belgeler.  
  
     Belge sınıfı (türetilmiş [CDocument](../mfc/reference/cdocument-class.md)), uygulamanızın veri belirtir.  
  
     Uygulamanızda OLE işlevselliği istiyorsanız, belge sınıfından türetilen [COleDocument](../mfc/reference/coledocument-class.md) veya gereksinim duyduğunuz işlevselliği türüne bağlı olarak türetilmiş sınıflarından biri.  
  
-   Görünüm veya görünüm.  
  
     View sınıfı (türetilmiş [CView](../mfc/reference/cview-class.md)) kullanıcının "penceresi verilere." View sınıfı nasıl kullanıcı belgenizin veri görür ve onunla etkileşimde bulunan denetler. Bazı durumlarda, verilerin birden çok görünüm için bir belge isteyebilirsiniz.  
  
     Kaydırma gerekiyorsa, türetilen [CScrollView](../mfc/reference/cscrollview-class.md). Görünümünüze bir iletişim şablonunu kaynak düzenlendiği bir kullanıcı arabirimi varsa, türetilen [Cformview'yu](../mfc/reference/cformview-class.md). Basit metin verileri için kullanın veya öğesinden türetilen [CEditView](../mfc/reference/ceditview-class.md). Bir veri girişi programı gibi bir form tabanlı veri erişimi uygulama için türetilen [CRecordView](../mfc/reference/crecordview-class.md) (ODBC için). Sınıfları ayrıca kullanılabilir [CTreeView](../mfc/reference/ctreeview-class.md), [CListView](../mfc/reference/clistview-class.md), ve [CRichEditView](../mfc/reference/cricheditview-class.md).  
  
-   Çerçeve pencereleri  
  
     Görünümler "içinde belge çerçeve pencereleri." görüntülenir SDI uygulamada belge çerçeve penceresi de "ana çerçeve" uygulaması için penceredir. MDI uygulamada belge pencereleri alt windows ana çerçeve penceresi içinde görüntülenir ' dir. Türetilen ana çerçeve penceresi sınıfınız stilleri ve kendi görünümlerinizi içeren çerçeve pencereleri diğer özelliklerini belirtir. Çerçeve pencereleri özelleştirmeniz gerekiyorsa, türetilen [CFrameWnd](../mfc/reference/cframewnd-class.md) SDI uygulamalar için belge çerçeve penceresi özelleştirmek için. Öğesinden türetilen [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) MDI uygulamaları için ana çerçeve penceresi özelleştirmek için. Ayrıca öğesinden bir sınıf türetin [Cmdıchildwnd](../mfc/reference/cmdichildwnd-class.md) uygulamanızı destekleyen MDI belge çerçeve pencereleri ayrı her tür özelleştirmek için.  
  
-   Belge şablonu veya şablonları  
  
     Belge şablonu oluşturma belgeler, görünümler ve çerçeve pencereleri düzenler. Sınıfından türetilen bir belirli belge şablonu sınıfı [CDocTemplate](../mfc/reference/cdoctemplate-class.md), oluşturur ve bir türdeki tüm açık belgeleri yönetir. Birden fazla belge türü destekleyen uygulamalar birden çok belge şablonu vardır. Bir sınıf kullanma [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) SDI uygulamaları ya da kullanım sınıfı için [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md) MDI uygulamaları için.  
  
-   Uygulama nesnesi  
  
     Uygulama sınıfı (türetilmiş [CWinApp](../mfc/reference/cwinapp-class.md)) tüm nesneleri yukarıdaki denetler ve başlatma ve temizleme gibi uygulama davranışını belirtir. Uygulamanın bir ve yalnızca uygulama nesnesi oluşturur ve uygulamanızın desteklediği herhangi bir belge türleri için belge şablonları yönetir.  
  
-   İş parçacığı nesneleri  
  
     Uygulamanızın ayrı iş parçacıklarının yürütülmesine oluşturursa — Örneğin, arka planda hesaplamalar için — türetilmiş sınıfları kullanacağınız [CWinThread](../mfc/reference/cwinthread-class.md). [CWinApp](../mfc/reference/cwinapp-class.md) kendisini türetilir `CWinThread` ve birincil iş parçacığı yürütme (veya ana işlem), uygulamanızda temsil eder. MFC İkincil iş parçacıklarında de kullanabilirsiniz.  
  
 Çalışan bir uygulama bu nesneler işlevinizde komutlar ve diğer iletileri tarafından birbirine bağlı kullanıcı eylemlerini yanıt verin. Tek bir uygulama nesnesi bir veya daha fazla belge şablonları yönetir. Her belge şablonu oluşturur ve (uygulama SDI veya MDI olup olmamasına bağlı olarak) bir veya daha fazla belge yönetir. Kullanıcı görünümler ve çerçeve penceresi içinde yer alan bir görünümü aracılığıyla bir belge yönetir. Aşağıdaki şekilde bir SDI uygulama için bu nesneleri arasındaki ilişkiler gösterilmektedir.  
  
 ![Çalışan bir SDI uygulama nesneleri](../mfc/media/vc386v1.gif "vc386v1")  
Çalışan bir SDI uygulamada nesneler  
  
 Bu ailesi makaleler rest nasıl framework araçları, MFC Uygulama Sihirbazı'nı ve kaynak Düzenleyicileri Bu nesneleri oluşturmak, bunlar birlikte nasıl çalışır ve bunları sizin programlamada kullanma açıklanmaktadır. Belgeler, görünümler ve çerçeve pencereleri daha ayrıntılı olarak açıklanmıştır [pencere nesneleri](../mfc/window-objects.md) ve [belge/görünüm mimarisinin](../mfc/document-view-architecture.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows uygulamaları yazmak için sınıfları kullanma](../mfc/using-the-classes-to-write-applications-for-windows.md)
