---
title: "Veri nesneleri ve veri kaynakları: düzenleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- data objects [MFC], manipulating
- data sources [MFC], data operations
- data sources [MFC], inserting data
- Clipboard [MFC], determining available formats
- OLE [MFC], data objects
- Clipboard [MFC], passing format information
- data sources [MFC], determining available formats
- delayed rendering [MFC]
- OLE [MFC], data sources
ms.assetid: f7f27e77-bb5d-4131-b819-d71bf929ebaf
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4561e055bd258ba2b276075ff337d62cf194813b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="data-objects-and-data-sources-manipulation"></a>Veri Nesneleri ve Veri Kaynakları: Düzenleme
Bir veri nesnesi veya veri kaynağı oluşturulduktan sonra birkaç ortak işlem verileri ekleme ve kaldırma verileri, verilerin bulunduğu biçimleri numaralandırma gibi ve daha fazlasını gerçekleştirebilirsiniz. Bu makale, en yaygın işlemleri tamamlamak gerekli teknikleri açıklar. Konular şunlardır:  
  
-   [Bir veri kaynağına veri ekleme](#_core_inserting_data_into_a_data_source)  
  
-   [Bir veri nesnesi içinde kullanılabilir biçimleri belirleme](#_core_determining_the_formats_available_in_a_data_object)  
  
-   [Bir veri nesnesinden veriyi geri alma](#_core_retrieving_data_from_a_data_object)  
  
##  <a name="_core_inserting_data_into_a_data_source"></a>Bir veri kaynağına veri ekleme  
 Veriler bir veri kaynağına nasıl eklenir olup verileri hemen sağlanır üzerinde bağlıdır veya isteğe bağlı ve hangi Orta sağlanır. Olanakları aşağıdaki gibidir.  
  
### <a name="supplying-data-immediately-immediate-rendering"></a>Sağlama verileri hemen (anlık görüntü oluşturma)  
  
-   Çağrı `COleDataSource::CacheGlobalData` art arda içinde sağladığını veri her Pano biçimi. Kullanılmak üzere Pano biçimi geçirmek verileri içeren bellek için bir tanıtıcı ve isteğe bağlı olarak bir **FORMATETC** açıklayan veri yapısı.  
  
     veya  
  
-   İle doğrudan çalışmak isterseniz **STGMEDIUM** yapıları çağırmanız `COleDataSource::CacheData` yerine `COleDataSource::CacheGlobalData` yukarıdaki seçeneği.  
  
### <a name="supplying-data-on-demand-delayed-rendering"></a>(Gecikmeli işleme) istek üzerine veri sağlama  
 Bu gelişmiş bir konudur.  
  
-   Çağrı `COleDataSource::DelayRenderData` art arda içinde sağladığını veri her Pano biçimi. Kullanılacak Pano biçimi geçirmek ve isteğe bağlı olarak bir **FORMATETC** açıklayan veri yapısı. Verileri istendiğinde framework çağıracak `COleDataSource::OnRenderData`, hangi geçersiz kılmanız gerekir.  
  
     veya  
  
-   Kullanırsanız, bir `CFile` veri sağlamak için nesne çağrısı `COleDataSource::DelayRenderFileData` yerine `COleDataSource::DelayRenderData` önceki seçeneği. Verileri istendiğinde framework çağıracak `COleDataSource::OnRenderFileData`, hangi geçersiz kılmanız gerekir.  
  
##  <a name="_core_determining_the_formats_available_in_a_data_object"></a>Bir veri nesnesi içinde kullanılabilir biçimleri belirleme  
 Bir uygulama veri yapıştırın kullanıcıya vermeden önce bunu işleyebileceği panoya biçimleri olup olmadığını bilmek ister. Bunu yapmak için uygulamanızın şunları yapmalıdır:  
  
1.  Oluşturma bir `COleDataObject` nesne ve **FORMATETC** yapısı.  
  
2.  Veri nesnesinin çağrı `AttachClipboard` Panodaki veriler veri nesnesi ilişkilendirmek için üye işlevi.  
  
3.  Aşağıdakilerden birini yapın:  
  
    -   Veri nesnesinin çağrı `IsDataAvailable` yalnızca bir veya iki biçimleri, üye işlevi gerekir. Bu durumlarda, Panodaki veriler uygulamanızı daha önemli ölçüde daha fazla destekler zaman kazanabilirsiniz.  
  
         veya  
  
    -   Veri nesnesinin çağrı `BeginEnumFormats` Pano'ya biçimlerinden numaralandırma başlatmak için üye işlevi. ' I çağırın `GetNextFormat` Pano dönene kadar uygulamanızın bir biçimini destekler veya daha fazla hiçbir biçimleri vardır.  
  
 Kullanıyorsanız `ON_UPDATE_COMMAND_UI`, yapıştırma ve muhtemelen Düzenle menüsündeki Özel Yapıştır öğeleri artık etkinleştirebilirsiniz. Bunu yapmak için ya da çağrısı `CMenu::EnableMenuItem` veya `CCmdUI::Enable`. Hangi kapsayıcı hakkında daha fazla bilgi için uygulamaları menü öğeleriyle yapın ve gerekir, gördüğünüzde [menüler ve kaynaklar: kapsayıcı ekleme](../mfc/menus-and-resources-container-additions.md).  
  
##  <a name="_core_retrieving_data_from_a_data_object"></a>Bir veri nesnesinden veriyi geri alma  
 Veri biçimi karar verdikten sonra kalan tek şey veri nesnesinden verileri almak üzere. Bunu yapmak için kullanıcı verileri nereye karar ve uygulama uygun işlevi çağırır. Veriler aşağıdaki ortamlarının birinde kullanılabilir:  
  
|Orta|Çağrılacak işlevi|  
|------------|----------------------|  
|Genel bellek (`HGLOBAL`)|`COleDataObject::GetGlobalData`|  
|Dosya (`CFile`)|`COleDataObject::GetFileData`|  
|**STGMEDIUM** yapısı (`IStorage`)|`COleDataObject::GetData`|  
  
 Genellikle, Orta, Pano biçimi birlikte belirtilir. Örneğin, bir **CF_EMBEDDEDSTRUCT** nesne içinde her zaman bir `IStorage` gerektirir Orta bir **STGMEDIUM** yapısı. Bu nedenle, kullanacağınız `GetData` kabul edebilir bu işlevler yalnızca biri olduğundan bir **STGMEDIUM** yapısı.  
  
 Pano biçimi olduğu durumlarda bir `IStream` veya `HGLOBAL` framework Orta, sağlayabilen bir `CFile` verilere başvuruda işaretçi. Uygulama daha sonra dosya bir dosyadan veri alabilir gibi aynı şekilde çok veri almak için okuma kullanabilirsiniz. Esas olarak, bu istemci tarafı için arabirimidir `OnRenderData` ve `OnRenderFileData` veri kaynağındaki yordamları.  
  
 Kullanıcı verileri belgeye Ekle aynı biçimde diğer verilerin için olduğu gibi artık açabilir.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Sürükleme ve bırakma](../mfc/drag-and-drop-ole.md)  
  
-   [Pano](../mfc/clipboard.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri nesneleri ve veri kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md)   
 [COleDataObject sınıfı](../mfc/reference/coledataobject-class.md)   
 [COleDataSource sınıfı](../mfc/reference/coledatasource-class.md)
