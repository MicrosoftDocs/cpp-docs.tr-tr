---
title: Özellik Sayfası (ATL) Uygulama
ms.date: 05/09/2019
helpviewer_keywords:
- property pages, implementing
ms.assetid: c30b67fe-ce08-4249-ae29-f3060fa8d61e
ms.openlocfilehash: 0b2448e66e3b86e3295cd4b318a268a113f6058b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319586"
---
# <a name="example-implementing-a-property-page"></a>Örnek: Özellik Sayfası Uygulama

::: moniker range="vs-2019"

ATL Özellik Sayfası sihirbazı Visual Studio 2019 ve sonraki yıllarda kullanılamaz.

::: moniker-end

::: moniker range="<=vs-2017"

Bu örnek, [Belge Sınıfları](../mfc/document-classes.md) arabiriminin özelliklerini görüntüleyen (ve değiştirmenize izin veren) bir özellik sayfasının nasıl oluşturulabildiğini gösterir.

Örnek, [ATLPages örneğine](../overview/visual-cpp-samples.md)dayanmaktadır.

Bu örneği tamamlamak için şunları yapacaksınız:

- Sınıf Ekle iletişim kutusunu ve ATL Özellik Sayfası Sihirbazı'nı kullanarak [ATL özellik sayfası sınıfını ekleyin.](#vcconusing_the_atl_object_wizard)

- `Document` Arabirimin ilginç özellikleri için yeni denetimler ekleyerek iletişim kaynağını [düzenleme.](#vcconediting_the_dialog_resource)

- Özellik sayfası sitesini kullanıcı tarafından yapılan değişikliklerden haberdar etmek için [ileti işleyicileri ekleyin.](#vcconadding_message_handlers)

- `#import` [Housekeeping](#vcconhousekeeping) bölümüne bazı ifadeler ve bir typedef ekleyin.

- Özellik sayfasına geçirilen nesneleri doğrulamak için [IPropertyPageImpl::Nesneleri Ayarlama.](#vcconoverriding_ipropertypageimpl_setobjects)

- [IPropertyPageImpl geçersiz kılın::Özellik](#vcconoverriding_ipropertypageimpl_activate) sayfasının arabirimini başlatmayı etkinleştirin.

- [IPropertyPageImpl geçersiz kılın::Nesneyi](#vcconoverride_ipropertypageimpl_apply) en son özellik değerleriyle güncelleştirmek için uygulayın.

- Basit bir yardımcı nesne oluşturarak [özellik sayfasını görüntüleyin.](#vccontesting_the_property_page)

- Özellik sayfasını sınayacak [bir makro oluşturun.](#vcconcreating_a_macro)

## <a name="adding-the-atl-property-page-class"></a><a name="vcconusing_the_atl_object_wizard"></a>ATL Özellik Sayfası Sınıfı Ekleme

İlk olarak, dll sunucusu için yeni `ATLPages7`bir ATL projesi oluşturun. Şimdi bir özellik sayfası oluşturmak için [ATL Özellik Sayfası Sihirbazı'nı](../atl/reference/atl-property-page-wizard.md) kullanın. Özellik sayfasına **DocProperties'in** **Kısa Adı** verin ve ardından aşağıdaki tabloda gösterildiği gibi özellik sayfasına özgü öğeleri ayarlamak için **Dizeleri** sayfasına geçin.

|Öğe|Değer|
|----------|-----------|
|Başlık|Metin Belgesi|
|Doküman Dizesi|VCUE TextDocument Özellikleri|
|Helpfile|*\<boş>*|

Sihirbazın bu sayfasında belirlediğiniz değerler, çağırdığı `IPropertyPage::GetPageInfo`zaman özellik sayfası kapsayıcısına döndürülür. Bundan sonra dizeleri ne olur kapsayıcı bağlıdır, ancak genellikle kullanıcıya sayfanızı tanımlamak için kullanılır. Başlık genellikle sayfanızın üstündeki bir sekmede görünür ve Doküman Dizesi durum çubuğunda veya Araç İpucu'nda görüntülenebilir (standart özellik çerçevesi bu dizeyi hiç kullanmasa da).

> [!NOTE]
> Burada ayarladığınız dizeleri sihirbaz tarafından projenizde dize kaynakları olarak depolanır. Sayfanızın kodu oluşturulduktan sonra bu bilgileri değiştirmeniz gerekiyorsa, kaynak düzenleyicisini kullanarak bu dizeleri kolayca edinebilirsiniz.

Sihirbazın özellik sayfanızı oluşturması için **Tamam'ı** tıklatın.

## <a name="editing-the-dialog-resource"></a><a name="vcconediting_the_dialog_resource"></a>İletişim Kaynağını Düzenleme

Özellik sayfanız oluşturulduğuna göre, sayfanızı temsil eden iletişim kaynağına birkaç denetim eklemeniz gerekir. Bir edit kutusu, statik metin denetimi ve bir onay kutusu ekleyin ve kimliklerini aşağıda gösterildiği gibi ayarlayın:

![İletişim kaynağını düzenleme](../atl/media/ppgresourcelabeled.gif "İletişim kaynağını düzenleme")

Bu denetimler, belgenin dosya adını ve salt okunur durumunu görüntülemek için kullanılır.

> [!NOTE]
> İletişim kaynağı bir çerçeve veya komut düğmeleri içermez, ne de beklediğiniz sekmeli görünüme sahip. Bu özellikler, [OleCreatePropertyFrame'i](/windows/win32/api/olectl/nf-olectl-olecreatepropertyframe)arayarak oluşturulan özellik sayfası çerçevesi tarafından sağlanmaktadır.

## <a name="adding-message-handlers"></a><a name="vcconadding_message_handlers"></a>İleti Işleyicileri Ekleme

Denetimler yerindeyken, denetimlerden birinin değeri değiştiğinde sayfanın kirli durumunu güncelleştirmek için ileti işleyicileri ekleyebilirsiniz:

[!code-cpp[NVC_ATL_Windowing#73](../atl/codesnippet/cpp/example-implementing-a-property-page_1.h)]

Bu kod, sayfanın değiştiğini sayfa sitesine bildiren [IPropertyPageImpl::SetDirty](../atl/reference/ipropertypageimpl-class.md#setdirty)adlı telefonu arayarak düzenleme denetiminde veya onay kutusunda yapılan değişikliklere yanıt verir. Genellikle sayfa sitesi, özellik sayfası çerçevesindeki bir **Uygula** düğmesini etkinleştirerek veya devre dışı bırakarak yanıt verir.

> [!NOTE]
> Kendi özellik sayfalarınızda, değiştirilmemiş özellikleri güncelleştirmekten kaçınmak için kullanıcı tarafından tam olarak hangi özelliklerin değiştirildiğini izlemeniz gerekebilir. Bu örnek, özgün özellik değerlerini izleyerek ve değişiklikleri uygulama zamanı geldiğinde ui'deki geçerli değerlerle karşılaştırarak bu kodu uygular.

## <a name="housekeeping"></a><a name="vcconhousekeeping"></a>Temizlik

Şimdi derleyici `#import` `Document` arabirimi hakkında bilir böylece DocProperties.h ifadeler bir çift ekleyin:

[!code-cpp[NVC_ATL_Windowing#74](../atl/codesnippet/cpp/example-implementing-a-property-page_2.h)]

Ayrıca `IPropertyPageImpl` taban sınıfa başvurmanız gerekir; sınıfa aşağıdaki **typedef** ekleyin: `CDocProperties`

[!code-cpp[NVC_ATL_Windowing#75](../atl/codesnippet/cpp/example-implementing-a-property-page_3.h)]

## <a name="overriding-ipropertypageimplsetobjects"></a><a name="vcconoverriding_ipropertypageimpl_setobjects"></a>Geçersiz kılma IPropertyPageImpl::SetObjects

Geçersiz `IPropertyPageImpl` kılmak için gereken ilk yöntem [SetObjects](../atl/reference/ipropertypageimpl-class.md#setobjects)olduğunu. Burada yalnızca tek bir nesnenin geçirildiğini ve beklediğiniz `Document` arabirimi desteklediğini denetlemek için kod eklersiniz:

[!code-cpp[NVC_ATL_Windowing#76](../atl/codesnippet/cpp/example-implementing-a-property-page_4.h)]

> [!NOTE]
> Kullanıcının nesnenin dosya adını ayarlamasına izin vereceksiniz çünkü bu sayfa için yalnızca tek bir nesneyi desteklemek mantıklıdır — herhangi bir konumda yalnızca bir dosya bulunabilir.

## <a name="overriding-ipropertypageimplactivate"></a><a name="vcconoverriding_ipropertypageimpl_activate"></a>Geçersiz kılma IPropertyPageImpl::Etkinleştir

Bir sonraki adım, sayfa ilk oluşturulduğunda temel nesnenin özellik değerleriyle özellik sayfasını başlatmadır.

Bu durumda, sayfa kullanıcıları değişikliklerini uyguladığında karşılaştırma için ilk özellik değerlerini de kullanacağınız için sınıfa aşağıdaki üyeleri eklemeniz gerekir:

[!code-cpp[NVC_ATL_Windowing#77](../atl/codesnippet/cpp/example-implementing-a-property-page_5.h)]

[Etkinleştirme](../atl/reference/ipropertypageimpl-class.md#activate) yönteminin taban sınıf uygulaması iletişim kutusunu ve denetimlerini oluşturmaktan sorumludur, böylece bu yöntemi geçersiz kılabilir ve taban sınıfı aradıktan sonra kendi başlatmanızı ekleyebilirsiniz:

[!code-cpp[NVC_ATL_Windowing#78](../atl/codesnippet/cpp/example-implementing-a-property-page_6.h)]

Bu kod, ilgilendiğiniz `Document` özellikleri almak için arabirimin COM yöntemlerini kullanır. Daha sonra kullanıcıya özellik değerlerini görüntülemek için [CDialogImpl](../atl/reference/cdialogimpl-class.md) ve temel sınıfları tarafından sağlanan Win32 API sarmalayıcıları kullanır.

## <a name="overriding-ipropertypageimplapply"></a><a name="vcconoverride_ipropertypageimpl_apply"></a>Geçersiz kılma IPropertyPageImpl::Uygula

Kullanıcılar değişikliklerini nesnelere uygulamak istediklerinde, özellik sayfası sitesi [Uygula](../atl/reference/ipropertypageimpl-class.md#apply) yöntemini çağırır. Bu, kodun tersini yapmak `Activate` için bir `Activate` yerdir — oysa değer nesneden değerleri alıp `Apply` özellik sayfasındaki denetimlere iter, özellik sayfasındaki denetimlerden değerleri alır ve nesneye iter.

[!code-cpp[NVC_ATL_Windowing#79](../atl/codesnippet/cpp/example-implementing-a-property-page_7.h)]

> [!NOTE]
> Bu uygulamanın başında [m_bDirty](../atl/reference/ipropertypageimpl-class.md#m_bdirty) karşı denetim birden fazla kez çağrılır sayının `Apply` gereksiz güncelleştirmelerini önlemek için bir ilk denetimdir. Ayrıca, yalnızca değişikliklerin bir yöntem çağrısıyla sonuçlanmasından emin olmak `Document`için özellik değerlerinin her birine karşı denetimler de vardır.

> [!NOTE]
> `Document`salt `FullName` okunur bir özellik olarak ortaya çıkarır. Özellik sayfasında yapılan değişikliklere göre belgenin dosya adını güncelleştirmek için, dosyayı `Save` farklı bir adla kaydetmek için yöntemi kullanmanız gerekir. Bu nedenle, bir özellik sayfasındaki kodun kendisini özellikleri almak veya ayarlamakla sınırlamak zorunda değildir.

## <a name="displaying-the-property-page"></a><a name="vccontesting_the_property_page"></a>Özellik Sayfasını Görüntüleme

Bu sayfayı görüntülemek için basit bir yardımcı nesne oluşturmanız gerekir. Yardımcı nesne, tek bir nesneye `OleCreatePropertyFrame` bağlı tek bir sayfagörüntülemek için API basitleştiren bir yöntem sağlar. Bu yardımcı Visual Basic'ten kullanılabilecek şekilde tasarlanacaktır.

Yeni bir sınıf oluşturmak ve kısa adı olarak kullanmak için Sınıf `Helper` Ekle iletişim [kutusunu](../ide/add-class-dialog-box.md) ve [ATL Basit Nesne Sihirbazı'nı](../atl/reference/atl-simple-object-wizard.md) kullanın. Oluşturulduktan sonra, aşağıdaki tabloda gösterildiği gibi bir yöntem ekleyin.

|Öğe|Değer|
|----------|-----------|
|Yöntem Adı|`ShowPage`|
|Parametreler|`[in] BSTR bstrCaption, [in] BSTR bstrID, [in] IUnknown* pUnk`|

*bstrCaption* parametresi, iletişim kutusunun başlığı olarak görüntülenecek başlıktır. *bstrID* parametresi, görüntülenecek özellik sayfasının CLSID veya ProgID'sini temsil eden bir dizedir. *PUnk* parametresi, `IUnknown` özellikleri özellik sayfası tarafından yapılandırılacak nesnenin işaretçisi olacaktır.

Yöntemi aşağıda gösterildiği gibi uygulayın:

[!code-cpp[NVC_ATL_Windowing#80](../atl/codesnippet/cpp/example-implementing-a-property-page_8.cpp)]

## <a name="creating-a-macro"></a><a name="vcconcreating_a_macro"></a>Makro Oluşturma

Projeyi oluşturduktan sonra, Visual Studio geliştirme ortamında oluşturabileceğiniz ve çalıştırabileceğiniz basit bir makroyu kullanarak özellik sayfasını ve yardımcı nesneyi sınayabilirsiniz. Bu makro bir yardımcı nesne oluşturur, `ShowPage` ardından **DocProperties** özellik sayfasının ProgID'sini ve Visual Studio düzenleyicisinde şu anda etkin olan belgenin `IUnknown` işaretçisini kullanarak yöntemini çağırır. Bu makro için ihtiyacınız olan kod aşağıda gösterilmiştir:

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

Bu makroyu çalıştırdığınızda, özellik sayfası dosya adını ve şu anda etkin olan metin belgesinin salt okunur durumunu gösterirken görüntülenir. Belgenin salt okunur durumu yalnızca geliştirme ortamında belgeye yazma yeteneğini yansıtır; diskteki dosyanın salt okunur özniteliğini etkilemez.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Özellik Sayfaları](../atl/atl-com-property-pages.md)<br/>
[ATLPages Örnek](../overview/visual-cpp-samples.md)
