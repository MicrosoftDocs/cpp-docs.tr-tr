---
title: "Birden çok belge | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 43bc9bbe4653e34c37ae46439baa1e649d6d8042
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="multipage-documents"></a>Birden Fazla Belge
Bu makalede Windows Yazdırma Protokolü açıklar ve birden fazla sayfa içeren belgeleri yazdırma açıklanmaktadır. Makale aşağıdaki konuları içerir:  
  
-   [Yazdırma Protokolü](#_core_the_printing_protocol)  
  
-   [View sınıfı işlevleri geçersiz kılma](#_core_overriding_view_class_functions)  
  
-   [Sayfa numaralandırma](#_core_pagination)  
  
-   [Yazıcı sayfaları belge sayfalarının karşılaştırması](#_core_printer_pages_vs.._document_pages)  
  
-   [Yazdırma zamanı sayfa numaralandırma](#_core_print.2d.time_pagination)  
  
##  <a name="_core_the_printing_protocol"></a>Yazdırma Protokolü  
 Birden çok belge yazdırmak için aşağıdaki şekilde framework ve görünüm etkileşimde bulunur. İlk framework görüntüler **yazdırma** iletişim kutusu, yazıcı ve aramalar için cihaz bağlamı oluşturan [StartDoc](../mfc/reference/cdc-class.md#startdoc) üye işlevini [CDC](../mfc/reference/cdc-class.md) nesnesi. Ardından, belgenin her sayfasında framework çağırması [StartPage](../mfc/reference/cdc-class.md#startpage) üye işlevini `CDC` nesne, sayfa ve çağrıları yazdırmak için Görünüm nesnesi bildirir [EndPage](../mfc/reference/cdc-class.md#endpage) üye işlevi. Yazıcı modu belirli bir sayfayı başlatmadan önce değişmesi gerekip gerekmediğini görünüme çağırır [ResetDC](../mfc/reference/cdc-class.md#resetdc), hangi güncelleştirmelerin [aygıt MODUNDAN](http://msdn.microsoft.com/library/windows/desktop/dd183565) yeni yazıcı modu bilgilerini içeren yapısı. Tüm belgeyi yazdırıldığında framework çağırması [EndDoc](../mfc/reference/cdc-class.md#enddoc) üye işlevi.  
  
##  <a name="_core_overriding_view_class_functions"></a>View sınıfı işlevleri geçersiz kılma  
 [CView](../mfc/reference/cview-class.md) sınıfı, yazdırma sırasında çerçevesi tarafından çağrılır birkaç üye işlevleri tanımlar. Bu işlevler görünüm sınıfınızda kılarak framework'ün yazdırma mantığı ve görünüm sınıfınızın yazdırma mantığı arasında bağlantı sağlar. Aşağıdaki tabloda, bu üye işlevleri listeler.  
  
### <a name="cviews-overridable-functions-for-printing"></a>Yazdırma için CView'ın geçersiz kılınabilir İşlevler  
  
|Ad|Geçersiz kılma nedeni|  
|----------|---------------------------|  
|[OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)|Yazdır iletişim kutusunda, özellikle belgenin uzunluğunu değerleri eklemek için|  
|[OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting)|Yazı tipleri veya diğer GDI kaynaklarını ayırmak için|  
|[OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc)|Belirli bir sayfa için cihaz bağlamı özniteliklerini ayarlayın ya da yazdırma zamanı sayfalandırma yapmak için|  
|[OnPrint](../mfc/reference/cview-class.md#onprint)|Belirli bir sayfa yazdırmak için|  
|[OnEndPrinting](../mfc/reference/cview-class.md#onendprinting)|GDI kaynaklarını kaldırmak için|  
  
 Yazdırma ilgili işleme, diğer işlevlerini de yapabilirsiniz ancak bu işlevler yazdırma işlemi sürücü olanlardır.  
  
 Aşağıdaki şekilde yazdırma işleminde adımlarını gösterir ve nereye gösteren her biri `CView`üye işlevleri çağrılır yazdırma kullanıcının. Bu makalenin geri kalanında daha ayrıntılı adımları çoğunu açıklar. Yazdırma işlemi ek bölümlerini makalesinde açıklanan [GDI kaynaklarını ayırma](../mfc/allocating-gdi-resources.md).  
  
 ![Döngü işlem yazdırma](../mfc/media/vc37c71.gif "vc37c71")  
Yazdırma döngüsü  
  
##  <a name="_core_pagination"></a>Sayfa numaralandırma  
 Framework çok yazdırma işi hakkındaki bilgileri depolayan bir [Cprintınfo](../mfc/reference/cprintinfo-structure.md) yapısı. Birkaç değerler `CPrintInfo` için sayfalandırma ilgilidir; bu değerleri aşağıdaki tabloda gösterildiği gibi erişilebilir.  
  
### <a name="page-number-information-stored-in-cprintinfo"></a>Cprintınfo içinde depolanan sayfa numarası bilgileri  
  
|Üye değişkeni veya<br /><br /> işlev adları|Başvurulan sayfa numarası|  
|-----------------------------------------------|----------------------------|  
|`GetMinPage`/`SetMinPage`|Belgenin ilk sayfası|  
|`GetMaxPage`/`SetMaxPage`|Belgenin son sayfası|  
|`GetFromPage`|Yazdırılacak ilk sayfa|  
|`GetToPage`|Yazdırılacak son sayfayı|  
|`m_nCurPage`|Şu anda yazdırılmasını sayfası|  
  
 Sayfa numaraları başlangıcında 1, diğer bir deyişle, ilk sayfa numaralandırılmıştır 1, 0. Bunlar ve diğer üyeleriyle ilgili daha fazla bilgi için [Cprintınfo](../mfc/reference/cprintinfo-structure.md), bkz: *MFC başvurusu*.  
  
 Yazdırma işleminin başında framework görünümün çağırması [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) gösteren bir işaretçi geçirme üye işlevi bir `CPrintInfo` yapısı. Uygulama Sihirbazı'nı bir uygulamasını sağlar `OnPreparePrinting` çağrısı [DoPreparePrinting](../mfc/reference/cview-class.md#doprepareprinting), başka bir üye işlevini `CView`. `DoPreparePrinting`Yazdır iletişim kutusu görüntüler ve yazıcı cihaz bağlamı oluşturan işlevdir.  
  
 Bu noktada uygulamanın kaç tane sayfalarıdır belgede bilmiyor. Belgenin ilk ve son sayfa sayısı için 1 ile 0xFFFF varsayılan değerleri kullanır. Kaç sayfası belgenizi olduğunu biliyorsanız, geçersiz kılma `OnPreparePrinting` ve arama [SetMaxPage]--brokenlink--(reference/cprintinfo-class.md#setmaxpage) için `CPrintInfo` için göndermeden önce yapısı `DoPreparePrinting`. Belgenizi uzunluk belirtmenize olanak sağlar.  
  
 `DoPreparePrinting`Daha sonra yazdırma iletişim kutusu görüntüler. Döndüğünde, `CPrintInfo` yapısı kullanıcı tarafından belirtilen değerleri içerir. Kullanıcı yalnızca seçilen bir aralığı sayfaların yazdırma isterse çözemiyorsa başlangıç ve bitiş Yazdır iletişim kutusunda sayfa numaraları belirtebilirsiniz. Framework kullanarak bu değerleri alır `GetFromPage` ve `GetToPage` işlevlerini [Cprintınfo](../mfc/reference/cprintinfo-structure.md). Kullanıcı sayfa aralığını belirtmiyorsa, framework çağırması `GetMinPage` ve `GetMaxPage` ve tüm belgeyi yazdırmak için döndürülen değerlerini kullanır.  
  
 Yazdırılacak belgenin her sayfasına framework iki üye işlevleri görünüm sınıfınızda çağırması [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) ve [OnPrint](../mfc/reference/cview-class.md#onprint), her işlev iki parametreleri ve geçirir: bir işaretçi bir [ CDC](../mfc/reference/cdc-class.md) nesne ve bir işaretçi bir `CPrintInfo` yapısı. Her zaman framework çağrıları `OnPrepareDC` ve `OnPrint`, farklı bir değer geçirir `m_nCurPage` üyesi `CPrintInfo` yapısı. Bu şekilde framework görünümü hangi sayfasının yazdırılması bildirir.  
  
 [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) üye işlevi ekran görüntüsü için de kullanılır. Çizim gerçekleşmeden önce cihaz bağlamı ayarlamalar kolaylaştırır. `OnPrepareDC`yazdırma, benzer bir rolü hizmet birkaç farklılıkla ancak: ilk olarak, `CDC` nesnesi ekran cihaz bağlamı ve ikincisi, yerine yazıcı cihaz bağlamı temsil eder bir `CPrintInfo` nesnesi, ikinci parametre olarak geçirilir. (Bu parametre **NULL** zaman `OnPrepareDC` ekran görüntüsü için olarak adlandırılır.) Geçersiz kılma `OnPrepareDC` hangi sayfa yazdırılacağı üzerinde tabanlı cihaz bağlamı ayarlamalar yapmak için. Örneğin, Görünüm penceresi kaynak ve belgenin uygun bölümünü yazdırılan sağlamak için kırpma bölgesinin taşıyabilirsiniz.  
  
 [OnPrint](../mfc/reference/cview-class.md#onprint) üye işlevi sayfanın gerçek yazdırma gerçekleştirir. Makaleyi [nasıl varsayılan yazdırma yapılır](../mfc/how-default-printing-is-done.md) framework çağırması gösterir [OnDraw](../mfc/reference/cview-class.md#ondraw) yazdırma gerçekleştirmek için bir yazıcı cihaz bağlamına sahip. Daha hassas bir şekilde framework çağrıları `OnPrint` ile bir `CPrintInfo` yapısı ve cihaz bağlamı ve `OnPrint` cihaz bağlamına geçirir `OnDraw`. Geçersiz kılma `OnPrint` yazdırma sırasında yalnızca ve ekran görüntüsü için yapılması herhangi bir işleme gerçekleştirmek için. Örneğin, üstbilgiler ve altbilgiler yazdırmak için (makalesine bakın [üstbilgiler ve altbilgiler](../mfc/headers-and-footers.md) daha fazla bilgi için). ' I çağırın `OnDraw` geçersiz kılma gelen `OnPrint` hem ekran görüntüsüne ortak işleme ve yazdırma yapmak için.  
  
 Olgu, `OnDraw` her ikisi de görüntü ekran ve yazdırma anlamına gelir, uygulamanızın WYSIWYG olduğunu işleme desteklemez: "ne görüyorsanız aldığınızdır." Ancak, WYSIWYG uygulaması yazma olmayan varsayalım. Örneğin, bir metin Düzenleyicisi'yazdırmak için kalın yazı tipiyle kullanan, ancak ekranda kalın metin göstermek için denetim kodları görüntüler göz önünde bulundurun. Böyle bir durumda, kullandığınız `OnDraw` kesinlikle için ekran görüntüsü. Kıldığınızda `OnPrint`, çağrısı yerine `OnDraw` ayrı bir çizim işlevi çağrısı ile. Bu işlev belge ekranda gösterme özniteliklerini kullanarak kağıda göründüğü şekilde çizer.  
  
##  <a name="_core_printer_pages_vs.._document_pages"></a>Yazıcı sayfaları vs. Belge sayfası  
 Sayfa numaralarına başvurduğunuzda, bazen bir sayfa yazıcının kavramı bir sayfa belgenin kavramı arasında ayrım yapmak gereklidir. Açısından bakıldığında yazıcının, bir yaprak kağıda sayfadır. Ancak, bir yaprak kağıda mutlaka belgenin bir sayfa eşit değil. Örneğin, bir yaprak kağıda sayfaları katlanmış için nerede, bülten, yazdırma yapıyorsanız yan yana belgenin ilk ve son sayfalarınızın içerebilir. Elektronik yazdırma yapıyorsanız, benzer şekilde, belge sayfalarının hiç öğesiyse değil. Bunun yerine, bir yaprak kağıda satırları 1 ila 20, 6-10 arası sütunları içerebilir.  
  
 Tüm sayfa numaraları [Cprintınfo](../mfc/reference/cprintinfo-structure.md) yapısı yazıcı sayfalarına bakın. Framework çağrıları `OnPrepareDC` ve `OnPrint` üzerinden yazıcıyı geçireceği her sayfa için bir kez. Kıldığınızda [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) belgenin uzunluğunu belirtmek için işlev, yazıcı sayfaları kullanmanız gerekir. Bir bire ise (diğer bir deyişle, bir belge sayfası bir yazıcı sayfası eşittir), bu kolay olur. Diğer taraftan, belge sayfalarını ve yazıcı sayfaları doğrudan karşılık gelmeyen varsa, aralarında Çevir gerekir. Örneğin, elektronik tablo yazdırma göz önünde bulundurun. Geçersiz kılarken `OnPreparePrinting`, kaç tane kağıda tüm elektronik tabloyu yazdırma ve sonra bu değeri çağrılırken kullanmak için gerekli olacak hesaplamak gerekir `SetMaxPage` üye işlevini `CPrintInfo`. Benzer şekilde, geçersiz kılarken `OnPrepareDC`, çevir gerekir `m_nCurPage` belirli bu sayfada görüntülenir ve görünüm penceresinin başlangıç buna göre satır ve sütun aralığı içinde.  
  
##  <a name="_core_print.2d.time_pagination"></a>Yazdırma zamanı sayfa numaralandırma  
 Bazı durumlarda, görünüm sınıfınız önceden gerçekte bastırıldı kadar belgeyi ne kadar olacağını bilemeyebilirsiniz. Uygulamanızı WYSIWYG değil varsayalım Örneğin, bu nedenle belgenin uzunluğu ekranında yazdırıldığında uzunluğuna karşılık gelmiyor.  
  
 Geçersiz olduğunda bu soruna neden [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) görünüm sınıfınız için: bir değere geçiremezsiniz `SetMaxPage` işlevi [Cprintınfo](../mfc/reference/cprintinfo-structure.md) yapısı uzunluğu tanımadığınız çünkü bir Belge. Yazdır iletişim kutusunu kullanarak durdurmak için bir sayfa numarası kullanıcı belirtmiyorsa, framework yazdırma döngü durdurmak ne zaman bilmiyor. Yazdırma döngü durdurmak ne zaman belirlemek için yalnızca belgeyi yazdırmak ve sona erdiğinde görmek için yoludur. Yazdırılacağı ve sonuna gelindiğinde framework bildirmek görünüm sınıfı belgenin sonuna için denetlemeniz gerekir.  
  
 Çerçeve görünüm sınıfınızın üzerinde dayanır [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) bunu bildirmek için işlevi zaman durdurmak. Her çağrı sonra `OnPrepareDC`, üyesi framework denetler `CPrintInfo` adlı yapısı `m_bContinuePrinting`. Varsayılan değeri olduğu **TRUE.** Bunu kaldığı sürece framework yazdırma döngü devam eder. Bu ayarlanırsa **yanlış**, framework durdurur. Yazdırma zamanı sayfalandırma gerçekleştirmek için geçersiz kılma `OnPrepareDC` belgenin sonuna ulaşıldı ve ayarlandı olup olmadığını denetlemek için `m_bContinuePrinting` için **FALSE** sahip olduğunda.  
  
 Varsayılan uygulaması `OnPrepareDC` ayarlar `m_bContinuePrinting` için **yanlış** geçerli sayfa 1'den büyük olduğunda. Bu belgenin uzunluğunu belirtilmezse framework belgeyi bir sayfa uzun olduğunu varsayar anlamına gelir. Bunun bir sonucu olduğundan temel sınıf sürümü çağırırsanız dikkatli olmalıdır `OnPrepareDC`. Varsayımında değil `m_bContinuePrinting` olacaktır **TRUE** temel sınıf sürüm çağrıldıktan sonra.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Üstbilgiler ve altbilgiler](../mfc/headers-and-footers.md)  
  
-   [GDI kaynaklarını ayırma](../mfc/allocating-gdi-resources.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yazdırma](../mfc/printing.md)   
 [CView sınıfı](../mfc/reference/cview-class.md)   
 [CDC Sınıfı](../mfc/reference/cdc-class.md)