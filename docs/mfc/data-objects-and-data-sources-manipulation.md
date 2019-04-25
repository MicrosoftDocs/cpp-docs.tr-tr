---
title: 'Veri nesneleri ve veri kaynakları: Düzenleme'
ms.date: 11/04/2016
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
ms.openlocfilehash: 81dfe911866c4d1ba1720ee2c9854076c499f0a3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62241555"
---
# <a name="data-objects-and-data-sources-manipulation"></a>Veri nesneleri ve veri kaynakları: Düzenleme

Bir veri nesnesi veya veri kaynağı oluşturulduktan sonra ekleme ve kaldırma verileri, verilerin bulunduğu biçimleri numaralandırma gibi verileri ve daha fazla yaygın işlemlerin sayısı gerçekleştirebilirsiniz. Bu makalede, en yaygın işlemlerin tamamlanması gereken teknikleri açıklar. Konular şunlardır:

- [Bir veri kaynağına veri ekleme](#_core_inserting_data_into_a_data_source)

- [Bir veri nesnesi içinde kullanılabilir biçimleri belirleme](#_core_determining_the_formats_available_in_a_data_object)

- [Bir veri nesnesinden veriyi geri alma](#_core_retrieving_data_from_a_data_object)

##  <a name="_core_inserting_data_into_a_data_source"></a> Bir veri kaynağına veri ekleme

Veriler bir veri kaynağına nasıl eklenir olup verileri hemen sağlanan üzerinde bağlıdır veya isteğe bağlı ve hangi ortamda sağlanır. Olasılık aşağıdaki gibidir.

### <a name="supplying-data-immediately-immediate-rendering"></a>Hemen veri (anlık görüntü oluşturma) sağlama

- Çağrı `COleDataSource::CacheGlobalData` art arda içinde sağladığınız verileri her Pano biçimi. Kullanılacak, Pano biçimi geçirmek verileri içeren bellek için bir tanıtıcı ve isteğe bağlı olarak bir **FORMATETC** açıklayan veri yapısı.

     -veya-

- İle doğrudan çalışmak istiyorsanız **STGMEDIUM** yapıları çağırmanızı `COleDataSource::CacheData` yerine `COleDataSource::CacheGlobalData` yukarıdaki seçeneği.

### <a name="supplying-data-on-demand-delayed-rendering"></a>Verileri isteğe bağlı (Gecikmeli işleme) sağlama

Bu gelişmiş bir konudur.

- Çağrı `COleDataSource::DelayRenderData` art arda içinde sağladığınız verileri her Pano biçimi. Pano biçimi kullanılacak geçirin ve isteğe bağlı olarak bir **FORMATETC** açıklayan veri yapısı. Veri istendiğinde, çerçeve çağıracak `COleDataSource::OnRenderData`, hangi geçersiz kılmanız gerekir.

     -veya-

- Kullanıyorsanız bir `CFile` veri sağlamak için nesne çağrısı `COleDataSource::DelayRenderFileData` yerine `COleDataSource::DelayRenderData` önceki seçeneği. Veri istendiğinde, çerçeve çağıracak `COleDataSource::OnRenderFileData`, hangi geçersiz kılmanız gerekir.

##  <a name="_core_determining_the_formats_available_in_a_data_object"></a> Bir veri nesnesi içinde kullanılabilir biçimleri belirleme

Bir uygulama veri yapıştırın kullanıcıya vermeden önce işleyebileceği panoya biçimleri olup olmadığını bilmek ister. Bunu yapmak için uygulamanızı şunları yapmalıdır:

1. Oluşturma bir `COleDataObject` nesnesi ve bir **FORMATETC** yapısı.

1. Veri nesnesinin çağrı `AttachClipboard` Panodaki veriler veri nesnesi ilişkilendirmek için üye işlevi.

1. Aşağıdakilerden birini yapın:

   - Veri nesnesinin çağrı `IsDataAvailable` üye işlevi, yalnızca bir veya iki biçimler gerekir. Bu durumda burada Panodaki veriler, uygulamanızın daha önemli ölçüde daha fazla destekler zaman kazanabilirsiniz.

         -or-

   - Veri nesnesinin çağrı `BeginEnumFormats` panoya biçimlerinden numaralandırma başlatmak için üye işlevi. Ardından çağırın `GetNextFormat` Pano dönene kadar uygulamanızın bir biçimini destekler veya daha fazla hiçbir biçimi vardır.

Kullanıyorsanız **on_update_command_uı**, yapıştırma ve muhtemelen, Düzen menüsündeki Özel Yapıştır öğeler artık etkinleştirebilirsiniz. Bunu yapmak için çağırın ya da `CMenu::EnableMenuItem` veya `CCmdUI::Enable`. Hangi kapsayıcı hakkında daha fazla bilgi için uygulamalar ile menü öğesi yapın ve gerekir, bkz [menüler ve kaynaklar: Kapsayıcı ekleme](../mfc/menus-and-resources-container-additions.md).

##  <a name="_core_retrieving_data_from_a_data_object"></a> Bir veri nesnesinden veriyi geri alma

Veri biçimi verdikten sonra kalan tek şey veri nesneden verileri almak üzere. Bunu yapmak için kullanıcı verileri nereye karar ve uygulama uygun işlevi çağırır. Veriler aşağıdaki ortamları birinde kullanılabilir olacak:

|Orta|Çağrılacak işlevi|
|------------|----------------------|
|Genel bellek (`HGLOBAL`)|`COleDataObject::GetGlobalData`|
|Dosya (`CFile`)|`COleDataObject::GetFileData`|
|**STGMEDIUM** yapısı (`IStorage`)|`COleDataObject::GetData`|

Yaygın olarak, ortam, Pano biçimi ile birlikte belirtilir. Örneğin, bir **CF_EMBEDDEDSTRUCT** nesnesi içinde her zaman bir `IStorage` gerektiren Orta bir **STGMEDIUM** yapısı. Bu nedenle, kullanacağınız `GetData` kabul edebilen bu işlevler yalnızca biri olduğundan bir **STGMEDIUM** yapısı.

Pano biçimi olduğu durumlarda bir `IStream` veya `HGLOBAL` Orta, çerçeve sağlayabilir bir `CFile` verilerine başvuran bir işaretçi. Uygulama, daha sonra dosya okuma gibi bir dosyadan veri içeri aktarabilir verilerin aynı şekilde almak için kullanabilirsiniz. Esas olarak, istemci tarafı arabirimi budur `OnRenderData` ve `OnRenderFileData` veri kaynağındaki yordamları.

Belgeye verileri Ekle, diğer tüm veriler aynı biçimde için olduğu gibi artık kullanıcı geçirebilirsiniz.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Sürükle ve bırak](../mfc/drag-and-drop-ole.md)

- [Pano](../mfc/clipboard.md)

## <a name="see-also"></a>Ayrıca bkz.

[Veri Nesneleri ve Veri Kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md)<br/>
[COleDataObject Sınıfı](../mfc/reference/coledataobject-class.md)<br/>
[COleDataSource Sınıfı](../mfc/reference/coledatasource-class.md)
