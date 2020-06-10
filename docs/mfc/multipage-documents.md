---
title: Birden Fazla Belge
ms.date: 11/19/2018
helpviewer_keywords:
- pagination [MFC]
- overriding [MFC], View class functions for printing
- OnPrepareDC method [MFC]
- CPrintInfo structure [MFC], multipage documents
- OnEndPrinting method [MFC]
- protocols [MFC], printing protocol
- document pages vs. printer pages [MFC]
- printer mode [MFC]
- printing [MFC], multipage documents
- printers [MFC], printer mode
- documents [MFC], printing
- OnPreparePrinting method [MFC]
- OnPrint method [MFC]
- DoPreparePrinting method and pagination [MFC]
- OnDraw method [MFC], printing
- pagination [MFC], printing multipage documents
- printing [MFC], protocol
- pages [MFC], printing
- OnBeginPrinting method [MFC]
- multipage documents [MFC]
- printing [MFC], pagination
- documents [MFC], paginating
ms.assetid: 69626b86-73ac-4b74-b126-9955034835ef
ms.openlocfilehash: c73692c315b07d6b690180886d494ee12f85f52d
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621050"
---
# <a name="multipage-documents"></a>Birden Fazla Belge

Bu makalede Windows Yazdırma Protokolü açıklanmakta ve birden fazla sayfa içeren belgelerin nasıl yazdırılacağı açıklanmaktadır. Makalede aşağıdaki konular ele alınmaktadır:

- [Yazdırma Protokolü](#_core_the_printing_protocol)

- [Görünüm sınıfı işlevlerini geçersiz kılma](#_core_overriding_view_class_functions)

- [Mayı](#_core_pagination)

- [Yazıcı sayfaları ve belge sayfaları karşılaştırması](#_core_printer_pages_vs.._document_pages)

- [Yazdırma zamanı sayfalandırma](#_core_print.2d.time_pagination)

## <a name="the-printing-protocol"></a><a name="_core_the_printing_protocol"></a>Yazdırma Protokolü

Çok sayfalı bir belgeyi yazdırmak için çerçeve ve Görünüm aşağıdaki şekilde etkileşime geçin. İlk çerçeve **Yazdır** iletişim kutusunu görüntüler, yazıcı için bir cihaz bağlamı oluşturur ve [CDC](reference/cdc-class.md) nesnesinin [StartDoc](reference/cdc-class.md#startdoc) üye işlevini çağırır. Ardından, belgenin her sayfası için çerçeve nesnenin [StartPage](reference/cdc-class.md#startpage) üye işlevini çağırır `CDC` , görünüm nesnesine sayfayı yazdırmasını söyler ve [EndPage](reference/cdc-class.md#endpage) üye işlevini çağırır. Yazıcı modunun belirli bir sayfa başlatılmadan önce değiştirilmesi gerekiyorsa, görünüm, yeni yazıcı modu bilgilerini içeren [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) yapısını güncelleştiren [ResetDC](reference/cdc-class.md#resetdc)'yi çağırır. Belgenin tamamı yazdırıldığında, çerçeve [EndDoc](reference/cdc-class.md#enddoc) üye işlevini çağırır.

## <a name="overriding-view-class-functions"></a><a name="_core_overriding_view_class_functions"></a>Görünüm sınıfı Işlevlerini geçersiz kılma

[CView](reference/cview-class.md) sınıfı, yazdırma sırasında çerçeve tarafından çağrılan çeşitli üye işlevlerini tanımlar. Görünüm sınıfınızdaki bu işlevleri geçersiz kılarak, Framework 'ün yazdırma mantığı ve Görünüm sınıfınızın yazdırma mantığı arasındaki bağlantıları sağlarsınız. Aşağıdaki tabloda bu üye işlevleri listelenmektedir.

### <a name="cviews-overridable-functions-for-printing"></a>CView 'in yazdırma için geçersiz kılınabilir Işlevleri

|Name|Geçersiz kılma nedeni|
|----------|---------------------------|
|[OnPreparePrinting](reference/cview-class.md#onprepareprinting)|Yazdır iletişim kutusuna değerler eklemek için, özellikle belgenin uzunluğu|
|[OnBeginPrinting](reference/cview-class.md#onbeginprinting)|Yazı tiplerini veya diğer GDI kaynaklarını ayırmak için|
|[OnPrepareDC](reference/cview-class.md#onpreparedc)|Belirli bir sayfa için cihaz bağlamının özniteliklerini ayarlamak veya yazdırma zamanı sayfalandırmayı yapmak için|
|[Yazdırma](reference/cview-class.md#onprint)|Belirli bir sayfayı yazdırmak için|
|[OnEndPrinting](reference/cview-class.md#onendprinting)|GDI kaynaklarını serbest bırakmak için|

Yazdırma ile ilgili işlemeyi diğer işlevlerde da yapabilirsiniz, ancak bu işlevler yazdırma sürecini belirten alanlardır.

Aşağıdaki şekilde, yazdırma işleminde yer alan adımlar gösterilmektedir ve her birinin `CView` yazdırma üyesi işlevlerinin nerede çağrıldığını gösterir. Bu makalenin geri kalanında bu adımların çoğu daha ayrıntılı olarak açıklanmaktadır. Yazdırma sürecinin ek bölümleri, [GDI kaynaklarını ayırma](allocating-gdi-resources.md)makalesinde açıklanmaktadır.

![Döngü işlemi yazdırılıyor](../mfc/media/vc37c71.gif "Döngü işlemi yazdırılıyor") <br/>
Yazdırma döngüsü

## <a name="pagination"></a><a name="_core_pagination"></a>Mayı

Framework bir [CPrintInfo](reference/cprintinfo-structure.md) yapısında bir yazdırma işi hakkındaki bilgilerin çoğunu depolar. İçindeki bazı değerler `CPrintInfo` Sayfalandırmaya aittir; bu değerler aşağıdaki tabloda gösterildiği gibi erişilebilir.

### <a name="page-number-information-stored-in-cprintinfo"></a>CPrintInfo 'da depolanan sayfa numarası bilgileri

|Üye değişkeni veya<br /><br /> işlev adı (ler)|Başvurulan sayfa numarası|
|-----------------------------------------------|----------------------------|
|`GetMinPage`/`SetMinPage`|Belgenin ilk sayfası|
|`GetMaxPage`/`SetMaxPage`|Belgenin son sayfası|
|`GetFromPage`|Yazdırılacak ilk sayfa|
|`GetToPage`|Yazdırılacak son sayfa|
|`m_nCurPage`|Sayfa Şu anda yazdırılıyor|

Sayfa numaraları 1 ' den başlar, diğer bir deyişle, ilk sayfa 0 değil 1 numaralandırılır. Bu ve diğer [CPrintInfo](reference/cprintinfo-structure.md)üyeleri hakkında daha fazla bilgi için bkz. *MFC başvurusu*.

Yazdırma işleminin başlangıcında çerçeve, görünümün [OnPreparePrinting](reference/cview-class.md#onprepareprinting) üye işlevini çağırır ve bir yapıya işaretçi geçirmektir `CPrintInfo` . Uygulama Sihirbazı `OnPreparePrinting` , diğer bir üye işlevi olan [DoPreparePrinting](reference/cview-class.md#doprepareprinting)çağrısı yapan bir uygulaması sağlar `CView` . `DoPreparePrinting`, Yazdır iletişim kutusunu görüntüleyen ve bir yazıcı cihaz bağlamı oluşturan işlevdir.

Bu noktada, uygulama belgede kaç sayfa olduğunu bilmez. Belgenin ilk ve son sayfasının sayıları için 1 ve 0xFFFF varsayılan değerlerini kullanır. Belgenizin kaç sayfa olduğunu biliyorsanız, ' a göndermeden `OnPreparePrinting` önce yapı için [SetMaxPage]--brokenlınk--(Reference/CPrintInfo-Class. MD # SetMaxPage) öğesini geçersiz kılın ve çağırın `CPrintInfo` `DoPreparePrinting` . Bu, belgenizin uzunluğunu belirtmenizi sağlar.

`DoPreparePrinting`ardından Yazdır iletişim kutusunu görüntüler. Döndüğünde, `CPrintInfo` Yapı Kullanıcı tarafından belirtilen değerleri içerir. Kullanıcı yalnızca seçili bir sayfa aralığını yazdırmaya istiyorsa, Yazdır iletişim kutusunda başlangıç ve bitiş sayfa numaralarını belirtebilir. Framework, `GetFromPage` `GetToPage` [CPrintInfo](reference/cprintinfo-structure.md)'ın ve işlevlerini kullanarak bu değerleri alır. Kullanıcı bir sayfa aralığı belirtmezse, çerçeve `GetMinPage` `GetMaxPage` Tüm belgeyi yazdırmak için döndürülen değerleri çağırır ve kullanır.

Bir belgenin yazdırılacağı her sayfasında çerçeve, görünüm sınıfınıza ait iki üye işlevini çağırarak, [Onhazırlık EDC](reference/cview-class.md#onpreparedc) ve [OnPrint](reference/cview-class.md#onprint)ve her bir işlevi iki parametre olarak geçirir: bir [CDC](reference/cdc-class.md) nesnesi işaretçisi ve bir `CPrintInfo` Yapı işaretçisi. Framework ve her çağırdığında `OnPrepareDC` `OnPrint` , yapının *m_nCurPage* üyesine farklı bir değer geçirir `CPrintInfo` . Bu şekilde Framework, görüntülenecek sayfanın yazdırılması gerektiğini gösterir.

[Onhazırlık EDC](reference/cview-class.md#onpreparedc) üye işlevi ekran görüntüleme için de kullanılır. Çizim gerçekleşmeden önce cihaz bağlamında ayarlamalar yapar. `OnPrepareDC`yazdırırken benzer bir rol sunar, ancak birkaç fark vardır: ilk, `CDC` nesne bir ekran cihaz bağlamı yerine bir yazıcı cihaz bağlamını temsil eder ve ikinci olarak bir `CPrintInfo` nesne ikinci bir parametre olarak geçirilir. (Bu parametre, **NULL** `OnPrepareDC` ekran görüntüleme için çağrıldığında null olur.) `OnPrepareDC`Cihaz bağlamına hangi sayfanın yazdırıldığını belirleyen ayarlamalar yapmak için geçersiz kılın. Örneğin, belgenin uygun kısmının yazdırılmasını sağlamak için görünüm kutusu başlangıcını ve kırpma bölgesini taşıyabilirsiniz.

[OnPrint](reference/cview-class.md#onprint) üye işlevi, sayfanın gerçek yazdırma işlemini gerçekleştirir. [Varsayılan yazdırma](how-default-printing-is-done.md) işlemi, çerçevenin yazdırma işlemini gerçekleştirmek için bir yazıcı cihaz bağlamı Ile [OnDraw](reference/cview-class.md#ondraw) 'ın nasıl çağırılamadığını gösterir. Daha kesin olarak, Framework `OnPrint` bir `CPrintInfo` yapıyla ve bir cihaz içeriğiyle çağrı yapar ve `OnPrint` cihaz bağlamını ' ye geçirir `OnDraw` . `OnPrint`Yalnızca yazdırma sırasında yapılması gereken, ekran görüntüsü için değil, herhangi bir işlemeyi gerçekleştirmek için geçersiz kılın. Örneğin, üst bilgileri veya altbilgileri yazdırmak için (daha fazla bilgi için bkz. [başlıklar ve altbilgiler](headers-and-footers.md) makalesine bakın). Sonra, `OnDraw` `OnPrint` oluşturma işlemini hem ekran görüntüleme hem de yazdırma için ortak yapmak için geçersiz kılmada çağırın.

`OnDraw`Hem ekran görüntüleme hem de yazdırma için işleme yapan olgu, UYGULAMANıZıN WYSIWYG olduğu anlamına gelir: "gördükleriniz." Ancak, bir WYSıWYG uygulaması yazmadığınızı varsayalım. Örneğin, yazdırma için kalın yazı tipi kullanan bir metin düzenleyicisini düşünün ancak ekranda kalın metin göstermek için denetim kodlarını görüntüler. Böyle bir durumda, `OnDraw` kesinlikle ekran görüntüsü için kullanırsınız. Geçersiz kıldığınızda `OnPrint` , çağrısını `OnDraw` ayrı bir çizim işlevine çağrısıyla değiştirin. Bu işlev, ekranda görüntülenmeyin öznitelikleri kullanarak belgeyi kağıda göründüğü şekilde çizer.

## <a name="printer-pages-vs-document-pages"></a><a name="_core_printer_pages_vs.._document_pages"></a>Yazıcı sayfaları ve belge sayfaları karşılaştırması

Sayfa numaralarına başvurduğunuzda, bazen yazıcının bir sayfa kavramı ve bir belgenin kavramı arasında ayrım yapmak gerekir. Yazıcının görünüm noktasından bir sayfa bir kağıt yaprabiridir. Ancak, bir kağıt yaprağının belgenin bir sayfasına eşit olması gerekmez. Örneğin, sayfaların katlanmakta olduğu bir Bülteni yazdırıyorsanız, tek bir kağıda belgenin her ikisi ve son sayfaları, yan yana olabilir. Benzer şekilde, bir elektronik tablo yazdırıyorsanız belge, hiç sayfadan oluşamaz. Bunun yerine, bir kağıda bir kağıt 1 ile 20 arasındaki sütunlar, 6 ile 10 arasında bir sayfa içerebilir.

[CPrintInfo](reference/cprintinfo-structure.md) yapısındaki tüm sayfa numaraları yazıcı sayfalarına başvurur. Çerçeve, `OnPrepareDC` `OnPrint` yazıcıdan geçirilecek her bir kağıt sayfası için ve bir kez çağırır. Belge uzunluğunu belirtmek için [OnPreparePrinting](reference/cview-class.md#onprepareprinting) işlevini geçersiz kıldığınızda, yazıcı sayfalarını kullanmanız gerekir. Bire bir yazışmalar varsa (yani, bir yazıcı sayfası bir belge sayfasına eşitse), bu oldukça kolaydır. Diğer taraftan, belge sayfaları ve yazıcı sayfaları doğrudan karşılık gelmiyorsa, aralarında çeviri yapmanız gerekir. Örneğin, bir elektronik tablo yazdırmayı göz önünde bulundurun. Geçersiz kıldığınızda `OnPreparePrinting` , tüm elektronik tabloyu yazdırmak için kaç yaprak kağıt gerektiğini hesaplamanız ve sonra üye işlevini çağırırken bu değeri kullanmanız gerekir `SetMaxPage` `CPrintInfo` . Benzer şekilde, geçersiz kılma sırasında `OnPrepareDC` , *m_nCurPage* söz konusu sayfada görünecek satırlar ve sütunlar aralığına çevirmeniz ve sonra da görünüm kaynağını uygun şekilde ayarlamanız gerekir.

## <a name="print-time-pagination"></a><a name="_core_print.2d.time_pagination"></a>Yazdırma zamanı sayfalandırma

Bazı durumlarda, görünüm sınıfınız belgenin gerçekten yazdırılana kadar ne kadar sürdüğünü önceden bilmiyor olabilir. Örneğin, uygulamanızın WYSıWYG olmadığını varsayalım, bu yüzden bir belgenin uzunluğu, yazdırıldığında bu uzunluğa karşılık gelmez.

Bu, görünüm sınıfınız için [OnPreparePrinting](reference/cview-class.md#onprepareprinting) 'i geçersiz kıldığınızda bir soruna neden olur: `SetMaxPage` bir belgenin uzunluğunu bilmiyorsanız [CPrintInfo](reference/cprintinfo-structure.md) yapısının işlevine bir değer geçirilemez. Kullanıcı Yazdır iletişim kutusunu kullanırken durdurulacak bir sayfa numarası belirtmezse, çerçeve, yazdırma döngüsünün ne zaman durdurulacağını bilmez. Yazdırma döngüsünün ne zaman durdurulacağını belirlemenin tek yolu belgeyi yazdırmaktır ve ne zaman sona ereceğini görür. Görünüm sınıfınızın belge yazdırılırken belgenin sonunu denetlemesi ve sonra da sona ulaşıldığında çerçeveyi bilgilendirmeniz gerekir.

Framework, ne zaman durdurulacağını anlatmak için Görünüm sınıfınızın [Onhazırlık EDC](reference/cview-class.md#onpreparedc) işlevini kullanır. Her çağrısından sonra `OnPrepareDC` Framework, `CPrintInfo` *m_bContinuePrinting*adlı yapının bir üyesini denetler. Varsayılan değeri true 'dur **.** Bu şekilde kaldığı sürece çerçeve, yazdırma döngüsüne devam eder. **Yanlış**olarak ayarlanırsa, çerçeve duraklar. Yazdırma zamanı sayfalandırmayı gerçekleştirmek için, `OnPrepareDC` belgenin sonuna ulaşılıp ulaşılmadığını denetlemek için geçersiz kılın ve olduğunda *m_bContinuePrinting* **false** olarak ayarlayın.

`OnPrepareDC`Geçerli sayfa 1 ' den büyükse, varsayılan ayarlar *m_bContinuePrinting* **false** olarak ayarlanır. Bu, belgenin uzunluğu belirtilmemişse, çerçevenin belgenin bir sayfa uzunluğunda olduğunu varsaydığı anlamına gelir. Bunun bir sonucu, temel sınıf sürümünü çağırdığınızda dikkatli olmanız gerekir `OnPrepareDC` . Temel sınıf sürümü çağrıldıktan sonra *M_bContinuePrinting* **true** olacağını varsayın.

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Üstbilgiler ve altbilgiler](headers-and-footers.md)

- [GDI kaynaklarını ayırma](allocating-gdi-resources.md)

## <a name="see-also"></a>Ayrıca bkz.

[Yazdırma](printing.md)<br/>
[CView sınıfı](reference/cview-class.md)<br/>
[CDC sınıfı](reference/cdc-class.md)
