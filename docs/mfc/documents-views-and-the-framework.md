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
ms.openlocfilehash: 17956c0b175e978c6e4e2fefcdad5f744929d457
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621831"
---
# <a name="documents-views-and-the-framework"></a>Belgeler, Görünümler ve Çerçeve

MFC çerçevesinin kalbi, belge ve görünüm kavramlardır. Belge, kullanıcının bir düzenleyen oturumunda etkileşimde bulunduğu bir veri nesnesidir. **Dosya** menüsünde **Yeni** veya **Aç** komutu tarafından oluşturulur ve genellikle bir dosyaya kaydedilir. (Sınıftan türetilmiş standart MFC belgeleri `CDocument` , etkin belgelerden ve ole bileşik belgelerinden farklıdır.) Görünüm, kullanıcının bir belge ile etkileşime girdiği bir pencere nesnesidir.

Çalışan bir uygulamadaki önemli nesneler şunlardır:

- Belge veya belgeler.

   Belge sınıfınız ( [CDocument](reference/cdocument-class.md)öğesinden türetilir) uygulamanızın verilerini belirtir.

   Uygulamanızda OLE işlevselliği istiyorsanız, ihtiyacınız olan işlevselliğin türüne bağlı olarak [copadocument](reference/coledocument-class.md) veya türetilmiş sınıflarından biri olan belge sınıfınızı türetebilirsiniz.

- Görünüm veya görünümler.

   Görünüm sınıfınız ( [CView](reference/cview-class.md)'dan türetilmiş) kullanıcının "verilerdeki pencere" görünümüdür. Görünüm sınıfı, kullanıcının belgenizin verilerini nasıl göreceğini ve bununla nasıl etkileşime gireceğini denetler. Bazı durumlarda, bir belgede verilerin birden çok görünümünün olmasını isteyebilirsiniz.

   Kaydırma gerekiyorsa [CScrollView](reference/cscrollview-class.md)öğesinden türetirsiniz. Görünümünüzde bir iletişim kutusu şablonu kaynağında yer alan bir kullanıcı arabirimi varsa [CFormView](reference/cformview-class.md)öğesinden türetirsiniz. Basit metin verileri için [CEditView](reference/ceditview-class.md)'dan kullanın veya türetebilirsiniz. Veri girişi programı gibi form tabanlı veri erişim uygulaması için [CRecordView](reference/crecordview-class.md) (ODBC için) öğesinden türetirsiniz. Ayrıca, [CTreeView](reference/ctreeview-class.md), [Clienstview](reference/clistview-class.md)ve [CRichEditView](reference/cricheditview-class.md)sınıfları bulunur.

- Çerçeve pencereleri

   Görünümler "belge çerçeve pencereleri" içinde görüntülenir. Bir SDI uygulamasında belge çerçevesi penceresi ayrıca uygulamanın "ana çerçeve penceresi" olur. Bir MDI uygulamasında belge pencereleri, bir ana çerçeve penceresi içinde görüntülenen alt pencere. Türetilmiş ana çerçeve pencere sınıfınız, görünümlerinizi içeren çerçeve pencerelerinin stillerini ve diğer özelliklerini belirtir. Çerçeve pencerelerini özelleştirmeniz gerekiyorsa, [Sframewnd](reference/cframewnd-class.md) öğesinden türet, SDI uygulamaları için belge çerçevesi penceresini özelleştirin. MDI uygulamalarının ana çerçeve penceresini özelleştirmek için [Cmdiframewnd](reference/cmdiframewnd-class.md) 'den türetirsiniz. Ayrıca, uygulamanızın desteklediği her türlü farklı MDI belge çerçevesi pencerelerini özelleştirmek için [Cmdictepdwnd](reference/cmdichildwnd-class.md) öğesinden bir sınıf türetirsiniz.

- Belge şablonu veya şablonları

   Belge şablonu, belge, görünüm ve çerçeve pencerelerinin oluşturulmasını düzenler. [CDocTemplate](reference/cdoctemplate-class.md)sınıfından türetilen belirli bir belge-şablon sınıfı, bir türdeki tüm açık belgeleri oluşturur ve yönetir. Birden fazla belge türünü destekleyen uygulamaların birden çok belge şablonu vardır. SDI uygulamaları için [CSingleDocTemplate](reference/csingledoctemplate-class.md) sınıfını kullanın veya MDI uygulamaları Için [CMultiDocTemplate](reference/cmultidoctemplate-class.md) sınıfını kullanın.

- Uygulama nesnesi

   Uygulama sınıfınız ( [CWinApp](reference/cwinapp-class.md)öğesinden türetilir) Yukarıdaki tüm nesneleri denetler ve başlatma ve temizleme gibi uygulama davranışlarını belirtir. Uygulamanın yalnızca bir uygulama nesnesi, uygulamanın desteklediği her belge türü için belge şablonları oluşturur ve yönetir.

- İş parçacığı nesneleri

   Uygulamanız ayrı yürütme iş parçacıkları oluşturursa — Örneğin, arka planda hesaplamalar gerçekleştirmek için —, [CWinThread](reference/cwinthread-class.md)öğesinden türetilmiş sınıfları kullanacaksınız. [CWinApp](reference/cwinapp-class.md) ' dan türetilir `CWinThread` ve uygulamanızda yürütmenin birincil iş parçacığını (veya ana işlem) temsil eder. MFC 'yi ikincil iş parçacıklarında de kullanabilirsiniz.

Çalışan bir uygulamada, bu nesneler, komutlar ve diğer iletilerle birlikte birbirlerine göre, kullanıcı eylemlerine uygun şekilde yanıt verir. Tek bir uygulama nesnesi bir veya daha fazla belge şablonunu yönetir. Her belge şablonu, bir veya daha fazla belge oluşturur ve yönetir (uygulamanın SDI veya MDI olmasına bağlı olarak). Kullanıcı bir çerçeve penceresi içindeki bir görünüm aracılığıyla bir belgeyi görüntüler ve yönetir. Aşağıdaki şekilde bir SDI uygulaması için bu nesneler arasındaki ilişkiler gösterilmektedir.

![Çalışan bir SDI uygulamasındaki nesneler](../mfc/media/vc386v1.gif "Çalışan bir SDI uygulamasındaki nesneler") <br/>
Çalışan bir SDI uygulamasındaki nesneler

Bu makale ailesinin geri kalanında Framework araçları, MFC Uygulama Sihirbazı ve kaynak düzenleyicilerinin nasıl oluşturulduğu, nasıl birlikte çalıştıkları ve programınızdaki nasıl kullanılacağı açıklanmaktadır. Belgeler, görünümler ve çerçeve pencereleri, [Pencere nesneleri](window-objects.md) ve [belge/görünüm mimarisi](document-view-architecture.md)içinde daha ayrıntılı olarak ele alınmıştır.

## <a name="see-also"></a>Ayrıca bkz.

[Windows Uygulamaları Yazmak için Sınıfları Kullanma](using-the-classes-to-write-applications-for-windows.md)
