---
title: "Özellik sayfası (ATL) uygulama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: property pages, implementing
ms.assetid: c30b67fe-ce08-4249-ae29-f3060fa8d61e
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 04f2871af749091e97ec1731650f998739995781
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="example-implementing-a-property-page"></a>Örnek: bir özellik sayfası uygulama
Bu örnek özelliklerini görüntüler (ve değiştirmenize izin verir) özellik sayfası oluşturma gösterir [belge sınıfları](../mfc/document-classes.md) arabirimi.  
  
 Örnek dayanır [ATLPages örnek](../visual-cpp-samples.md).  
  
 Bu örnek tamamlamak için şunları yapacaksınız:  
  
- [ATL özellik sayfası sınıfı ekleme](#vcconusing_the_atl_object_wizard) Sınıf Ekle iletişim kutusu ve ATL Özellik Sayfası Sihirbazı'nı kullanarak.  
  
- [İletişim kaynağını düzenleme](#vcconediting_the_dialog_resource) ilginç özelliklerine yönelik yeni denetimler ekleyerek **belge** arabirimi.  
  
- [İleti işleyicileri ekleme](#vcconadding_message_handlers) özellik sayfası sitesi tutmak için kullanıcı tarafından yapılan değişikliklerin bilgilendirildi.  
  
-   Bazı eklemek `#import` deyimleri ve bir typedef [temizlik](#vcconhousekeeping) bölümü.  
  
- [IPropertyPageImpl::SetObjects geçersiz kılma](#vcconoverriding_ipropertypageimpl_setobjects) özellik sayfası geçirilen nesneleri doğrulanacak.  
  
- [IPropertyPageImpl::Activate geçersiz kılma](#vcconoverriding_ipropertypageimpl_activate) özelliği sayfanın arabirimi başlatılamıyor.  
  
- [IPropertyPageImpl::Apply geçersiz kılma](#vcconoverride_ipropertypageimpl_apply) son özellik değerleriyle Nesne güncelleştirilemedi.  
  
- [Özellik sayfasını görüntülemek](#vccontesting_the_property_page) basit yardımcı nesnesi oluşturarak.  
  
- [Makro oluşturma](#vcconcreating_a_macro) özellik sayfası test.  
  
##  <a name="vcconusing_the_atl_object_wizard"></a>ATL özellik sayfası sınıfı ekleme  
 İlk olarak, adlı bir DLL sunucusu için yeni bir ATL projesi oluşturma `ATLPages7`. Şimdi kullanmak [ATL Özellik Sayfası Sihirbazı](../atl/reference/atl-property-page-wizard.md) özellik sayfası oluşturulamadı. Özellik sayfası vermek bir **kısa ad** , **DocProperties** için geçiş **dizeleri** sayfa özellik sayfası özel öğeleri aşağıdaki tabloda gösterilen şekilde ayarlayın.  
  
|Öğe|Değer|  
|----------|-----------|  
|Başlık|TextDocument|  
|Belge dize|VCUE TextDocument özellikleri|  
|HelpFile|*\<Boş >*|  
  
 Sihirbazın bu sayfasında belirlediğiniz değerler çağırdığında özellik sayfası kapsayıcıya döndürülür **IPropertyPage::GetPageInfo**. Kapsayıcıda bağlıdır, ancak genellikle bunlar kullanıcı sayfanıza tanımlamak için kullanılacak sonra ne dizelere olur. Başlık genellikle sayfanızı yukarıda bir sekmede görünür ve (standart özellik çerçeve bu dizeyi hiç kullanmayan rağmen) belge dize durum çubuğu veya araç ipucu görüntülenebilir.  
  
> [!NOTE]
>  Burada ayarladığınız dizeleri varsayılan olarak, sihirbaz tarafından dize kaynaklarını projenize olarak depolanır. Sayfanızın kod oluşturulduktan sonra bu bilgileri değiştirmeniz gerekirse, Kaynak Düzenleyicisi'ni kullanarak bu dizeler kolayca düzenleyebilirsiniz.  
  
 Tıklatın **Tamam** özellik sayfası oluşturma Sihirbazı'nı sağlamak için.  
  
##  <a name="vcconediting_the_dialog_resource"></a>İletişim kaynağını düzenleme  
 Özellik sayfası oluşturulan, birkaç denetimleri sayfanızı temsil eden iletişim kutusu kaynağı eklemeniz gerekir. Düzenleme kutusu, statik metin denetimi ve onay kutusu ekleyin ve kimlikleri aşağıda gösterildiği gibi ayarlayın:  
  
 ![Bir iletişim kutusu kaynağı düzenleme](../atl/media/ppgresourcelabeled.gif "ppgresourcelabeled")  
  
 Bu denetimler, dosya adı belgenin ve salt okunur durumunu görüntülemek için kullanılır.  
  
> [!NOTE]
>  İletişim kaynağını çerçeve veya komut düğmesi içermez ve beklenen sekmeli görünüm yok. Bu özellikler çağrılarak oluşturulan gibi bir özellik sayfası çerçevesi tarafından sağlanan [OleCreatePropertyFrame](http://msdn.microsoft.com/library/windows/desktop/ms678437).  
  
##  <a name="vcconadding_message_handlers"></a>İleti işleyicileri ekleme  
 Kontroller varken, denetimleri birini değeri değiştiğinde sayfa kirli durumunu güncelleştirmek için ileti işleyicileri ekleyebilirsiniz:  
  
 [!code-cpp[NVC_ATL_Windowing#73](../atl/codesnippet/cpp/example-implementing-a-property-page_1.h)]  
  
 Bu kod düzenleme denetimi veya onay kutusunu çağırarak yapılan değişiklikler yanıtlar [IPropertyPageImpl::SetDirty](../atl/reference/ipropertypageimpl-class.md#setdirty), SAYA değişmiş sayfa site sizi bilgilendirir. Sayfa site etkinleştirme veya devre dışı bırakarak genellikle yanıtlar bir **Uygula** özellik sayfası çerçeve düğmesinde.  
  
> [!NOTE]
>  Kendi özellik sayfalarında değiştirilmemiş olması özelliklerini güncelleştirme engellemek için tam olarak hangi özelliklerin kullanıcı tarafından değiştirilmiş izlemek gerekebilir. Bu örnek kod, özgün özellik değerlerini izlemek ve değişiklikleri uygulamak için zamanı geldiğinde UI geçerli değerlerle bunları karşılaştırma uygular.  
  
##  <a name="vcconhousekeeping"></a>Kayıt tutma  
 Şimdi birkaç ekleyin `#import` DocProperties.h deyimlerini böylece derleyici bildiği **belge** arabirimi:  
  
 [!code-cpp[NVC_ATL_Windowing#74](../atl/codesnippet/cpp/example-implementing-a-property-page_2.h)]  
  
 Başvurmak gerekecektir `IPropertyPageImpl` temel sınıfı; şu ekleyin `typedef` için **CDocProperties** sınıfı:  
  
 [!code-cpp[NVC_ATL_Windowing#75](../atl/codesnippet/cpp/example-implementing-a-property-page_3.h)]  
  
##  <a name="vcconoverriding_ipropertypageimpl_setobjects"></a>IPropertyPageImpl::SetObjects geçersiz kılma  
 İlk `IPropertyPageImpl` geçersiz kılmak için gereken yöntemdir [SetObjects](../atl/reference/ipropertypageimpl-class.md#setobjects). Burada yalnızca tek bir nesne geçirildi ve desteklediğinden emin denetlemek için kod ekleyeceksiniz **belge** beklediğiniz arabirimi:  
  
 [!code-cpp[NVC_ATL_Windowing#76](../atl/codesnippet/cpp/example-implementing-a-property-page_4.h)]  
  
> [!NOTE]
>  Nesnesinin dosya adını ayarlamak kullanıcının izin verecektir olduğundan yalnızca tek bir nesne için bu sayfayı desteklemek için mantıklıdır — tek bir dosya, herhangi bir konumda bulunabilir.  
  
##  <a name="vcconoverriding_ipropertypageimpl_activate"></a>IPropertyPageImpl::Activate geçersiz kılma  
 Sonraki sayfanın ilk oluşturulduğunda, temel alınan nesnenin özellik değerleriyle özellik sayfasını başlatmak için adımdır.  
  
 Bu durumda sayfası kullanıcıları yaptıkları değişiklikleri uyguladığınızda karşılaştırma için başlangıç özellik değerlerini de kullanacağınız beri sınıfına aşağıdaki üyeleri eklemeniz gerekir:  
  
 [!code-cpp[NVC_ATL_Windowing#77](../atl/codesnippet/cpp/example-implementing-a-property-page_5.h)]  
  
 Temel sınıf uygulamasını [etkinleştirme](../atl/reference/ipropertypageimpl-class.md#activate) yöntemi bu yöntemi geçersiz kılın ve temel sınıfı çağrıldıktan sonra kendi başlatma Ekle iletişim kutusu ve onun denetimler oluşturmaktan sorumlu:  
  
 [!code-cpp[NVC_ATL_Windowing#78](../atl/codesnippet/cpp/example-implementing-a-property-page_6.h)]  
  
 Bu kodu COM yöntemlerini kullanan **belge** ilgilendiğiniz özellikleri almak için arabirim. Daha sonra tarafından sağlanan Win32 API sarmalayıcıları kullanır [Cdialogımpl](../atl/reference/cdialogimpl-class.md) ve kullanıcıya özellik değerlerini görüntülemek için taban sınıflarından.  
  
##  <a name="vcconoverride_ipropertypageimpl_apply"></a>IPropertyPageImpl::Apply geçersiz kılma  
 Kullanıcıların yaptıkları değişiklikleri nesnelerine uygulamak istediğiniz zaman, özellik sayfasında site çağıracak [Uygula](../atl/reference/ipropertypageimpl-class.md#apply) yöntemi. Bu kodda ters yapmak için yerdir **etkinleştirme** — ancak **etkinleştir** nesnedeki değerleri sürdü ve bunları özellik sayfasında denetimlere gönderilen **Uygula** özellik sayfasında denetimlerinden değerleri alır ve bunları nesnesine iter.  
  
 [!code-cpp[NVC_ATL_Windowing#79](../atl/codesnippet/cpp/example-implementing-a-property-page_7.h)]  
  
> [!NOTE]
>  Onay karşı [m_bDirty](../atl/reference/ipropertypageimpl-class.md#m_bdirty) bu uygulama, nesnelerin gereksiz güncelleştirmeleri önlemek için bir başlangıç onay başındadır **Uygula** birden çok kez çağrılır. Ayrıca her bir yöntem çağrısı yalnızca değişiklikler neden olmak için özellik değerlerinin karşı denetimi yoktur **belge**.  
  
> [!NOTE]
> **Belge** sunan **FullName** salt okunur bir özellik olarak. Özellik sayfası yapılan değişikliklere göre belgenin dosya adı güncelleştirmek için kullanmak zorunda **kaydetmek** yöntemi dosyayı farklı bir adla kaydedin. Bu nedenle, kendisini sınırlamak bir özellik sayfası kodda yok alma veya özelliklerini ayarlama.  
  
##  <a name="vccontesting_the_property_page"></a>Özellik sayfası görüntüleme  
 Bu sayfayı görüntülemek için bir basit yardımcı nesnesi oluşturmanız gerekir. Yardımcı nesnesi basitleştiren bir yöntem sağlar **OleCreatePropertyFrame** tek bir sayfayı görüntülemeye API tek bir nesneye bağlı. Bu yardımcı tasarlanacağını, böylece Visual Basic'ten kullanılabilir.  
  
 Kullanmak [Sınıf Ekle iletişim kutusu](../ide/add-class-dialog-box.md) ve [ATL Basit Nesne Sihirbazı](../atl/reference/atl-simple-object-wizard.md) yeni bir sınıf oluşturun ve kullanmak için `Helper` kısa ad olarak. Oluşturduktan sonra aşağıdaki tabloda gösterildiği gibi bir yöntem ekleyin.  
  
|Öğe|Değer|  
|----------|-----------|  
|Yöntem adı|`ShowPage`|  
|Parametreler|`[in] BSTR bstrCaption, [in] BSTR bstrID, [in] IUnknown* pUnk`|  
  
 `bstrCaption` İletişim kutusu başlığı olarak görüntülenecek resim yazısı parametresidir. `bstrID` Parametredir görüntülemek için bir CLSID veya özellik sayfasının bir ProgID temsil eden dize. `pUnk` Parametresi olacaktır `IUnknown` özelliklerini özellik sayfası tarafından yapılandırılacak nesne işaretçisi.  
  
 Yöntemi, aşağıda gösterildiği gibi uygulayın:  
  
 [!code-cpp[NVC_ATL_Windowing#80](../atl/codesnippet/cpp/example-implementing-a-property-page_8.cpp)]  
  
##  <a name="vcconcreating_a_macro"></a>Makro oluşturma  
 Proje oluşturuncaya sonra özellik sayfasında ve oluşturduğunuz ve ve Visual Studio geliştirme ortamında çalışan basit bir makrosu kullanarak yardımcı nesnesi test edebilirsiniz. Bu makrosu yardımcıyı oluşturacak nesne sonra çağırın kendi **ShowPage** ProgID kullanarak yöntemini **DocProperties** özellik sayfası ve **IUnknown** belge işaretçisi Visual Studio düzenleyicisinde şu anda etkin. Bu makrosu için gereksinim duyduğunuz kod aşağıda verilmiştir:  
  
```  
Imports EnvDTE  
Imports System.Diagnostics  
 
Public Module AtlPages  
 
    Public Sub Test()  
    Dim Helper  
    Helper = CreateObject("ATLPages7.Helper.1")  
 
    On Error Resume Next  
    Helper.ShowPage(_ 
    ActiveDocument.Name,
    _ 
 "ATLPages7Lib.DocumentProperties.1",
    _ 
    DTE.ActiveDocument _)  
    End Sub  
 
End Module  
```  
  
 Bu makrosu çalıştırdığınızda, dosya adı ve şu anda etkin metin belgesi salt okunur durumunu gösteren özellik sayfası görüntülenir. Belgeyi salt okunur durumunu yalnızca geliştirme ortamında belgeye yazma yeteneğini yansıtır; diskteki dosyanın salt okunur özniteliğini etkilemez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik sayfaları](../atl/atl-com-property-pages.md)   
 [ATLPages örnek](../visual-cpp-samples.md)

