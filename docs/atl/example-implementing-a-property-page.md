---
title: Özellik sayfası (ATL) uygulama
ms.date: 11/19/2018
helpviewer_keywords:
- property pages, implementing
ms.assetid: c30b67fe-ce08-4249-ae29-f3060fa8d61e
ms.openlocfilehash: 9aaf75916196f33904a51289d0a49725e042aa9e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262113"
---
# <a name="example-implementing-a-property-page"></a>Örnek: Özellik sayfası uygulama

Bu örnekte derleme özelliklerini görüntüler (ve değiştirmenize izin verir) bir özellik sayfası gösterilmektedir [belge sınıfları](../mfc/document-classes.md) arabirimi.

Örneği temel alarak [ATLPages örnek](../overview/visual-cpp-samples.md).

Bu örneği tamamlamak için şunları yapacaksınız:

- [ATL özellik sayfası sınıfının ekleme](#vcconusing_the_atl_object_wizard) Sınıf Ekle iletişim kutusu ve ATL Özellik Sayfası Sihirbazı'nı kullanarak.

- [İletişim kaynağını Düzenle](#vcconediting_the_dialog_resource) ilginç özelliklerine yönelik yeni denetimler ekleyerek `Document` arabirimi.

- [İleti işleyicileri eklemek](#vcconadding_message_handlers) özellik sayfası site tutmak için kullanıcı tarafından yapılan değişiklikler hakkında bilgi sahibi olmak.

- Bazı ekleme `#import` bildirimleri ve typedef içindeki [temizlik](#vcconhousekeeping) bölümü.

- [Geçersiz kılma IPropertyPageImpl::SetObjects](#vcconoverriding_ipropertypageimpl_setobjects) özellik sayfasında geçirilen nesneleri doğrulamak için.

- [Geçersiz kılma IPropertyPageImpl::Activate](#vcconoverriding_ipropertypageimpl_activate) özellik sayfa arabirimi başlatılamıyor.

- [Geçersiz kılma IPropertyPageImpl::Apply](#vcconoverride_ipropertypageimpl_apply) nesne en son özellik değerleri güncelleştirilemedi.

- [Özellik sayfasını görüntüleme](#vccontesting_the_property_page) oluşturarak basit yardımcı nesnesi.

- [Makro oluşturma](#vcconcreating_a_macro) özellik sayfasını test.

##  <a name="vcconusing_the_atl_object_wizard"></a> ATL özellik sayfası sınıfının ekleme

İlk olarak, adlı bir DLL sunucusu için yeni bir ATL projesi oluşturma `ATLPages7`. Artık [ATL Özellik Sayfası Sihirbazı](../atl/reference/atl-property-page-wizard.md) özellik sayfası oluşturmak için. Özellik sayfası vermek bir **kısa ad** , **DocProperties** dönersiniz **dizeleri** sayfasında, aşağıdaki tabloda gösterildiği gibi özellik sayfası özel öğeleri ayarlamak için.

|Öğe|Değer|
|----------|-----------|
|Başlık|TextDocument|
|Doc dizesi|VCUE TextDocument özellikleri|
|HelpFile|*\<Boş >*|

Özellik sayfası kapsayıcıya çağırdığında sihirbazın bu sayfasında belirlediğiniz değerleri döndürülecek `IPropertyPage::GetPageInfo`. Ne sonra kapsayıcıdaki bağlıdır, ancak genellikle bunlar kullanıcı sayfanıza tanımlamak için kullanılacak dizeleri olur. Başlık genellikle yukarıda sayfanız bir sekmede görünür ve (standart özellik çerçevesi Bu dize hiç kullanmaz ancak) Doc dizesi bir durum çubuğu veya araç ipucu görüntülenebilir.

> [!NOTE]
>  Burada ayarlanan dizeleri varsayılan olarak, sihirbaz tarafından projeniz içindeki dize kaynaklarını olarak depolanır. Bu dizeler sayfanızın kod oluşturulduktan sonra bu bilgileri değiştirmeniz gerekirse, Kaynak Düzenleyicisi'ni kullanarak kolayca düzenleyebilirsiniz.

Tıklayın **Tamam** , özellik sayfası Oluştur Sihirbazı'nı sağlamak için.

##  <a name="vcconediting_the_dialog_resource"></a> İletişim kaynağını düzenleme

Oluşturulan, özellik sayfası, sayfanız temsil eden bir iletişim kutusu kaynağı için bazı denetimler eklemek gerekir. Düzenleme kutusu, bir statik metin denetimini ve onay kutusu ekleyin ve kimlikleri aşağıda gösterilen şekilde ayarlayın:

![Bir iletişim kutusu kaynağı düzenleme](../atl/media/ppgresourcelabeled.gif "düzenleme iletişim kutusu kaynağı")

Bu denetimler, dosya adını, belge ve salt okunur durumunu görüntülemek için kullanılır.

> [!NOTE]
>  İletişim kaynağını bir çerçeve veya komut düğmesi içermez ya da beklenen sekmeli görünümü yok. Bu özellikler gibi çağrılarak oluşturulan bir özellik sayfası çerçeve tarafından sağlanan [OleCreatePropertyFrame](/windows/desktop/api/olectl/nf-olectl-olecreatepropertyframe).

##  <a name="vcconadding_message_handlers"></a> İleti işleyicileri ekleme

Kontroller varken, denetimleri birini değeri değiştiğinde sayfa kirli durumu güncelleştirmek için ileti işleyicileri ekleyebilirsiniz:

[!code-cpp[NVC_ATL_Windowing#73](../atl/codesnippet/cpp/example-implementing-a-property-page_1.h)]

Bu kod düzenleme denetimi veya onay kutusunu çağırarak yapılan değişikliklere yanıt [IPropertyPageImpl::SetDirty](../atl/reference/ipropertypageimpl-class.md#setdirty), SAYA değişmiş sayfasında site bildirir. Sayfa site etkinleştirme veya devre dışı bırakarak yanıt genellikle bir **Uygula** düğmesine özellik sayfası çerçevesi.

> [!NOTE]
>  Kendi özellik sayfaları'nda değiştirilmemiştir özelliklerini güncelleştirme engellemek için tam olarak hangi özelliklerin kullanıcı tarafından değiştirilmiş izlemek gerekebilir. Bu örnek kod, özgün özellik değerlerini izler ve değişiklikleri uygulamak için zaman olduğunda kullanıcı arabiriminden geçerli değerleri karşılaştırma uygular.

##  <a name="vcconhousekeeping"></a> Temizlik

Şimdi birkaç ekleyin `#import` DocProperties.h deyimleriyle böylece derleyici bildiği `Document` arabirimi:

[!code-cpp[NVC_ATL_Windowing#74](../atl/codesnippet/cpp/example-implementing-a-property-page_2.h)]

Ayrıca başvurmanız gerekir `IPropertyPageImpl` aşağıdakileri ekleyin; temel sınıf **typedef** için `CDocProperties` sınıfı:

[!code-cpp[NVC_ATL_Windowing#75](../atl/codesnippet/cpp/example-implementing-a-property-page_3.h)]

##  <a name="vcconoverriding_ipropertypageimpl_setobjects"></a> IPropertyPageImpl::SetObjects geçersiz kılma

İlk `IPropertyPageImpl` geçersiz kılmak için gereken yöntemdir [SetObjects](../atl/reference/ipropertypageimpl-class.md#setobjects). Burada yalnızca tek bir nesne geçirildi ve onu desteklediğini denetlemek için kod ekleyeceksiniz `Document` beklediğiniz arabirimi:

[!code-cpp[NVC_ATL_Windowing#76](../atl/codesnippet/cpp/example-implementing-a-property-page_4.h)]

> [!NOTE]
>  Nesne dosyası adını kullanıcıya izin verir, çünkü yalnızca tek bir nesne için bu sayfayı desteklemek için mantıklı — tek bir dosya, herhangi bir konumda bulunabilir.

##  <a name="vcconoverriding_ipropertypageimpl_activate"></a> IPropertyPageImpl::Activate geçersiz kılma

Sayfanın ilk oluşturulduğunda temel nesnenin özellik değerlerini ile özellik sayfasını başlatmak için sonraki adımdır bakın.

Bu durumda sayfanın kullanıcıların yaptıkları değişiklikleri uyguladığınızda, karşılaştırma için ilk özellik değerleri de kullanacaksınız beri sınıfına aşağıdaki üyeleri eklemeniz gerekir:

[!code-cpp[NVC_ATL_Windowing#77](../atl/codesnippet/cpp/example-implementing-a-property-page_5.h)]

Temel sınıf uygulamasına [etkinleştirme](../atl/reference/ipropertypageimpl-class.md#activate) yöntemi, bu yöntemi yok sayın ve temel sınıfı çağırmadan sonra kendi başlatma Ekle iletişim kutusu ve denetimlerini oluşturmak için sorumludur:

[!code-cpp[NVC_ATL_Windowing#78](../atl/codesnippet/cpp/example-implementing-a-property-page_6.h)]

Bu kod, COM yöntemlerini kullanan `Document` ilgilendiğiniz özelliklerini almak için arabirim. Tarafından sağlanan Win32 API sarmalayıcıları kullanır [Cdialogımpl](../atl/reference/cdialogimpl-class.md) ve kullanıcıya özellik değerlerini görüntülemek için temel sınıfları.

##  <a name="vcconoverride_ipropertypageimpl_apply"></a> IPropertyPageImpl::Apply geçersiz kılma

Kullanıcıların yaptıkları değişiklikleri uygulamak istediğinizde, özellik sayfasında site çağıracak [Uygula](../atl/reference/ipropertypageimpl-class.md#apply) yöntemi. Bu kodun tersine yapmak için yerdir `Activate` — ise `Activate` nesnesinden değerleri sürdü ve bunları özellik sayfasında denetimlerine gönderdiniz `Apply` özellik sayfasındaki denetimleri değerlerini alır ve bunları gönderim nesne.

[!code-cpp[NVC_ATL_Windowing#79](../atl/codesnippet/cpp/example-implementing-a-property-page_7.h)]

> [!NOTE]
>  Onay karşı [m_bDirty](../atl/reference/ipropertypageimpl-class.md#m_bdirty) bu uygulama, nesnelerin gereksiz güncelleştirmelerini önlemek için ilk denetimini başındadır `Apply` birden çok kez çağrılır. Ayrıca her biri için bir yöntem çağrısına neden yalnızca değişiklikler sağlamak için özellik değerlerini denetimi yoktur `Document`.

> [!NOTE]
> `Document` kullanıma sunan `FullName` salt okunur bir özellik olarak. Özellik sayfasında yaptığınız değişikliklere göre belgenin dosya adı güncelleştirmek için kullanılacak olan `Save` dosyayı farklı bir adla kaydetmek için yöntemi. Bu nedenle, kendisini sınırlamak bir özellik sayfası kod yok alma veya ayarlama özellikleri için.

##  <a name="vccontesting_the_property_page"></a> Özellik sayfasını görüntüleme

Bu sayfayı görüntülemek için bir basit yardımcı nesnesi oluşturmanız gerekir. Yardımcı nesnesi basitleştiren bir yöntem sağlayacak `OleCreatePropertyFrame` API tek bir sayfayı görüntülemek için tek bir nesneye bağlı. Visual Basic kullanılabilir, böylece bu yardımcı tasarlanmış.

Kullanma [Sınıf Ekle iletişim kutusu](../ide/add-class-dialog-box.md) ve [ATL Basit Nesne Sihirbazı](../atl/reference/atl-simple-object-wizard.md) yeni bir sınıf oluşturmak ve kullanmak için `Helper` kısa ad olarak. Oluşturulduktan sonra aşağıdaki tabloda gösterildiği gibi bir yöntem ekleyin.

|Öğe|Değer|
|----------|-----------|
|Yöntem adı|`ShowPage`|
|Parametreler|`[in] BSTR bstrCaption, [in] BSTR bstrID, [in] IUnknown* pUnk`|

*BstrCaption* iletişim kutusunun başlığı olarak görüntülenecek resim yazısı parametredir. *BstrID* parametredir görüntülemek için bir CLSID veya ProgID özellik sayfasının temsil eden bir dize. *PUnk* parametre olacak `IUnknown` işaretçi nesnesinin özelliklerini özellik sayfası tarafından yapılandırılır.

Yöntemi, aşağıda gösterildiği gibi uygulayın:

[!code-cpp[NVC_ATL_Windowing#80](../atl/codesnippet/cpp/example-implementing-a-property-page_8.cpp)]

##  <a name="vcconcreating_a_macro"></a> Makro oluşturma

Projeyi oluşturduktan sonra özellik sayfası ve yardımcı nesnesi oluşturabilir ve Visual Studio geliştirme ortamında çalıştırmak basit bir makro kullanarak test edebilirsiniz. Bu makro, bir yardımcı oluşturacak nesnesi ve ardından arama kendi `ShowPage` ProgID kullanarak yöntemini **DocProperties** özellik sayfası ve `IUnknown` etkin Visual Studio Düzenleyicisi'nde belge işaretçisi. Bu makro için ihtiyacınız olan kod, aşağıda gösterilmiştir:

```vb
Imports EnvDTE
Imports System.Diagnostics

Public Module AtlPages

Public Sub Test()
    Dim Helper
    Helper = CreateObject("ATLPages7.Helper.1")

    On Error Resume Next
    Helper.ShowPage( ActiveDocument.Name, "ATLPages7Lib.DocumentProperties.1", DTE.ActiveDocument )
End Sub

End Module
```

Bu makro çalıştırdığınızda, dosya adı ve şu anda etkin bir metin belgesi salt okunur durumunu gösteren özellik sayfası görüntülenir. Belge salt okunur durumunu, yalnızca geliştirme ortamında belge yazma olanağı yansıtır; Bu dosya diskte salt okunur özniteliğini etkilemez.

## <a name="see-also"></a>Ayrıca bkz.

[Özellik Sayfaları](../atl/atl-com-property-pages.md)<br/>
[ATLPages örnek](../overview/visual-cpp-samples.md)
