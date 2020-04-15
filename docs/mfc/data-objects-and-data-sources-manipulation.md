---
title: 'Veri Nesneleri ve Veri Kaynakları: Düzenleme'
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
ms.openlocfilehash: a08b6ff274c73d301c156d65aa56fbecca49128c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370545"
---
# <a name="data-objects-and-data-sources-manipulation"></a>Veri Nesneleri ve Veri Kaynakları: Düzenleme

Bir veri nesnesi veya veri kaynağı oluşturulduktan sonra, veri ekleme ve kaldırma, verilerin içinde olduğu biçimleri numaralandırma ve daha fazlası gibi veriler üzerinde bir dizi yaygın işlem gerçekleştirebilirsiniz. Bu makalede, en yaygın işlemleri tamamlamak için gerekli teknikler açıklanmaktadır. Konu başlıkları şunlardır:

- [Veri kaynağına veri ekleme](#_core_inserting_data_into_a_data_source)

- [Veri nesnesinde kullanılabilen biçimleri belirleme](#_core_determining_the_formats_available_in_a_data_object)

- [Veri nesnesinden veri alma](#_core_retrieving_data_from_a_data_object)

## <a name="inserting-data-into-a-data-source"></a><a name="_core_inserting_data_into_a_data_source"></a>Veri Kaynağına Veri Ekleme

Verilerin bir veri kaynağına nasıl eklendiği, verilerin hemen veya isteğe bağlı olarak sağlanıp sağlanmadığına ve hangi ortamda sağlandığına bağlıdır. Olasılıklar aşağıdaki gibidir.

### <a name="supplying-data-immediately-immediate-rendering"></a>Hemen Veri Sağlama (Anında İşleme)

- Veri `COleDataSource::CacheGlobalData` sağladığınız her Pano biçimi için tekrar tekrar arayın. Kullanılacak Pano biçimini, verileri içeren belleğe bir tutamacı ve isteğe bağlı olarak verileri açıklayan bir **FORMATETC** yapısını geçirin.

     -veya-

- Doğrudan **STGMEDIUM** yapıları ile çalışmak istiyorsanız, `COleDataSource::CacheData` yukarıdaki `COleDataSource::CacheGlobalData` seçenek yerine arama.

### <a name="supplying-data-on-demand-delayed-rendering"></a>Talep Üzerine Veri Sağlama (Gecikmeli İşleme)

Bu gelişmiş bir konudur.

- Veri `COleDataSource::DelayRenderData` sağladığınız her Pano biçimi için tekrar tekrar arayın. Kullanılacak Pano biçimini ve isteğe bağlı olarak verileri açıklayan bir **FORMATETC** yapısını geçirin. Veriler istendiğinde, çerçeve, geçersiz `COleDataSource::OnRenderData`kılmanız gereken çağrıyı arayacaktır.

     -veya-

- Verileri sağlamak `CFile` için bir nesne kullanıyorsanız, `COleDataSource::DelayRenderData` önceki seçenek yerine arayın. `COleDataSource::DelayRenderFileData` Veriler istendiğinde, çerçeve, geçersiz `COleDataSource::OnRenderFileData`kılmanız gereken çağrıyı arayacaktır.

## <a name="determining-the-formats-available-in-a-data-object"></a><a name="_core_determining_the_formats_available_in_a_data_object"></a>Veri Nesnesinde Bulunan Biçimleri Belirleme

Bir uygulama, kullanıcının verileri bu uygulamaya yapıştırmasına izin vermeden önce, Pano'da işleyebilir biçimleri olup olmadığını bilmesi gerekir. Bunu yapmak için, uygulamanız aşağıdakileri yapmalıdır:

1. Bir `COleDataObject` nesne ve **FORMATETC** yapısı oluşturun.

1. Veri nesnesini Pano'daki verilerle ilişkilendirmek için veri nesnesinin `AttachClipboard` üye işlevini arayın.

1. Aşağıdakilerden birini yapın:

   - İhtiyacınız olan yalnızca `IsDataAvailable` bir veya iki biçim varsa veri nesnesinin üye işlevini arayın. Bu, Pano'daki verilerin uygulamanızdan önemli ölçüde daha fazla biçimi desteklediği durumlarda size zaman kazandırır.

     \-veya-

   - Pano'da bulunan `BeginEnumFormats` biçimleri sayısallandırmaya başlamak için veri nesnesinin üye işlevini arayın. Ardından, `GetNextFormat` Pano uygulamanızın desteklediği veya başka biçim olmayan bir biçimi döndürene kadar arayın.

**ON_UPDATE_COMMAND_UI**kullanıyorsanız, artık Ekle menüsündeki Yapıştır'ı ve muhtemelen Özel öğeleri yapıştır'ı etkinleştirebilirsiniz. Bunu yapmak için, `CMenu::EnableMenuItem` `CCmdUI::Enable`ya arayın ya da . Kapsayıcı uygulamalarının menü öğeleriyle ne yapması gerektiği ve ne zaman yapması gerektiği hakkında daha fazla bilgi için [Menüler ve Kaynaklar: Kapsayıcı Eklemeleri'ne](../mfc/menus-and-resources-container-additions.md)bakın.

## <a name="retrieving-data-from-a-data-object"></a><a name="_core_retrieving_data_from_a_data_object"></a>Veri Nesnesinden Veri Alma

Bir veri biçimine karar verdikten sonra, geriye kalan tek şey verileri veri nesnesinden almaktır. Bunu yapmak için, kullanıcı verileri nereye koyacağına karar verir ve uygulama uygun işlevi çağırır. Veriler aşağıdaki ortamlardan birinde kullanılabilir:

|Orta|Aramak için fonksiyon|
|------------|----------------------|
|Genel Bellek`HGLOBAL`( )|`COleDataObject::GetGlobalData`|
|Dosya`CFile`( )|`COleDataObject::GetFileData`|
|**STGMEDIUM** yapısı`IStorage`( )|`COleDataObject::GetData`|

Genellikle, ortam Pano biçimiyle birlikte belirtilir. Örneğin, **CF_EMBEDDEDSTRUCT** bir nesne her `IStorage` zaman **STGMEDIUM** yapısı gerektiren bir ortamdadır. Bu nedenle, `GetData` bir **STGMEDIUM** yapısını kabul edebilen bu işlevlerden yalnızca biri olduğu için kullanırsınız.

Pano biçiminin bir `IStream` veya `HGLOBAL` orta düzeyde olduğu durumlarda, `CFile` çerçeve verilere başvuruyapan bir işaretçi sağlayabilir. Uygulama daha sonra, verileri bir dosyadan veri içe aktarabileceği şekilde almak için dosya okumasını kullanabilir. Esasen, bu veri kaynağında `OnRenderData` ve `OnRenderFileData` yordamları için istemci tarafı arabirimidir.

Kullanıcı artık aynı biçimdeki diğer veriler de olduğu gibi belgeye de veri ekleyebilir.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilmek istiyorum

- [Sürükle ve bırak](../mfc/drag-and-drop-ole.md)

- [Pano](../mfc/clipboard.md)

## <a name="see-also"></a>Ayrıca bkz.

[Veri Nesneleri ve Veri Kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md)<br/>
[COleDataObject Sınıfı](../mfc/reference/coledataobject-class.md)<br/>
[COleDataSource Sınıfı](../mfc/reference/coledatasource-class.md)
