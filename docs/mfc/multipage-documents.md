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
ms.openlocfilehash: 87912c06a40740d25530235ee421c6c8bfa11aab
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370728"
---
# <a name="multipage-documents"></a>Birden Fazla Belge

Bu makalede, Windows yazdırma protokolü açıklanır ve birden fazla sayfa içeren belgelerin nasıl yazdırılacaaçıklanmıştır. Makale aşağıdaki konuları kapsamaktadır:

- [Yazdırma protokolü](#_core_the_printing_protocol)

- [Görünüm sınıfı işlevlerini geçersiz kılma](#_core_overriding_view_class_functions)

- [Sayfalandırma](#_core_pagination)

- [Yazıcı sayfaları ve belge sayfaları](#_core_printer_pages_vs.._document_pages)

- [Baskı zamanı pagination](#_core_print.2d.time_pagination)

## <a name="the-printing-protocol"></a><a name="_core_the_printing_protocol"></a>Yazdırma Protokolü

Çok sayfalı bir belge yazdırmak için çerçeve ve görünüm aşağıdaki şekilde etkileşime girecektir. Önce çerçeve **Yazdır** iletişim kutusunu görüntüler, yazıcı için bir aygıt bağlamı oluşturur ve [CDC](../mfc/reference/cdc-class.md) nesnesinin [StartDoc](../mfc/reference/cdc-class.md#startdoc) üye işlevini çağırır. Daha sonra, belgenin her sayfası için [StartPage](../mfc/reference/cdc-class.md#startpage) çerçeve `CDC` nesnenin Başlangıç Sayfası üye işlevini çağırır, sayfayı yazdırmak için görünüm nesnesine talimat verir ve [EndPage](../mfc/reference/cdc-class.md#endpage) üye işlevini çağırır. Belirli bir sayfayı başlatmadan önce yazıcı modunun değiştirilmesi gerekiyorsa, görünüm yeni yazıcı modu bilgilerini içeren [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) yapısını güncelleyen [ResetDC'yi](../mfc/reference/cdc-class.md#resetdc)çağırır. Belgenin tamamı yazdırıldığında, çerçeve [EndDoc](../mfc/reference/cdc-class.md#enddoc) üye işlevini çağırır.

## <a name="overriding-view-class-functions"></a><a name="_core_overriding_view_class_functions"></a>Görünüm Sınıfı İşlevlerini Geçersiz Kılma

[CView](../mfc/reference/cview-class.md) sınıfı, yazdırma sırasında çerçeve tarafından çağrılan birkaç üye işlevi tanımlar. Görünüm sınıfınızdaki bu işlevleri geçersiz kılarak, çerçevenin yazdırma mantığı ile görünüm sınıfınızın yazdırma mantığı arasındaki bağlantıları sağlarsınız. Aşağıdaki tabloda bu üye işlevler listelemektedir.

### <a name="cviews-overridable-functions-for-printing"></a>CView'in Yazdırma için Overridable İşlevleri

|Adı|Geçersiz kılma nedeni|
|----------|---------------------------|
|[OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)|Yazdır iletişim kutusuna, özellikle belgenin uzunluğuna değerleri eklemek için|
|[OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting)|Yazı tiplerini veya diğer GDI kaynaklarını ayırmak için|
|[Onpreparedc](../mfc/reference/cview-class.md#onpreparedc)|Belirli bir sayfa için aygıt bağlamının özniteliklerini ayarlamak veya yazdırma zamanı pagination yapmak için|
|[Onprint](../mfc/reference/cview-class.md#onprint)|Belirli bir sayfayı yazdırmak için|
|[OnEndPrinting](../mfc/reference/cview-class.md#onendprinting)|GDI kaynaklarını n için|

Yazdırmayla ilgili işlemleri diğer işlevlerde de yapabilirsiniz, ancak bu işlevler yazdırma işlemini yönlendiren işlevlerdir.

Aşağıdaki şekil, yazdırma işleminde yer alan adımları gösterir `CView`ve 'yazdırma üye işlevlerinin her birinin nerede çağrıldığını gösterir. Bu makalenin geri kalanı, bu adımların çoğunu daha ayrıntılı olarak açıklar. Yazdırma işleminin ek bölümleri [GDI Kaynaklarını Ayırma](../mfc/allocating-gdi-resources.md)makalesinde açıklanmıştır.

![Yazdırma döngüsü işlemi](../mfc/media/vc37c71.gif "Yazdırma döngüsü işlemi") <br/>
Yazdırma Döngüsü

## <a name="pagination"></a><a name="_core_pagination"></a>Sayfa -landırma

Çerçeve, [bir CPrintInfo](../mfc/reference/cprintinfo-structure.md) yapısında bir baskı işi yle ilgili bilgilerin çoğunu depolar. Pagination `CPrintInfo` ile ilgili değerlerin birkaçı; bu değerlere aşağıdaki tabloda gösterildiği gibi erişilebilir.

### <a name="page-number-information-stored-in-cprintinfo"></a>CPrintInfo'da Depolanan Sayfa Numarası Bilgileri

|Üye değişkeni veya<br /><br /> fonksiyon adı(lar)|Başvurulan sayfa numarası|
|-----------------------------------------------|----------------------------|
|`GetMinPage`/`SetMinPage`|Belgenin ilk sayfası|
|`GetMaxPage`/`SetMaxPage`|Belgenin son sayfası|
|`GetFromPage`|Basılacak ilk sayfa|
|`GetToPage`|Yazdırılacak son sayfa|
|`m_nCurPage`|Şu anda yazdırılmakta olan sayfa|

Sayfa numaraları 1'den başlar, diğer bir tarihte ilk sayfa 0 değil, 1 numaralanır. Bu ve [CPrintInfo](../mfc/reference/cprintinfo-structure.md)diğer üyeleri hakkında daha fazla bilgi için, *MFC Referans*bakın.

Yazdırma işleminin başında, çerçeve görünümün [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) üye işlevini çağırır ve bir `CPrintInfo` işaretçiyi bir yapıya geçer. Uygulama Sihirbazı, [doprepareprinting](../mfc/reference/cview-class.md#doprepareprinting), başka bir üye `CView`işlevi çağıran bir uygulama `OnPreparePrinting` sağlar. `DoPreparePrinting`Yazdır iletişim kutusunu görüntüleyen ve yazıcı aygıtı bağlamı oluşturan işlevdir.

Bu noktada uygulama belgede kaç sayfa olduğunu bilmez. Belgenin ilk ve son sayfasının numaraları için varsayılan 1 ve 0xFFFF değerlerini kullanır. Belgenizin kaç sayfaolduğunu biliyorsanız, `OnPreparePrinting` göndermeden önce `CPrintInfo` yapı için [SetMaxPage]--brokenlink--(reference/cprintinfo-class.md#setmaxpage) `DoPreparePrinting`numaralı telefonu geçersiz kılın ve arayın. Bu, belgenizin uzunluğunu belirtmenize olanak tanır.

`DoPreparePrinting`sonra Yazdır iletişim kutusunu görüntüler. Döndürdüğünde, `CPrintInfo` yapı kullanıcı tarafından belirtilen değerleri içerir. Kullanıcı yalnızca seçili bir sayfa aralığı yazdırmak isterse, Yazdır iletişim kutusunda başlangıç ve bitiş sayfa numaralarını belirtebilir. Çerçeve [CPrintInfo](../mfc/reference/cprintinfo-structure.md) `GetFromPage` ve `GetToPage` işlevlerini kullanarak bu değerleri alır. Kullanıcı bir sayfa aralığı belirtmezse, çerçeve `GetMinPage` arar `GetMaxPage` ve belgenin tamamını yazdırmak için döndürülen değerleri kullanır.

Bir belgenin yazdırılacak her sayfası için çerçeve, görünüm sınıfınızdaki [onPrepareDC](../mfc/reference/cview-class.md#onpreparedc) ve [OnPrint'teki](../mfc/reference/cview-class.md#onprint)iki üye işlevi çağırır ve her işlevi `CPrintInfo` iki parametreden geçirir: [CDC](../mfc/reference/cdc-class.md) nesnesine işaretçi ve bir yapıya işaretçi. `OnPrepareDC` Çerçeve her aradığında `OnPrint`ve yapının *m_nCurPage* üyesi `CPrintInfo` farklı bir değer geçer. Bu şekilde çerçeve, görünümün hangi sayfanın yazdırılması gerektiğini söyler.

[OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) üye işlevi de ekran ekranı için kullanılır. Çizim gerçekleşmeden önce aygıt bağlamında ayarlamalar yapar. `OnPrepareDC`yazdırmada da benzer bir rol oynar, ancak birkaç fark `CDC` vardır: birincisi, nesne ekran aygıtı bağlamı yerine `CPrintInfo` yazıcı aygıtı bağlamını temsil eder ve ikinci olarak nesne ikinci bir parametre olarak geçirilir. (Ekran ekranı için `OnPrepareDC` çağrıldığında bu parametre NULL'dur.) **NULL** Yazdırılan sayfaya göre aygıt bağlamında ayarlamalar yapmak için geçersiz kılın. `OnPrepareDC` Örneğin, belgenin uygun bölümünün yazdırıldığından emin olmak için görünüm kaynağı nın kaynağını ve kırpma bölgesini taşıyabilirsiniz.

[OnPrint](../mfc/reference/cview-class.md#onprint) üye işlevi sayfanın gerçek yazdırma gerçekleştirir. Varsayılan [Yazdırma nın Nasıl Yapıldığı](../mfc/how-default-printing-is-done.md) makalesi, çerçevenin yazdırma gerçekleştirmek için bir yazıcı aygıtı bağlamıyla [OnDraw'ı](../mfc/reference/cview-class.md#ondraw) nasıl çağırdığını gösterir. Daha doğrusu, çerçeve `OnPrint` bir `CPrintInfo` yapı ve aygıt `OnPrint` bağlamı ile `OnDraw`çağırır ve aygıt bağlamını . Ekran `OnPrint` ekranı için değil, yalnızca yazdırma sırasında yapılması gereken herhangi bir işleme gerçekleştirmek için geçersiz kılın. Örneğin, üstbilgileri veya altbilgileri yazdırmak için (daha fazla bilgi için makale [Üstbilgileri ve Altbilgi'](../mfc/headers-and-footers.md) ne bakın). Ardından, `OnDraw` hem ekran `OnPrint` ekranında hem de yazdırmada ortak olan işlemeyi yapmak için geçersiz kılmadan arayın.

Hem ekran `OnDraw` ekranı hem de yazdırma için render yapan gerçek, uygulamanızın WYSIWYG olduğu anlamına gelir: "Gördüğünüz şey ne elde ettiğinizdir." Ancak, bir WYSIWYG uygulaması yazmadığınızı varsayalım. Örneğin, yazdırmak için kalın bir yazı tipi kullanan ancak ekranda kalın metni belirtmek için denetim kodlarını görüntüleyen bir metin düzenleyicisi düşünün. Böyle bir durumda, `OnDraw` kesinlikle ekran ekranı için kullanın. Geçersiz kılındığınızda, `OnPrint`aramayı `OnDraw` ayrı bir çizim işlevine bir çağrıyla değiştirin. Bu işlev, ekranda görüntülemediğiniz öznitelikleri kullanarak belgeyi kağıt üzerinde göründüğü şekilde çizer.

## <a name="printer-pages-vs-document-pages"></a><a name="_core_printer_pages_vs.._document_pages"></a>Yazıcı Sayfaları ve Belge Sayfaları

Sayfa numaralarına atıfta bulunduğunuzda, bazen yazıcının sayfa kavramı ile belgenin sayfa kavramı arasında ayrım yapmak gerekir. Yazıcının bakış açısından, bir sayfa bir sayfadır. Ancak, bir sayfa kağıt mutlaka belgenin bir sayfa eşit değildir. Örneğin, sayfaların katlandığı bir haber bülteni yazdırDıysanız, bir sayfa kağıt belgenin ilk ve son sayfalarını yan yana içerebilir. Benzer şekilde, bir elektronik tablo yazdırıyorsanız, belge hiç sayfalardan oluşmaz. Bunun yerine, bir sayfa kağıt satır 1 ile 20, sütun6 ile 10 arasında içerebilir.

[CPrintInfo](../mfc/reference/cprintinfo-structure.md) yapısındaki tüm sayfa numaraları yazıcı sayfalarına başvurur. Çerçeve çağırır `OnPrepareDC` `OnPrint` ve yazıcıdan geçecek her kağıt sayfası için bir kez. Belgenin uzunluğunu belirtmek için [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) işlevini geçersiz kaldığınızzaman, yazıcı sayfalarını kullanmanız gerekir. Bire bir yazışma varsa (diğer bir yazıcı sayfası bir belge sayfasına eşittir), o zaman bu kolaydır. Diğer taraftan, belge sayfaları ve yazıcı sayfaları doğrudan karşılık vermiyorsa, bunlar arasında çeviri yapmanız gerekir. Örneğin, bir elektronik tablo yazdırmayı düşünün. Geçersiz kılınırken, `OnPreparePrinting`tüm elektronik tabloyu yazdırmak için kaç sayfa kağıt gerekeceğini hesaplamanız `SetMaxPage` ve `CPrintInfo`ardından üye işlevini ararken bu değeri kullanmanız gerekir. Benzer şekilde, geçersiz `OnPrepareDC`kılınırken, *m_nCurPage* belirli bir sayfada görünecek satır ve sütun aralığına çevirmeniz ve ardından viewport kaynağını buna göre ayarlamanız gerekir.

## <a name="print-time-pagination"></a><a name="_core_print.2d.time_pagination"></a>Baskı-Zaman Pagination

Bazı durumlarda, görünüm sınıfınız belgenin gerçekte yazdırılana kadar ne kadar süreceğini önceden bilmiyor olabilir. Örneğin, uygulamanızın WYSIWYG olmadığını varsayalım, bu nedenle belgenin ekrandaki uzunluğu yazdırıldığında uzunluğuna karşılık gelmez.

Bu, görünüm sınıfınız için [OnPreparePrinting'i](../mfc/reference/cview-class.md#onprepareprinting) geçersiz kaldığınızzaman soruna `SetMaxPage` neden olur: belgenin uzunluğunu bilmediğiniz için [CPrintInfo](../mfc/reference/cprintinfo-structure.md) yapısının işlevine bir değer geçiremezsiniz. Kullanıcı Yazdır iletişim kutusunu kullanarak durdurmak için bir sayfa numarası belirtmezse, çerçeve yazdırma döngüsünün ne zaman durdurulacağını bilmez. Yazdırma döngüsünün ne zaman durdurululmasını belirlemenin tek yolu belgenin yazdırılması ve ne zaman sona erdirilece Görünüm sınıfınız yazdırılırken belgenin sonunu denetlemeli ve sona ulaşıldığında çerçeveyi bildirmelidir.

Çerçeve, ne zaman dureceğini söylemek için görünüm sınıfınızın [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) işlevine dayanır. Her çağrıdan `OnPrepareDC`sonra, çerçeve *m_bContinuePrinting* `CPrintInfo` adı verilen yapının bir üyesini denetler. Varsayılan değeri **TRUE'dur.** Öyle kaldığı sürece, çerçeve yazdırma döngüsüne devam eder. **FALSE**olarak ayarlanırsa, çerçeve durur. Yazdırma zamanı pagination gerçekleştirmek için, belgenin sonuna ulaşılıp ulaşılmadığını denetlemek için geçersiz kılma `OnPrepareDC` ve gerektiğinde **FALSE** *m_bContinuePrinting* ayarlayın.

Geçerli sayfa `OnPrepareDC` 1'den büyükse, kümelerin varsayılan uygulaması *FALSE'a m_bContinuePrinting.* **FALSE** Bu, belgenin uzunluğu belirtilmemişse, çerçevenin belgenin bir sayfa uzunluğunda olduğunu varsayar anlamına gelir. Bunun bir sonucu, taban sınıf sürümünü çağırırsanız dikkatli `OnPrepareDC`olmalısınız. Taban sınıf sürümünü aradıktan sonra *m_bContinuePrinting* **DOĞRU** olacağını düşünmeyin.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilmek istiyorum

- [Üstbilgiler ve altbilgiler](../mfc/headers-and-footers.md)

- [GDI kaynaklarını ayırma](../mfc/allocating-gdi-resources.md)

## <a name="see-also"></a>Ayrıca bkz.

[Yazdırma](../mfc/printing.md)<br/>
[CView Sınıfı](../mfc/reference/cview-class.md)<br/>
[CDC Sınıfı](../mfc/reference/cdc-class.md)
