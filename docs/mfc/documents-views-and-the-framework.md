---
title: Belgeler, görünümler ve Microsoft Foundation Class (MFC) kitaplık çerçevesi
description: Microsoft Foundation Class (MFC) kitaplığındaki belge ve görünümlerin açıklaması.
ms.date: 09/25/2020
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
ms.openlocfilehash: 41e145224e512b95d8674109f6ed3dcee39fffb1
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414106"
---
# <a name="documents-views-and-the-framework"></a>Belgeler, görünümler ve çerçeve

MFC çerçevesinin kalbi, belge ve görünüm kavramlardır. Belge, kullanıcının bir düzenleyen oturumunda etkileşimde bulunduğu bir veri nesnesidir. **Dosya** menüsünde **Yeni** veya **Aç** komutu tarafından oluşturulur ve genellikle bir dosyaya kaydedilir. (Sınıftan türetilmiş standart MFC belgeleri `CDocument` , etkin belgelerden ve ole bileşik belgelerinden farklıdır.) Görünüm, kullanıcının bir belge ile etkileşime girdiği bir pencere nesnesidir.

Çalışan bir uygulamadaki önemli nesneler şunlardır:

- İş parçacığı nesneleri

   Uygulamanız yürütmenin ayrı iş parçacıklarını oluşturursa — Örneğin, arka planda hesaplamalar yapmak için, öğesinden türetilmiş sınıfları kullanacaksınız [`CWinThread`](reference/cwinthread-class.md) . [`CWinApp`](reference/cwinapp-class.md) , ' den türetilir `CWinThread` ve uygulamanızdaki yürütmenin birincil iş parçacığını (veya ana işlem) temsil eder. MFC 'yi ikincil iş parçacıklarında de kullanabilirsiniz.

- Uygulama nesnesi

   Uygulama sınıfınız (öğesinden türetilir [`CWinApp`](reference/cwinapp-class.md) ) Yukarıdaki tüm nesneleri denetler ve başlatma ve temizleme gibi uygulama davranışlarını belirtir. Uygulamanın yalnızca bir uygulama nesnesi, uygulamanın desteklediği her belge türü için belge şablonları oluşturur ve yönetir.

- Belge şablonu veya şablonları

   Belge şablonu, belge, görünüm ve çerçeve pencerelerinin oluşturulmasını düzenler. Sınıfından türetilen belirli bir belge-şablon sınıfı [`CDocTemplate`](reference/cdoctemplate-class.md) , bir türdeki tüm açık belgeleri oluşturur ve yönetir. Birden fazla belge türünü destekleyen uygulamaların birden çok belge şablonu vardır. SDI uygulamaları için [CSingleDocTemplate](reference/csingledoctemplate-class.md) sınıfını kullanın veya [`CMultiDocTemplate`](reference/cmultidoctemplate-class.md) MDI uygulamaları için sınıfı kullanın.

- Çerçeve pencereleri

   Görünümler "belge çerçeve pencereleri" içinde görüntülenir. Bir SDI uygulamasında belge çerçevesi penceresi ayrıca uygulamanın "ana çerçeve penceresi" olur. Bir MDI uygulamasında belge pencereleri, bir ana çerçeve penceresi içinde görüntülenen alt pencere. Türetilmiş ana çerçeve pencere sınıfınız, görünümlerinizi içeren çerçeve pencerelerinin stillerini ve diğer özelliklerini belirtir. Çerçeve pencerelerini özelleştirmeniz gerekiyorsa, [`CFrameWnd`](reference/cframewnd-class.md) SDI uygulamaları için belge çerçevesi penceresini özelleştirmek üzere öğesinden türetirsiniz. [`CMDIFrameWnd`](reference/cmdiframewnd-class.md)MDI uygulamaları için ana çerçeve penceresini özelleştirmek üzere öğesinden türet. Ayrıca [`CMDIChildWnd`](reference/cmdichildwnd-class.md) , uygulamanızın desteklediği her türlü farklı MDI belge çerçevesi pencerelerini özelleştirmek için öğesinden bir sınıf türetirsiniz.

- Belge veya belgeler.

   Belge sınıfınız (türetilmiş), [`CDocument`](reference/cdocument-class.md) uygulamanızın verilerini belirtir.

   Uygulamanızda OLE işlevselliği istiyorsanız, [`COleDocument`](reference/coledocument-class.md) ihtiyacınız olan işlevselliğin türüne bağlı olarak belge sınıfınızı veya türetilmiş sınıflarından birini türetebilirsiniz.

- Görünüm veya görünümler.

   Görünüm sınıfınız (türetilmiş), [`CView`](reference/cview-class.md) kullanıcının "verilerdeki pencere" dir. Görünüm sınıfı, kullanıcının belgenizin verilerini nasıl göreceğini ve bununla nasıl etkileşime gireceğini denetler. Bazı durumlarda, bir belgede verilerin birden çok görünümünün olmasını isteyebilirsiniz.

   Kaydırma gerekiyorsa, öğesinden türetebilirsiniz [`CScrollView`](reference/cscrollview-class.md) . Görünümünüzde bir iletişim kutusu şablonu kaynağında yer alan bir kullanıcı arabirimi varsa, ' dan türetebilirsiniz [`CFormView`](reference/cformview-class.md) . Basit metin verileri için ' i kullanın veya buradan türetebilirsiniz [`CEditView`](reference/ceditview-class.md) . Veri girişi programı gibi form tabanlı veri erişim uygulaması için [`CRecordView`](reference/crecordview-class.md) (ODBC için) öğesinden türetebilirsiniz. Ayrıca sınıflar [`CTreeView`](reference/ctreeview-class.md) , ve ' dir [`CListView`](reference/clistview-class.md) [`CRichEditView`](reference/cricheditview-class.md) .

Çalışan bir uygulamada, bu nesneler, komutlar ve diğer iletilerle birlikte birbirlerine göre, kullanıcı eylemlerine uygun şekilde yanıt verir. Tek bir uygulama nesnesi bir veya daha fazla belge şablonunu yönetir. Her belge şablonu, bir veya daha fazla belge oluşturur ve yönetir (uygulamanın SDI veya MDI olmasına bağlı olarak). Kullanıcı bir çerçeve penceresi içindeki bir görünüm aracılığıyla bir belgeyi görüntüler ve yönetir. Aşağıdaki şekilde bir SDI uygulaması için bu nesneler arasındaki ilişkiler gösterilmektedir.

![Çalışan bir SDI uygulamasındaki nesneler](../mfc/media/vc386v1.gif "Çalışan bir SDI uygulamasındaki nesneler")\
Çalışan bir SDI uygulamasındaki nesneler

Bu makale ailesinin geri kalanında Framework araçları, MFC Uygulama Sihirbazı ve kaynak düzenleyicilerinin nasıl oluşturulduğu, nasıl birlikte çalıştıkları ve programınızdaki nasıl kullanılacağı açıklanmaktadır. Belgeler, görünümler ve çerçeve pencereleri, [Pencere nesneleri](window-objects.md) ve [belge/görünüm mimarisi](document-view-architecture.md)içinde daha ayrıntılı olarak ele alınmıştır.

## <a name="see-also"></a>Ayrıca bkz.

[Windows uygulamaları yazmak için sınıfları kullanma](using-the-classes-to-write-applications-for-windows.md)
