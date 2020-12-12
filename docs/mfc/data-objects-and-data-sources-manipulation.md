---
description: 'Hakkında daha fazla bilgi edinin: veri nesneleri ve veri kaynakları: düzenleme'
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
ms.openlocfilehash: a9611fefc94e8437f9e0e5361e0d95972f867984
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291239"
---
# <a name="data-objects-and-data-sources-manipulation"></a>Veri Nesneleri ve Veri Kaynakları: Düzenleme

Bir veri nesnesi veya veri kaynağı oluşturulduktan sonra, veriler üzerinde veri ekleme ve kaldırma, verilerin bulunduğu biçimleri numaralandırma ve daha fazlası gibi yaygın olarak kullanılan birkaç işlem gerçekleştirebilirsiniz. Bu makalede, en yaygın işlemleri gerçekleştirmek için gereken teknikler açıklanmaktadır. Konu başlıkları şunlardır:

- [Veri kaynağına veri ekleme](#_core_inserting_data_into_a_data_source)

- [Veri nesnesinde kullanılabilen biçimleri belirleme](#_core_determining_the_formats_available_in_a_data_object)

- [Veri nesnesinden veri alma](#_core_retrieving_data_from_a_data_object)

## <a name="inserting-data-into-a-data-source"></a><a name="_core_inserting_data_into_a_data_source"></a> Veri kaynağına veri ekleme

Verilerin bir veri kaynağına nasıl eklendiği, verilerin anında veya isteğe bağlı olarak verilip verilmeyeceğini ve hangi medyada sağlandığına bağlıdır. Olanaklar aşağıda verilmiştir.

### <a name="supplying-data-immediately-immediate-rendering"></a>Verileri hemen sağlama (anında Işleme)

- `COleDataSource::CacheGlobalData`Veri tedarik ettiğiniz her Pano biçimi için tekrar tekrar çağırın. Kullanılacak Pano biçimini, verileri içeren belleğe yönelik bir tanıtıcıyı ve isteğe bağlı olarak, verileri açıklayan bir **FORMATETC** yapısını geçirin.

     -veya-

- Doğrudan **Stgorta** yapıları ile çalışmak istiyorsanız `COleDataSource::CacheData` `COleDataSource::CacheGlobalData` Yukarıdaki seçeneği yerine çağırın.

### <a name="supplying-data-on-demand-delayed-rendering"></a>Isteğe bağlı veri sağlama (Gecikmeli Işleme)

Bu, gelişmiş bir konudur.

- `COleDataSource::DelayRenderData`Veri tedarik ettiğiniz her Pano biçimi için tekrar tekrar çağırın. Kullanılacak Pano biçimini ve isteğe bağlı olarak, verileri açıklayan bir **FORMATETC** yapısını geçirin. Veriler istendiğinde, çerçeve, `COleDataSource::OnRenderData` geçersiz kılmanız gereken öğesini çağırır.

     -veya-

- `CFile`Verileri sağlamak için bir nesnesi kullanırsanız, `COleDataSource::DelayRenderFileData` `COleDataSource::DelayRenderData` önceki seçeneğinde yerine çağırın. Veriler istendiğinde, çerçeve, `COleDataSource::OnRenderFileData` geçersiz kılmanız gereken öğesini çağırır.

## <a name="determining-the-formats-available-in-a-data-object"></a><a name="_core_determining_the_formats_available_in_a_data_object"></a> Veri nesnesinde kullanılabilen biçimleri belirleme

Bir uygulama, kullanıcının içine veri yapıştırmasına izin vermeden önce, panoda işleyebileceği bir biçim olup olmadığını bilmesi gerekir. Bunu yapmak için uygulamanızın aşağıdakileri yapması gerekir:

1. Bir `COleDataObject` nesne ve bir **FORMATETC** yapısı oluşturun.

1. Veri `AttachClipboard` nesnesini panodaki verilerle ilişkilendirmek için veri nesnesinin üye işlevini çağırın.

1. Aşağıdakilerden birini yapın:

   - `IsDataAvailable`İhtiyaç duyduğunuz yalnızca bir veya iki biçim varsa, veri nesnesinin üye işlevini çağırın. Bu, panodaki verilerin uygulamanızdan önemli ölçüde daha fazla biçim desteklediği durumlarda size zaman kazandırır.

     \-veya

   - `BeginEnumFormats`Panoda bulunan biçimleri listeme başlamak için veri nesnesinin üye işlevini çağırın. Ardından `GetNextFormat` , pano uygulamanızın desteklediği bir biçim döndürdüğünden veya başka biçim kalmadığında çağırın.

**ON_UPDATE_COMMAND_UI** kullanıyorsanız, şimdi Yapıştır ' ı ve büyük olasılıkla özel öğeleri Yapıştır ' ı etkinleştirerek düzenleme menüsünü etkinleştirebilirsiniz. Bunu yapmak için ya da ' i çağırın `CMenu::EnableMenuItem` `CCmdUI::Enable` . Hangi kapsayıcı uygulamalarının menü öğeleri ve ne zaman yapması gerektiği hakkında daha fazla bilgi için bkz. [menüler ve kaynaklar: kapsayıcı eklemeleri](menus-and-resources-container-additions.md).

## <a name="retrieving-data-from-a-data-object"></a><a name="_core_retrieving_data_from_a_data_object"></a> Veri nesnesinden veri alma

Bir veri biçimi üzerinde karar verdikten sonra, veri nesnesinden verilerin alınması, tüm kalmaya devam eder. Bunu yapmak için Kullanıcı, verileri nereye koyacağına karar verir ve uygulama uygun işlevi çağırır. Veriler aşağıdaki ortaorelerin birinde kullanılabilir olacaktır:

|Orta|Çağrılacak işlev|
|------------|----------------------|
|Genel bellek ( `HGLOBAL` )|`COleDataObject::GetGlobalData`|
|Dosya ( `CFile` )|`COleDataObject::GetFileData`|
|**Stgorta** yapısı ( `IStorage` )|`COleDataObject::GetData`|

Genellikle, ortam, pano biçimiyle birlikte belirtilir. Örneğin, bir **CF_EMBEDDEDSTRUCT** nesnesi her zaman bir `IStorage` **stgmedium** yapısı gerektiren bir medyada bulunur. Bu nedenle, `GetData` bir **Stgmedium** yapısını kabul edebilecek bu işlevlerden yalnızca biri olduğu için kullanacaksınız.

Pano biçiminin bir `IStream` veya `HGLOBAL` Orta düzeyde olduğu durumlarda, çerçeve `CFile` verilere başvuran bir işaretçi sağlayabilir. Daha sonra uygulama, verileri bir dosyadaki verileri içeri aktarabilecek şekilde almak için dosya okuma 'yı kullanabilir. Temelde, bu, `OnRenderData` veri kaynağındaki ve yordamlarına yönelik istemci tarafı arabirimidir `OnRenderFileData` .

Kullanıcı artık aynı biçimdeki diğer veriler için olduğu gibi belgeye veri ekleyebilir.

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Sürükleyip bırakma](drag-and-drop-ole.md)

- [Pano](clipboard.md)

## <a name="see-also"></a>Ayrıca bkz.

[Veri nesneleri ve veri kaynakları (OLE)](data-objects-and-data-sources-ole.md)<br/>
[Cotadataobject sınıfı](reference/coledataobject-class.md)<br/>
[Cotadatasource sınıfı](reference/coledatasource-class.md)
