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
ms.openlocfilehash: 7ef4267c311c1de516f75c3b54677adfbfaba5c9
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916433"
---
# <a name="multipage-documents"></a>Birden Fazla Belge

Bu makalede Windows Yazdırma Protokolü açıklanmakta ve birden fazla sayfa içeren belgelerin nasıl yazdırılacağı açıklanmaktadır. Makalede aşağıdaki konular ele alınmaktadır:

- [Yazdırma Protokolü](#_core_the_printing_protocol)

- [Görünüm sınıfı işlevlerini geçersiz kılma](#_core_overriding_view_class_functions)

- [Mayı](#_core_pagination)

- [Yazıcı sayfaları ve belge sayfaları karşılaştırması](#_core_printer_pages_vs.._document_pages)

- [Yazdırma zamanı sayfalandırma](#_core_print.2d.time_pagination)

##  <a name="_core_the_printing_protocol"></a>Yazdırma Protokolü

Çok sayfalı bir belgeyi yazdırmak için çerçeve ve Görünüm aşağıdaki şekilde etkileşime geçin. İlk çerçeve **Yazdır** iletişim kutusunu görüntüler, yazıcı için bir cihaz bağlamı oluşturur ve [CDC](../mfc/reference/cdc-class.md) nesnesinin [StartDoc](../mfc/reference/cdc-class.md#startdoc) üye işlevini çağırır. Ardından, belgenin her sayfası için çerçeve `CDC` nesnenin [StartPage](../mfc/reference/cdc-class.md#startpage) üye işlevini çağırır, görünüm nesnesine sayfayı yazdırmasını söyler ve [EndPage](../mfc/reference/cdc-class.md#endpage) üye işlevini çağırır. Yazıcı modunun belirli bir sayfa başlatılmadan önce değiştirilmesi gerekiyorsa, görünüm, yeni yazıcı modu bilgilerini içeren [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) yapısını güncelleştiren [ResetDC](../mfc/reference/cdc-class.md#resetdc)'yi çağırır. Belgenin tamamı yazdırıldığında, çerçeve [EndDoc](../mfc/reference/cdc-class.md#enddoc) üye işlevini çağırır.

##  <a name="_core_overriding_view_class_functions"></a>Görünüm sınıfı Işlevlerini geçersiz kılma

[CView](../mfc/reference/cview-class.md) sınıfı, yazdırma sırasında çerçeve tarafından çağrılan çeşitli üye işlevlerini tanımlar. Görünüm sınıfınızdaki bu işlevleri geçersiz kılarak, Framework 'ün yazdırma mantığı ve Görünüm sınıfınızın yazdırma mantığı arasındaki bağlantıları sağlarsınız. Aşağıdaki tabloda bu üye işlevleri listelenmektedir.

### <a name="cviews-overridable-functions-for-printing"></a>CView 'in yazdırma için geçersiz kılınabilir Işlevleri

|Ad|Geçersiz kılma nedeni|
|----------|---------------------------|
|[OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)|Yazdır iletişim kutusuna değerler eklemek için, özellikle belgenin uzunluğu|
|[OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting)|Yazı tiplerini veya diğer GDI kaynaklarını ayırmak için|
|[OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc)|Belirli bir sayfa için cihaz bağlamının özniteliklerini ayarlamak veya yazdırma zamanı sayfalandırmayı yapmak için|
|[Yazdırma](../mfc/reference/cview-class.md#onprint)|Belirli bir sayfayı yazdırmak için|
|[OnEndPrinting](../mfc/reference/cview-class.md#onendprinting)|GDI kaynaklarını serbest bırakmak için|

Yazdırma ile ilgili işlemeyi diğer işlevlerde da yapabilirsiniz, ancak bu işlevler yazdırma sürecini belirten alanlardır.

Aşağıdaki şekilde, yazdırma işleminde yer alan adımlar gösterilmektedir ve her `CView`birinin yazdırma üyesi işlevlerinin nerede çağrıldığını gösterir. Bu makalenin geri kalanında bu adımların çoğu daha ayrıntılı olarak açıklanmaktadır. Yazdırma sürecinin ek bölümleri, [GDI kaynaklarını ayırma](../mfc/allocating-gdi-resources.md)makalesinde açıklanmaktadır.

![Döngü Işlemi yazdırılıyor](../mfc/media/vc37c71.gif "Döngü Işlemi yazdırılıyor") <br/>
Yazdırma döngüsü

##  <a name="_core_pagination"></a>Mayı

Framework bir [CPrintInfo](../mfc/reference/cprintinfo-structure.md) yapısında bir yazdırma işi hakkındaki bilgilerin çoğunu depolar. İçindeki `CPrintInfo` bazı değerler Sayfalandırmaya aittir; bu değerler aşağıdaki tabloda gösterildiği gibi erişilebilir.

### <a name="page-number-information-stored-in-cprintinfo"></a>CPrintInfo 'da depolanan sayfa numarası bilgileri

|Üye değişkeni veya<br /><br /> işlev adı (ler)|Başvurulan sayfa numarası|
|-----------------------------------------------|----------------------------|
|`GetMinPage`/`SetMinPage`|Belgenin ilk sayfası|
|`GetMaxPage`/`SetMaxPage`|Belgenin son sayfası|
|`GetFromPage`|Yazdırılacak ilk sayfa|
|`GetToPage`|Yazdırılacak son sayfa|
|`m_nCurPage`|Sayfa Şu anda yazdırılıyor|

Sayfa numaraları 1 ' den başlar, diğer bir deyişle, ilk sayfa 0 değil 1 numaralandırılır. Bu ve diğer [CPrintInfo](../mfc/reference/cprintinfo-structure.md)üyeleri hakkında daha fazla bilgi için bkz. *MFC başvurusu*.

Yazdırma işleminin başlangıcında çerçeve, görünümün [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) üye işlevini çağırır ve bir `CPrintInfo` yapıya işaretçi geçirmektir. Uygulama Sihirbazı, `OnPreparePrinting` `CView`diğer bir üye işlevi olan [DoPreparePrinting](../mfc/reference/cview-class.md#doprepareprinting)çağrısı yapan bir uygulaması sağlar. `DoPreparePrinting`, Yazdır iletişim kutusunu görüntüleyen ve bir yazıcı cihaz bağlamı oluşturan işlevdir.

Bu noktada, uygulama belgede kaç sayfa olduğunu bilmez. Belgenin ilk ve son sayfasının sayıları için 1 ve 0xFFFF varsayılan değerlerini kullanır. Belgenizin kaç sayfa olduğunu biliyorsanız, ' a göndermeden `OnPreparePrinting` `DoPreparePrinting`önce `CPrintInfo` yapı için [SetMaxPage]--brokenlınk--(Reference/CPrintInfo-Class. MD # SetMaxPage) öğesini geçersiz kılın ve çağırın. Bu, belgenizin uzunluğunu belirtmenizi sağlar.

`DoPreparePrinting`ardından Yazdır iletişim kutusunu görüntüler. Döndüğünde, `CPrintInfo` yapı Kullanıcı tarafından belirtilen değerleri içerir. Kullanıcı yalnızca seçili bir sayfa aralığını yazdırmaya istiyorsa, Yazdır iletişim kutusunda başlangıç ve bitiş sayfa numaralarını belirtebilir. Framework, `GetFromPage` [CPrintInfo](../mfc/reference/cprintinfo-structure.md)'ın ve `GetToPage` işlevlerini kullanarak bu değerleri alır. Kullanıcı bir sayfa aralığı belirtmezse, çerçeve tüm belgeyi yazdırmak için `GetMinPage` döndürülen `GetMaxPage` değerleri çağırır ve kullanır.

Bir belgenin yazdırılacağı her sayfasında çerçeve, görünüm sınıfınıza ait iki üye işlevini çağırarak, [Onhazırlık EDC](../mfc/reference/cview-class.md#onpreparedc) ve [OnPrint](../mfc/reference/cview-class.md#onprint)ve her bir `CPrintInfo` Işlevi iki parametre olarak geçirir: bir [CDC](../mfc/reference/cdc-class.md) nesnesine ve bir işaretçisine bir işaretçiye yapısı. `OnPrepareDC` Framework ve `OnPrint`her çağırdığında, `CPrintInfo` yapının *m_nCurPage* üyesine farklı bir değer geçirir. Bu şekilde Framework, görüntülenecek sayfanın yazdırılması gerektiğini gösterir.

[Onhazırlık EDC](../mfc/reference/cview-class.md#onpreparedc) üye işlevi ekran görüntüleme için de kullanılır. Çizim gerçekleşmeden önce cihaz bağlamında ayarlamalar yapar. `OnPrepareDC`yazdırırken benzer bir rol sunar, ancak birkaç fark vardır: ilk, `CDC` nesne bir ekran cihaz bağlamı yerine bir yazıcı cihaz bağlamını temsil eder ve ikinci olarak bir `CPrintInfo` nesne ikinci bir parametre olarak geçirilir. (Bu parametre, ekran görüntüleme `OnPrepareDC` için çağrıldığında null olur.) Cihaz `OnPrepareDC` bağlamına hangi sayfanın yazdırıldığını belirleyen ayarlamalar yapmak için geçersiz kılın. Örneğin, belgenin uygun kısmının yazdırılmasını sağlamak için görünüm kutusu başlangıcını ve kırpma bölgesini taşıyabilirsiniz.

[OnPrint](../mfc/reference/cview-class.md#onprint) üye işlevi, sayfanın gerçek yazdırma işlemini gerçekleştirir. [Varsayılan yazdırma](../mfc/how-default-printing-is-done.md) işlemi, çerçevenin yazdırma işlemini gerçekleştirmek için bir yazıcı cihaz bağlamı Ile [OnDraw](../mfc/reference/cview-class.md#ondraw) 'ın nasıl çağırılamadığını gösterir. Daha kesin olarak, Framework bir `OnPrint` `CPrintInfo` yapıyla ve bir cihaz içeriğiyle çağrı yapar ve `OnPrint` cihaz bağlamını ' ye `OnDraw`geçirir. Yalnızca `OnPrint` yazdırma sırasında yapılması gereken, ekran görüntüsü için değil, herhangi bir işlemeyi gerçekleştirmek için geçersiz kılın. Örneğin, üst bilgileri veya altbilgileri yazdırmak için (daha fazla bilgi için bkz. [başlıklar ve altbilgiler](../mfc/headers-and-footers.md) makalesine bakın). Sonra, `OnDraw` oluşturma işlemini hem ekran `OnPrint` görüntüleme hem de yazdırma için ortak yapmak için geçersiz kılmada çağırın.

Hem ekran görüntüleme `OnDraw` hem de yazdırma için işleme yapan olgu, uygulamanızın WYSIWYG olduğu anlamına gelir: "Gördükleriniz." Ancak, bir WYSıWYG uygulaması yazmadığınızı varsayalım. Örneğin, yazdırma için kalın yazı tipi kullanan bir metin düzenleyicisini düşünün ancak ekranda kalın metin göstermek için denetim kodlarını görüntüler. Böyle bir durumda, kesinlikle ekran görüntüsü `OnDraw` için kullanırsınız. Geçersiz kıldığınızda `OnPrint`, `OnDraw` çağrısını ayrı bir çizim işlevine çağrısıyla değiştirin. Bu işlev, ekranda görüntülenmeyin öznitelikleri kullanarak belgeyi kağıda göründüğü şekilde çizer.

##  <a name="_core_printer_pages_vs.._document_pages"></a>Yazıcı sayfaları ile Belge sayfaları

Sayfa numaralarına başvurduğunuzda, bazen yazıcının bir sayfa kavramı ve bir belgenin kavramı arasında ayrım yapmak gerekir. Yazıcının görünüm noktasından bir sayfa bir kağıt yaprabiridir. Ancak, bir kağıt yaprağının belgenin bir sayfasına eşit olması gerekmez. Örneğin, sayfaların katlanmakta olduğu bir Bülteni yazdırıyorsanız, tek bir kağıda belgenin her ikisi ve son sayfaları, yan yana olabilir. Benzer şekilde, bir elektronik tablo yazdırıyorsanız belge, hiç sayfadan oluşamaz. Bunun yerine, bir kağıda bir kağıt 1 ile 20 arasındaki sütunlar, 6 ile 10 arasında bir sayfa içerebilir.

[CPrintInfo](../mfc/reference/cprintinfo-structure.md) yapısındaki tüm sayfa numaraları yazıcı sayfalarına başvurur. Çerçeve, yazıcıdan `OnPrepareDC` geçirilecek `OnPrint` her bir kağıt sayfası için ve bir kez çağırır. Belge uzunluğunu belirtmek için [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) işlevini geçersiz kıldığınızda, yazıcı sayfalarını kullanmanız gerekir. Bire bir yazışmalar varsa (yani, bir yazıcı sayfası bir belge sayfasına eşitse), bu oldukça kolaydır. Diğer taraftan, belge sayfaları ve yazıcı sayfaları doğrudan karşılık gelmiyorsa, aralarında çeviri yapmanız gerekir. Örneğin, bir elektronik tablo yazdırmayı göz önünde bulundurun. Geçersiz kıldığınızda `OnPreparePrinting`, tüm elektronik tabloyu yazdırmak için kaç yaprak kağıt gerektiğini hesaplamanız ve sonra `SetMaxPage` üye işlevini `CPrintInfo`çağırırken bu değeri kullanmanız gerekir. Benzer şekilde, geçersiz `OnPrepareDC`kılma sırasında, *m_nCurPage* , söz konusu sayfada görünecek olan satır ve sütun aralığına çevirmeniz ve sonra Görünüm kaynağını uygun şekilde ayarlamanız gerekir.

##  <a name="_core_print.2d.time_pagination"></a>Yazdırma zamanı sayfalandırma

Bazı durumlarda, görünüm sınıfınız belgenin gerçekten yazdırılana kadar ne kadar sürdüğünü önceden bilmiyor olabilir. Örneğin, uygulamanızın WYSıWYG olmadığını varsayalım, bu yüzden bir belgenin uzunluğu, yazdırıldığında bu uzunluğa karşılık gelmez.

Bu, görünüm sınıfınız için [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) 'i geçersiz kıldığınızda bir soruna neden olur: bir belgenin uzunluğunu bilmiyorsanız `SetMaxPage` [CPrintInfo](../mfc/reference/cprintinfo-structure.md) yapısının işlevine bir değer geçirilemez. Kullanıcı Yazdır iletişim kutusunu kullanırken durdurulacak bir sayfa numarası belirtmezse, çerçeve, yazdırma döngüsünün ne zaman durdurulacağını bilmez. Yazdırma döngüsünün ne zaman durdurulacağını belirlemenin tek yolu belgeyi yazdırmaktır ve ne zaman sona ereceğini görür. Görünüm sınıfınızın belge yazdırılırken belgenin sonunu denetlemesi ve sonra da sona ulaşıldığında çerçeveyi bilgilendirmeniz gerekir.

Framework, ne zaman durdurulacağını anlatmak için Görünüm sınıfınızın [Onhazırlık EDC](../mfc/reference/cview-class.md#onpreparedc) işlevini kullanır. Her çağrısından `OnPrepareDC`sonra Framework, *m_bContinuePrinting*adlı `CPrintInfo` yapının bir üyesini denetler. Varsayılan değeri true 'dur **.** Bu şekilde kaldığı sürece çerçeve, yazdırma döngüsüne devam eder. **Yanlış**olarak ayarlanırsa, çerçeve duraklar. Yazdırma zamanı sayfalandırmayı gerçekleştirmek için, belgenin `OnPrepareDC` sonuna ulaşılıp ulaşılmadığını denetlemek için geçersiz kılın ve olduğunda *m_bContinuePrinting* **değerini false** olarak ayarlayın.

Geçerli sayfa 1 ' `OnPrepareDC` den büyükse, *m_bContinuePrinting* varsayılan uygulamasını **false** olarak ayarlar. Bu, belgenin uzunluğu belirtilmemişse, çerçevenin belgenin bir sayfa uzunluğunda olduğunu varsaydığı anlamına gelir. Bunun bir sonucu, temel sınıf sürümünü `OnPrepareDC`çağırdığınızda dikkatli olmanız gerekir. Temel sınıf sürümünü çağırdıktan sonra *M_bContinuePrinting* **true** olacağını varsaymayın.

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Üst bilgiler ve altbilgiler](../mfc/headers-and-footers.md)

- [GDI kaynaklarını ayırma](../mfc/allocating-gdi-resources.md)

## <a name="see-also"></a>Ayrıca bkz.

[Yazdırma](../mfc/printing.md)<br/>
[CView Sınıfı](../mfc/reference/cview-class.md)<br/>
[CDC Sınıfı](../mfc/reference/cdc-class.md)
