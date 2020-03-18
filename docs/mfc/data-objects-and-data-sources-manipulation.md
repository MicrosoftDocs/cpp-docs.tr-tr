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
ms.openlocfilehash: adbe2a77fb0069e9874ab20a51b3ab08aabbe1f6
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446996"
---
# <a name="data-objects-and-data-sources-manipulation"></a>Veri Nesneleri ve Veri Kaynakları: Düzenleme

Bir veri nesnesi veya veri kaynağı oluşturulduktan sonra, veriler üzerinde veri ekleme ve kaldırma, verilerin bulunduğu biçimleri numaralandırma ve daha fazlası gibi yaygın olarak kullanılan birkaç işlem gerçekleştirebilirsiniz. Bu makalede, en yaygın işlemleri gerçekleştirmek için gereken teknikler açıklanmaktadır. Konu başlıkları şunlardır:

- [Veri kaynağına veri ekleme](#_core_inserting_data_into_a_data_source)

- [Veri nesnesinde kullanılabilen biçimleri belirleme](#_core_determining_the_formats_available_in_a_data_object)

- [Veri nesnesinden veri alma](#_core_retrieving_data_from_a_data_object)

##  <a name="_core_inserting_data_into_a_data_source"></a>Veri kaynağına veri ekleme

Verilerin bir veri kaynağına nasıl eklendiği, verilerin anında veya isteğe bağlı olarak verilip verilmeyeceğini ve hangi medyada sağlandığına bağlıdır. Olanaklar aşağıda verilmiştir.

### <a name="supplying-data-immediately-immediate-rendering"></a>Verileri hemen sağlama (anında Işleme)

- Veri tedarik ettiğiniz her Pano biçimi için `COleDataSource::CacheGlobalData` tekrar tekrar çağırın. Kullanılacak Pano biçimini, verileri içeren belleğe yönelik bir tanıtıcıyı ve isteğe bağlı olarak, verileri açıklayan bir **FORMATETC** yapısını geçirin.

     -veya-

- Doğrudan **Stgorta** yapıları ile çalışmak istiyorsanız yukarıdaki seçeneğinde `COleDataSource::CacheGlobalData` yerine `COleDataSource::CacheData` çağırın.

### <a name="supplying-data-on-demand-delayed-rendering"></a>Isteğe bağlı veri sağlama (Gecikmeli Işleme)

Bu, gelişmiş bir konudur.

- Veri tedarik ettiğiniz her Pano biçimi için `COleDataSource::DelayRenderData` tekrar tekrar çağırın. Kullanılacak Pano biçimini ve isteğe bağlı olarak, verileri açıklayan bir **FORMATETC** yapısını geçirin. Veriler istendiğinde, çerçeve geçersiz kılmanız gereken `COleDataSource::OnRenderData`çağırır.

     -veya-

- Verileri sağlamak için bir `CFile` nesnesi kullanıyorsanız, önceki seçeneğinde `COleDataSource::DelayRenderData` yerine `COleDataSource::DelayRenderFileData` çağırın. Veriler istendiğinde, çerçeve geçersiz kılmanız gereken `COleDataSource::OnRenderFileData`çağırır.

##  <a name="_core_determining_the_formats_available_in_a_data_object"></a>Veri nesnesinde kullanılabilen biçimleri belirleme

Bir uygulama, kullanıcının içine veri yapıştırmasına izin vermeden önce, panoda işleyebileceği bir biçim olup olmadığını bilmesi gerekir. Bunu yapmak için uygulamanızın aşağıdakileri yapması gerekir:

1. `COleDataObject` nesnesi ve **FORMATETC** yapısı oluşturun.

1. Veri nesnesini panodaki verilerle ilişkilendirmek için veri nesnesinin `AttachClipboard` üye işlevini çağırın.

1. Aşağıdakilerden birini yapın:

   - İhtiyaç duyduğunuz yalnızca bir veya iki biçim varsa, veri nesnesinin `IsDataAvailable` üye işlevini çağırın. Bu, panodaki verilerin uygulamanızdan önemli ölçüde daha fazla biçim desteklediği durumlarda size zaman kazandırır.

     \-veya-

   - Panoda bulunan biçimleri listeme başlamak için veri nesnesinin `BeginEnumFormats` üye işlevini çağırın. Ardından, pano uygulamanızın desteklediği bir biçim döndürdüğünden veya daha fazla biçim bulunmadığından `GetNextFormat` çağırın.

**ON_UPDATE_COMMAND_UI**kullanıyorsanız, şimdi Yapıştır ' ı ve büyük olasılıkla özel öğeleri Yapıştır ' ı etkinleştirerek düzenleme menüsünü etkinleştirebilirsiniz. Bunu yapmak için `CMenu::EnableMenuItem` ya da `CCmdUI::Enable`çağırın. Hangi kapsayıcı uygulamalarının menü öğeleri ve ne zaman yapması gerektiği hakkında daha fazla bilgi için bkz. [menüler ve kaynaklar: kapsayıcı eklemeleri](../mfc/menus-and-resources-container-additions.md).

##  <a name="_core_retrieving_data_from_a_data_object"></a>Veri nesnesinden veri alma

Bir veri biçimi üzerinde karar verdikten sonra, veri nesnesinden verilerin alınması, tüm kalmaya devam eder. Bunu yapmak için Kullanıcı, verileri nereye koyacağına karar verir ve uygulama uygun işlevi çağırır. Veriler aşağıdaki ortaorelerin birinde kullanılabilir olacaktır:

|Orta|Çağrılacak işlev|
|------------|----------------------|
|Genel bellek (`HGLOBAL`)|`COleDataObject::GetGlobalData`|
|Dosya (`CFile`)|`COleDataObject::GetFileData`|
|**Stgorta** yapısı (`IStorage`)|`COleDataObject::GetData`|

Genellikle, ortam, pano biçimiyle birlikte belirtilir. Örneğin, bir **CF_EMBEDDEDSTRUCT** nesnesi her zaman bir **stgmedium** yapısı gerektiren bir `IStorage` ortamıdır. Bu nedenle, bir **Stgmedium** yapısını kabul edebilecek bu işlevlerden yalnızca biri olduğundan `GetData` kullanırsınız.

Pano biçiminin bir `IStream` veya `HGLOBAL` ortamında olduğu durumlarda, çerçeve verilere başvuran bir `CFile` işaretçisi sağlayabilir. Daha sonra uygulama, verileri bir dosyadaki verileri içeri aktarabilecek şekilde almak için dosya okuma 'yı kullanabilir. Temelde, bu, veri kaynağındaki `OnRenderData` ve `OnRenderFileData` yordamlarına yönelik istemci tarafı arabirimidir.

Kullanıcı artık aynı biçimdeki diğer veriler için olduğu gibi belgeye veri ekleyebilir.

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Sürükleyip bırakma](../mfc/drag-and-drop-ole.md)

- [Pano](../mfc/clipboard.md)

## <a name="see-also"></a>Ayrıca bkz.

[Veri Nesneleri ve Veri Kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md)<br/>
[COleDataObject Sınıfı](../mfc/reference/coledataobject-class.md)<br/>
[COleDataSource Sınıfı](../mfc/reference/coledatasource-class.md)
