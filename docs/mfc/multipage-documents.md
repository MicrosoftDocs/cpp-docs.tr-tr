---
title: Birden fazla belge | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8a7179c74347f3c710f542fb1fc83bb79d2acb38
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43220547"
---
# <a name="multipage-documents"></a>Birden Fazla Belge
Bu makalede Windows yazdırma iletişim kuralı ve birden çok sayfa içeren belgeleri nasıl açıklar. Bu makalede, aşağıdaki konular yer almaktadır:  
  
-   [Yazdırma Protokolü](#_core_the_printing_protocol)  
  
-   [View sınıfı işlevleri geçersiz kılma](#_core_overriding_view_class_functions)  
  
-   [Sayfalandırma](#_core_pagination)  
  
-   [Belge sayfaları ve yazıcı sayfaları](#_core_printer_pages_vs.._document_pages)  
  
-   [Yazdırma zamanı sayfalandırma](#_core_print.2d.time_pagination)  
  
##  <a name="_core_the_printing_protocol"></a> Yazdırma Protokolü  
 Birden çok belge yazdırma için aşağıdaki şekilde Görünüm ve çerçeve etkileşim kurun. İlk framework görüntüler **yazdırma** iletişim kutusu, yazıcı ve aramalar için bir cihaz bağlamı oluşturur [StartDoc](../mfc/reference/cdc-class.md#startdoc) üye işlevinin [CDC](../mfc/reference/cdc-class.md) nesne. Ardından, belge her sayfa için framework çağırır [StartPage](../mfc/reference/cdc-class.md#startpage) üye işlevinin `CDC` nesne, sayfa ve çağrıları'ı yazdırmak için Görünüm nesnesi bildirir [EndPage](../mfc/reference/cdc-class.md#endpage) üye işlevi. Yazıcı modu belirli bir sayfada başlatmadan önce değişmesi gerekip gerekmediğini görünümü çağrıları [ResetDC](../mfc/reference/cdc-class.md#resetdc), hangi güncelleştirmelerin [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) yeni yazıcı modu bilgi içeren yapıya. Tüm belgeyi yazdırılırken framework çağırır [EndDoc](../mfc/reference/cdc-class.md#enddoc) üye işlevi.  
  
##  <a name="_core_overriding_view_class_functions"></a> View sınıfı işlevleri geçersiz kılma  
 [CView](../mfc/reference/cview-class.md) sınıfı framework tarafından yazdırma sırasında çağrılan birçok üye işlevleri tanımlar. Bu işlevler görünümü sınıfınızda geçersiz kılarak, framework'ün yazdırma mantıksal görünümü sınıfınızın yazdırma mantığı arasında bağlantılar sağlar. Aşağıdaki tabloda, bu üye işlevleri listeler.  
  
### <a name="cviews-overridable-functions-for-printing"></a>CView'ın, yazdırma işlemi için geçersiz kılınabilir İşlevler  
  
|Ad|Geçersiz kılma nedeni|  
|----------|---------------------------|  
|[OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)|Yazdırma iletişim kutusunda, özellikle belgenin uzunluğunu değerleri eklemek için|  
|[OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting)|Yazı tipi veya diğer GDI kaynaklarını ayırmak için|  
|[OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc)|Belirtilen sayfa için cihaz bağlamı özniteliklerini ayarlayın ya da yazdırma zamanı sayfalandırma yapmak için|  
|[Yazdırma](../mfc/reference/cview-class.md#onprint)|Belirli bir sayfa yazdırmak için|  
|[OnEndPrinting](../mfc/reference/cview-class.md#onendprinting)|GDI kaynaklarını serbest bırakmak|  
  
 İşleme yazdırma ile ilgili diğer işlevlerde de yapabilirsiniz, ancak bu işlevler, yazdırma işlemi sürücü olanlardır.  
  
 Aşağıdaki şekilde yazdırma işleminde yer alan adımların gösterir ve nereye gösteren her biri `CView`üye işlevleri çağrılır yazdırmak kullanıcının. Bu makalenin geri kalanında adımları daha ayrıntılı bir çoğunu açıklar. Yazdırma işlemi ek bölümlerini makalesinde açıklanan [GDI kaynaklarını ayırma](../mfc/allocating-gdi-resources.md).  
  
 ![Döngü işlem yazdırma](../mfc/media/vc37c71.gif "vc37c71")  
Yazdırma döngü  
  
##  <a name="_core_pagination"></a> Sayfalandırma  
 Framework hemen bir yazdırma işi hakkında bilgileri depolayan bir [Cprintınfo](../mfc/reference/cprintinfo-structure.md) yapısı. Bazı değerlerin `CPrintInfo` için sayfalandırma ilgilidir; bu değerler aşağıdaki tabloda gösterildiği gibi erişilebilir.  
  
### <a name="page-number-information-stored-in-cprintinfo"></a>Cprintınfo içinde depolanan sayfa numarası bilgileri  
  
|Üye değişkeni veya<br /><br /> işlev adları|Başvurulan sayfa numarası|  
|-----------------------------------------------|----------------------------|  
|`GetMinPage`/`SetMinPage`|Belgenin ilk sayfa|  
|`GetMaxPage`/`SetMaxPage`|Belgenin son sayfa|  
|`GetFromPage`|Yazdırılacak ilk sayfa|  
|`GetToPage`|Yazdırılacak son sayfa|  
|`m_nCurPage`|Şu anda yazdırılmasını sayfası|  
  
 Sayfa numaralarını başlangıç 1, diğer bir deyişle, ilk sayfa numaralandırılmıştır 1, 0. Bu ve diğer üyeleri hakkında daha fazla bilgi için [Cprintınfo](../mfc/reference/cprintinfo-structure.md), bkz: *MFC başvurusu*.  
  
 Yazdırma işlemi başlangıcında, görünümün framework çağırır [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) geçen bir işaretçi, üye işlevi bir `CPrintInfo` yapısı. Uygulama Sihirbazı'nı bir uygulamasını sağlar `OnPreparePrinting` çağrılarının [DoPreparePrinting](../mfc/reference/cview-class.md#doprepareprinting), başka bir üye işlevinin `CView`. `DoPreparePrinting` Yazdır iletişim kutusunu görüntüler ve yazıcı cihaz bağlamı oluşturan işlevdir.  
  
 Bu noktada uygulama belgede kaç sayfalarıdır bilmez. Belgenin ilk ve son sayfa sayısı için 1 ile 0xFFFF varsayılan değerleri kullanır. Kaç sayfası, belge olduğunu biliyorsanız, geçersiz kılma `OnPreparePrinting` ve arama [için SetMaxPage]--brokenlink--(reference/cprintinfo-class.md#setmaxpage) `CPrintInfo` için göndermeden önce yapı `DoPreparePrinting`. Bu belgeyi uzunluğunu belirtmenize olanak sağlar.  
  
 `DoPreparePrinting` Daha sonra yazdırma iletişim kutusu görüntüler. Bu geri döndüğünde, `CPrintInfo` yapısı, kullanıcı tarafından belirtilen değerleri içerir. Kullanıcı yalnızca seçili bir dizi sayfa yazdırma isterse isterse başlangıç ve bitiş sayfa numaralarını yazdırma iletişim kutusunda belirtebilirsiniz. Framework kullanarak bu değerleri alır `GetFromPage` ve `GetToPage` işlevlerini [Cprintınfo](../mfc/reference/cprintinfo-structure.md). Kullanıcı bir sayfa aralığı belirtmiyorsa, framework çağırır `GetMinPage` ve `GetMaxPage` ve tüm belgeyi yazdırma için döndürülen değerleri kullanır.  
  
 Yazdırılacak belgenin her sayfa için framework görünümü sınıfınızda, iki üye işlevleri çağırır [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) ve [OnPrint](../mfc/reference/cview-class.md#onprint)ve her işlevin iki parametre geçirir: bir işaretçi bir [ CDC](../mfc/reference/cdc-class.md) nesnesi ve bir işaretçi bir `CPrintInfo` yapısı. Her zaman framework çağrıları `OnPrepareDC` ve `OnPrint`, farklı bir değer geçirir *m_nCurPage* üyesi `CPrintInfo` yapısı. Bu şekilde, hangi sayfa yazdırılıp görünümü framework söyler.  
  
 [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) üye işlevi ekran görüntüsü için de kullanılır. Çizim gerçekleşmeden önce cihaz bağlamı ayarlamalar yapar. `OnPrepareDC` benzer bir rol, yazdırma, hizmet vardır, ancak birkaç farklılıkla: ilk `CDC` nesnesini gösteren bir ekran cihaz bağlamı ve ikinci yerine bir yazıcı cihaz bağlamı bir `CPrintInfo` nesne, ikinci parametre olarak geçirilir. (Bu parametre **NULL** olduğunda `OnPrepareDC` ekran görüntüsü için çağrılır.) Geçersiz kılma `OnPrepareDC` hangi sayfa yazdırılıyor tabanlı cihaz bağlamı ayarlamalar yapmak için. Örneğin, Görünüm penceresi başlangıcı ve uygun kısmını serileştirmeniz yazdırılmaz sağlamak için kırpma bölgesini taşıyabilirsiniz.  
  
 [OnPrint](../mfc/reference/cview-class.md#onprint) sayfanın yazdırma üye işlevini gerçekleştirir. Makaleyi [nasıl varsayılan yazdırma yapılır](../mfc/how-default-printing-is-done.md) Framework'ün çağırması gösterir [OnDraw](../mfc/reference/cview-class.md#ondraw) yazdırma gerçekleştirmek için bir yazıcı cihaz bağlamı ile. Daha kesin framework çağrıları `OnPrint` ile bir `CPrintInfo` yapısı ve bir cihaz bağlamı ve `OnPrint` cihaz bağlamına geçirir `OnDraw`. Geçersiz kılma `OnPrint` yazdırma sırasında yalnızca ve ekran için yapılması herhangi bir işleme gerçekleştirmek için. Örneğin, üstbilgilerinde veya altbilgilerinde yazdırmak için (bkz [üstbilgiler ve altbilgiler](../mfc/headers-and-footers.md) daha fazla bilgi için). Ardından çağırın `OnDraw` geçersiz kılmasını gelen `OnPrint` hem ekran için ortak işleme ve yazdırma.  
  
 Olgu, `OnDraw` hem de görüntüleme ekranı ve yazdırma anlamına gelir, uygulamanızın WYSIWYG olduğunu işleme desteklemez: "ne görüyorsanız onu alırsınız sağlıyor." Ancak, bir WYSIWYG uygulama yazma olmayan varsayalım. Örneğin, bir metin düzenleyicisi yazdırma için kalın yazı tipi kullanan, ancak ekranda kalın metin göstermek için denetim kodlarını görüntüler göz önünde bulundurun. Böyle bir durumda, kullandığınız `OnDraw` kesinlikle için ekran görüntüsü. Ne zaman geçersiz kılmanız `OnPrint`, çağrı yerine `OnDraw` ayrı bir çizim işlevi çağrısı. Bu işlev, ekranda gösterme öznitelikleri kullanarak kağıda görüntülenme şeklini belge çizer.  
  
##  <a name="_core_printer_pages_vs.._document_pages"></a> Yazıcı sayfaları vs. Belge sayfaları  
 Sayfa numaralarını başvurduğunuzda, bazen bir sayfa yazıcının kavramı bir sayfa bir belge kavramı arasında ayrım yapmak gereklidir. Bakış açısıyla yazıcının, bir sayfa sayfadır. Ancak, bir sayfa mutlaka belgenin bir sayfasını eşit değildir. Örneğin, bir sayfa burada sayfalarını Katlanmış üzeresiniz, bülten, yazdırma yapıyorsanız yan yana belge ilk ve son sayfaların içerebilir. Bir elektronik tablo yazdırma benzer şekilde, belge sayfalarının hiç oluşur değil. Bunun yerine, bir sayfa 1 ile 20, 6-10 arası sütunların satır içerebilir.  
  
 İçindeki tüm sayfa sayıları [Cprintınfo](../mfc/reference/cprintinfo-structure.md) yapısı yazıcı sayfalarına bakın. Framework çağrıları `OnPrepareDC` ve `OnPrint` yazıcı geçecek her sayfa için bir kez. Ne zaman geçersiz kılmanız [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) belgenin uzunluğunu belirtmek için işlev, yazıcı sayfaları kullanmanız gerekir. Bire bir ilişkisi varsa (diğer bir deyişle, bir yazıcı sayfa bir belge sayfası eşittir), sonra da bu kolaydır. Öte yandan, belge sayfaları ve yazıcı sayfaları doğrudan karşılık gelmez, aralarında Çevir gerekir. Örneğin, bir elektronik tablo yazdırma göz önünde bulundurun. Geçersiz kılarken `OnPreparePrinting`, kaç kağıda tüm elektronik tablo yazdırma ve ardından bu değeri çağrılırken kullanmak için gerekli olacak karşılaştırılmalıdır `SetMaxPage` üye işlevini `CPrintInfo`. Benzer şekilde, geçersiz kılarken `OnPrepareDC`, çevirme gerekir *m_nCurPage* satır ve sütunları, belirli bir sayfada görüntülenir ve görünüm penceresinin başlangıç'ı uygun şekilde ayarlamanız bir aralıkta birleştirir.  
  
##  <a name="_core_print.2d.time_pagination"></a> Yazdırma zamanı sayfalandırma  
 Bazı durumlarda, görünüm sınıfı önceden gerçekten yazdırıldı kadar ne kadar belgeyi olduğunu bilmeyebilir. Uygulamanızı WYSIWYG değil varsayalım, örneğin, bu nedenle ekranında bir belgenin uzunluğu yazdırıldığında uzunluğuna karşılık gelmiyor.  
  
 Geçersiz kılmanız olduğunda bu soruna neden [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) görünümü sınıfınız için: bir değer geçiremezsiniz `SetMaxPage` işlevi [Cprintınfo](../mfc/reference/cprintinfo-structure.md) uzunluğunu bilmiyor yapısı bir Belge. Yazdır iletişim kutusunu kullanarak durdurmak için bir sayfa numarası kullanıcı belirtmiyorsa, framework ne zaman durdurulacağını yazdırma döngü bilmez. Ne zaman yazdırma döngü durdurulacağını belirlemek için tek yolu, belgeyi yazdırma ve sona erdiğinde bkz sağlamaktır. Görünüm sınıfınız, yazdırılıyor ve sonuna ulaşıldığında framework hakkında bilgilendirmek için belgenin sonuna denetlemeniz gerekir.  
  
 Görünüm sınıfınızın üzerinde framework kullanır [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) bunu bildirmek için işlevi ne zaman durdurulacağını. Her çağrı sonra `OnPrepareDC`, framework üyesi denetler `CPrintInfo` adlı yapısı *m_bContinuePrinting*. Varsayılan değeri **TRUE.** Bunu kaldığı sürece, framework yazdırma döngü devam eder. Bu ayarlanırsa **FALSE**, framework durdurur. Yazdırma zamanı sayfalandırma gerçekleştirmek için geçersiz kılma `OnPrepareDC` belgenin sonuna ulaşıldı ve ayarlandı olup olmadığını denetlemek için *m_bContinuePrinting* için **FALSE** sahip olduğunda.  
  
 Varsayılan uygulaması `OnPrepareDC` ayarlar *m_bContinuePrinting* için **FALSE** geçerli sayfa 1'den büyük olduğunda. Başka bir deyişle, belgenin uzunluğunu belirtilmezse framework belgeyi bir sayfa uzun olduğunu varsayar. Bunun bir sonucu olan temel sınıf sürümü çağırırsanız dikkatli olmalıdır `OnPrepareDC`. Varsaymayın *m_bContinuePrinting* olacaktır **TRUE** temel sınıftaki sürümün çağrıldıktan sonra.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Üstbilgiler ve altbilgiler](../mfc/headers-and-footers.md)  
  
-   [GDI kaynaklarını ayırma](../mfc/allocating-gdi-resources.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yazdırma](../mfc/printing.md)   
 [CView sınıfı](../mfc/reference/cview-class.md)   
 [CDC Sınıfı](../mfc/reference/cdc-class.md)