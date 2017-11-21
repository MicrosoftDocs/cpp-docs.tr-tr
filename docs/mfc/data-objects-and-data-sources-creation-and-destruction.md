---
title: "Veri nesneleri ve veri kaynakları: oluşturma ve yok etme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- destroying data objects [MFC]
- object creation [MFC], data source objects
- data sources [MFC], and data objects
- data source objects [MFC], creating
- destruction [MFC], data sources
- data source objects [MFC], destroying
- data objects [MFC], creating
- data objects [MFC], destroying
- data sources [MFC], role
- data sources [MFC], destroying
- destruction [MFC], data objects
- data sources [MFC], creating
ms.assetid: ac216d54-3ca5-4ce7-850d-cd1f6a90d4f1
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6b919fec6f9e835a788b6d9c7b5f5d8715bd22b9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="data-objects-and-data-sources-creation-and-destruction"></a>Veri Nesneleri ve Veri Kaynakları: Oluşturma ve Yok Etme
Makalesinde açıklandığı gibi [veri nesneleri ve veri kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md), veri nesneleri ve veri kaynaklarını her iki tarafında bir veri aktarımı temsil eder. Bu makalede oluşturmak ve bu nesneleri ve veri aktarımları düzgün şekilde gerçekleştirmek için kaynakları yok etmek ne zaman dahil olmak üzere açıklanmaktadır:  
  
-   [Veri nesneleri oluşturma](#_core_creating_data_objects)  
  
-   [Veri nesnelerini yok etme](#_core_destroying_data_objects)  
  
-   [Veri kaynakları oluşturma](#_core_creating_data_sources)  
  
-   [Veri kaynakları yok etme](#_core_destroying_data_sources)  
  
##  <a name="_core_creating_data_objects"></a>Veri nesneleri oluşturma  
 Veri nesneleri hedef uygulama tarafından kullanılan — istemci veya sunucu. Hedef uygulama veri nesnesinde kaynak uygulama ve hedef uygulama arasında bir bağlantı sonudur. Hedef uygulama veri nesnesinde erişmek ve veri kaynağındaki verileri ile etkileşim kurmak için kullanılır.  
  
 Burada bir veri nesnesi gereken iki ortak durumlar vardır. Veri Sürükle ve bırak kullanarak uygulamanızda bırakıldığında ilk durumdur. Düzen menüsünden Yapıştır veya Özel Yapıştır seçildiğinde ikinci durumdur.  
  
 Sürükle ve bırak durumda, bir veri nesnesi oluşturmak gerekmez. Varolan bir veri nesnesine bir işaretçi geçirilecektir, `OnDrop` işlevi. Bu veri nesnesi çerçevesi tarafından sürükle ve bırak işleminin bir parçası olarak oluşturulur ve ayrıca tarafından yok olacaktır. Başka bir yöntem kullanarak yapıştırma yapıldığında bu her zaman durumda değil. Daha fazla bilgi için bkz: [veri nesnelerini yok etme](#_core_destroying_data_objects).  
  
 Uygulama yapıştırma veya yapıştırma özel işlemi yapılıyorsa oluşturmalısınız bir `COleDataObject` nesne ve çağrı kendi `AttachClipboard` üye işlevi. Bu Panodaki veriler ile veri nesnesi ilişkilendirir. Daha sonra bu veri nesnesi Yapıştır işlevinizi kullanabilirsiniz.  
  
##  <a name="_core_destroying_data_objects"></a>Veri nesnelerini yok etme  
 Açıklanan düzeni izlerseniz [veri nesneleri oluşturma](#_core_creating_data_objects), veri aktarımları Önemsiz yönünü olan veri nesnelerini yok etme. İşlev Yapıştır döndürdüğünde Yapıştır işlevinizi oluşturulduğu veri nesnesi MFC tarafından yok olacaktır.  
  
 Yapıştırma işlemleri işleme başka bir yöntem izlerseniz, yapıştırma işlemi tamamlandıktan sonra veri nesnesi yok emin olun. Veri nesnesi yok kadar başarıyla veri panoya kopyalamak herhangi bir uygulama için imkansız olur.  
  
##  <a name="_core_creating_data_sources"></a>Veri kaynakları oluşturma  
 Veri kaynakları, istemci veya sunucu tarafı veri aktarım olabilir veri aktarımı kaynağı tarafından kullanılır. Bir veri kaynağı kaynak uygulaması, kaynak uygulama ve hedef uygulama arasında bir bağlantı sonudur. Hedef uygulama veri nesnesinde veri kaynağındaki verileri ile etkileşim kurmak için kullanılır.  
  
 Veri kaynakları, bir uygulama verileri Pano'ya kopyalamanız gerektiğinde oluşturulur. Tipik bir senaryo şöyle çalışır:  
  
1.  Kullanıcı, bazı veriler seçer.  
  
2.  Kullanıcının seçtiği **kopyalama** (veya **Kes**) gelen **Düzenle** menüsü veya bir Sürükle ve bırak işlemi başlar.  
  
3.  Program tasarımına bağlı olarak, uygulama ya da oluşturur bir `COleDataSource` veya nesneyi sınıfından türetilen `COleDataSource`.  
  
4.  Seçili verileri işlevlerde birini çağırarak veri kaynağına eklenen `COleDataSource::CacheData` veya `COleDataSource::DelayRenderData` gruplar.  
  
5.  Uygulama çağrıları `SetClipboard` üye işlevi (veya `DoDragDrop` sürükle ve bırak işlemi buysa üye işlevi) 3. adımda oluşturduğunuz nesneye ait.  
  
6.  Bu ise bir **Kes** işlemi veya `DoDragDrop` döndürür `DROPEFFECT_MOVE`, belge 1. adımda seçilen verileri silinir.  
  
 Bu senaryo MFC OLE örnekleri tarafından uygulanan [OCLIENT](../visual-cpp-samples.md) ve [HIERSVR](../visual-cpp-samples.md). Her uygulama için kaynak bakabilir `CView`-sınıfı için türetilen dışındaki tüm `GetClipboardData` ve `OnGetClipboardData` işlevleri. Bu iki ya da işlevlerdir `COleClientItem` veya `COleServerItem`-sınıf uygulamaları türetilmiş. Bu örnek programlar nasıl Bu kavramlar uygulamak iyi bir örnek sağlar.  
  
 İstediğiniz oluşturmak bir durum bir `COleDataSource` Nesne Sürükle ve bırak işlemi varsayılan davranışını değiştiriyorsanız oluşur. Daha fazla bilgi için bkz: [sürükle ve bırak: özelleştirme](../mfc/drag-and-drop-customizing.md) makalesi.  
  
##  <a name="_core_destroying_data_sources"></a>Veri kaynakları yok etme  
 Veri kaynakları için şu anda sorumlu uygulama tarafından yok edilmesi gerekir. Burada, teslim veri kaynağı için OLE durumlarda gibi çağırma [COleDataSource::DoDragDrop](../mfc/reference/coledatasource-class.md#dodragdrop), çağırmanız gerekir **pDataSrc -> Internalrelease**. Örneğin:  
  
 [!code-cpp[NVC_MFCListView#1](../atl/reference/codesnippet/cpp/data-objects-and-data-sources-creation-and-destruction_1.cpp)]  
  
 Veri kaynağınız için OLE karmalayan değil, ardından nesnesiyle herhangi tipik C++ gibi yok etme için sorumluluğu size aittir.  
  
 Daha fazla bilgi için bkz: [sürükle ve bırak](../mfc/drag-and-drop-ole.md), [Pano](../mfc/clipboard.md), ve [düzenleme veri nesneleri ve veri kaynakları](../mfc/data-objects-and-data-sources-manipulation.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri nesneleri ve veri kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md)   
 [COleDataObject sınıfı](../mfc/reference/coledataobject-class.md)   
 [COleDataSource sınıfı](../mfc/reference/coledatasource-class.md)
