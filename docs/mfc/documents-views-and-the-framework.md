---
title: Belgeler, Görünümler ve Çerçeve
ms.date: 11/19/2018
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
ms.openlocfilehash: 799035976ea55988a635f7dc9b667e87c48d8f7e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273510"
---
# <a name="documents-views-and-the-framework"></a>Belgeler, Görünümler ve Çerçeve

MFC çerçevesi yaklaşımının temelindeki, belge ve görünüm kavramlardır. Bir belge bir düzenleme oturumu ile kullanıcı etkileşim verilerini bir nesnedir. Tarafından oluşturulan **yeni** veya **açık** komutunu **dosya** menü ve genellikle bir dosyaya kaydedilir. (Standart MFC belge sınıfından türetilen `CDocument`, etkin belgeler ve OLE bileşik belgeler farklıdır.) Bir pencere nesnesi üzerinden kullanıcı bir belge ile etkileşime giren bir görünümüdür.

Çalışan bir uygulamada anahtar nesneleri şunlardır:

- Belgeleri ve belge.

   Belge sınıfınıza (türetilen [CDocument](../mfc/reference/cdocument-class.md)), uygulamanızın verilerini belirtir.

   Uygulamanızda OLE işlevselliği istiyorsanız, belge sınıfından türetilir [COleDocument](../mfc/reference/coledocument-class.md) veya gereksinim duyduğunuz işlevsellik türüne bağlı olarak türetilmiş sınıflarının biri.

- Görünümü veya görünümlerini.

   Görünüm sınıfınıza (türetilen [CView](../mfc/reference/cview-class.md)) kullanıcının "Pencere veri çubuğunda." Görünüm sınıfını nasıl kullanıcı, belgenin verilerini görür ve etkileşimine göre değişecek denetler. Bazı durumlarda, verilerin birden çok görünüm için bir belge isteyebilirsiniz.

   Kaydırma ihtiyacınız varsa, türetilen [CScrollView](../mfc/reference/cscrollview-class.md). Görünümünüze bir iletişim şablonunu kaynakta yayılır bir kullanıcı arabirimi varsa, türetilen [CFormView](../mfc/reference/cformview-class.md). Basit metin verileri kullanma veya öğesinden türetilen [CEditView](../mfc/reference/ceditview-class.md). Bir veri girişi programı gibi bir form tabanlı veri erişimi uygulama için türetilen [CRecordView](../mfc/reference/crecordview-class.md) (ODBC için). Sınıfları da kullanılabilir [CTreeView](../mfc/reference/ctreeview-class.md), [CListView](../mfc/reference/clistview-class.md), ve [CRichEditView](../mfc/reference/cricheditview-class.md).

- Çerçeve pencereleri

   Görünümler "içinde belge çerçeve pencereleri." görüntülenir Bir SDI uygulamasında, belge çerçeve penceresi de uygulamanın "ana çerçeve penceresinin" dir. Bir MDI uygulamasında, belge alt pencereleri bir ana çerçeve penceresi içinde görüntülenen dizisidir. Türetilmiş ana çerçeve penceresi sınıfınıza stilleri ve kendi görünümlerinizi içeren çerçeve pencereleri diğer özelliklerini belirtir. Çerçeve pencereleri özelleştirme gerekiyorsa türetilen [CFrameWnd](../mfc/reference/cframewnd-class.md) SDI uygulamaları için belge çerçeve penceresi özelleştirmek için. Öğesinden türetilen [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) MDI uygulamaları için ana çerçeve penceresine özelleştirmek için. Ayrıca bir sınıftan türetilen [Cmdıchildwnd](../mfc/reference/cmdichildwnd-class.md) uygulamanızın desteklediği MDI belge çerçeve pencereleri ayrı her tür özelleştirmek için.

- Şablonları ve belge şablonu

   Bir belge şablonu, belgeler, görünümler ve çerçeve pencereleri oluşturma düzenler. Belirli bir belge şablonu, türetilen bir sınıftan [CDocTemplate](../mfc/reference/cdoctemplate-class.md)oluşturur ve bir türdeki tüm açık belgeleri yönetir. Birden fazla belge türü destekleyen uygulamalar birden çok belge şablonu vardır. Bir sınıf kullanma [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) SDI uygulamaları ya da kullanım sınıfı için [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md) MDI uygulamaları için.

- Uygulama nesnesi

   Uygulama sınıfınıza (türetilen [CWinApp](../mfc/reference/cwinapp-class.md)) tüm nesneler yukarıdaki denetler ve başlatma ve temizleme gibi uygulama davranışını belirtir. Uygulamanın bir ve yalnızca uygulama nesnesi oluşturur ve uygulamanızın desteklediği herhangi bir belge türleri için şablonların yönetir.

- İş parçacığı nesneleri

   Uygulamanızı ayrı iş parçacığı yürütme oluşturursa — Örneğin, arka planda hesaplamalar gerçekleştirmek için — öğelerinden türetilen sınıfları kullanacağınız [CWinThread](../mfc/reference/cwinthread-class.md). [CWinApp](../mfc/reference/cwinapp-class.md) kendisini türetilir `CWinThread` ve uygulamanızda yürütme (veya ana işlem) birincil iş parçacığını temsil eder. MFC İkincil iş parçacığı da kullanabilirsiniz.

Çalışan bir uygulamada bu nesneler işbirliği ile kullanıcı eylemlerini, birlikte diğer iletiler ve komutlar ile ilişkili yanıt. Tek uygulama nesnesi bir veya daha fazla belge şablonları yönetir. Her bir belge şablonu oluşturur ve yönetir (uygulama SDI veya MDI olup olmamasına bağlı olarak) bir veya daha fazla belge. Kullanıcı görünümleri ve belge çerçeve pencere içinde yer alan bir görünüm aracılığıyla yönetir. Aşağıdaki şekilde bir SDI uygulaması için bu nesneleri arasındaki ilişkiler gösterilmektedir.

![Çalışan bir SDI uygulamasında nesneler](../mfc/media/vc386v1.gif "çalışan SDI uygulamasında nesneler") <br/>
Çalışan SDI uygulamasında nesneler

Bu makaleler ailesi geri kalanı, programlamada kullanımını framework araçları, MFC Uygulama Sihirbazı ve kaynak düzenleyicileri, bu nesneler oluşturma ve nasıl çalıştıkları açıklanır. Belgeler, görünümler ve çerçeve pencereleri daha ayrıntılı olarak açıklanmıştır [pencere nesneleri](../mfc/window-objects.md) ve [belge/görünüm mimarisi](../mfc/document-view-architecture.md).

## <a name="see-also"></a>Ayrıca bkz.

[Windows Uygulamaları Yazmak için Sınıfları Kullanma](../mfc/using-the-classes-to-write-applications-for-windows.md)
