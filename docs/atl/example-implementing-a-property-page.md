---
description: 'Daha fazla bilgi: örnek: Özellik sayfası uygulama'
title: Özellik sayfası uygulama (ATL)
ms.date: 05/09/2019
helpviewer_keywords:
- property pages, implementing
ms.assetid: c30b67fe-ce08-4249-ae29-f3060fa8d61e
ms.openlocfilehash: b5f05d4e47187a8d3c2fe10ca7a00808095a713a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152968"
---
# <a name="example-implementing-a-property-page"></a>Örnek: Özellik sayfası uygulama

::: moniker range="msvc-160"

ATL Özellik sayfası Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz.

::: moniker-end

::: moniker range="<=msvc-150"

Bu örnekte, [belge sınıfları](../mfc/document-classes.md) arabiriminin özelliklerini görüntüleyen (ve değiştirmenize olanak tanıyan) bir özellik sayfasının nasıl oluşturulacağı gösterilmektedir.

Örnek, [ATLPages örneğine](../overview/visual-cpp-samples.md)dayalıdır.

Bu örneği gerçekleştirmek için şunları yapmanız gerekir:

- Sınıf Ekle iletişim kutusunu ve ATL Özellik sayfası Sihirbazı 'Nı kullanarak [atl özellik sayfası sınıfını ekleyin](#vcconusing_the_atl_object_wizard) .

- Arabirimin ilginç özellikleri için yeni denetimler ekleyerek [iletişim kaynağını düzenleyin](#vcconediting_the_dialog_resource) `Document` .

- Özellik sayfası sitesini Kullanıcı tarafından yapılan değişikliklerin bilgilendirilmesi için [ileti Işleyicileri ekleyin](#vcconadding_message_handlers) .

- `#import` [Temizlik](#vcconhousekeeping) bölümünde bazı deyimler ve bir typedef ekleyin.

- Özellik sayfasına geçirilen nesneleri doğrulamak için [IPropertyPageImpl:: SetObjects öğesini geçersiz kılın](#vcconoverriding_ipropertypageimpl_setobjects) .

- Özellik sayfasının arabirimini başlatmak için [IPropertyPageImpl:: Activate öğesini geçersiz kılın](#vcconoverriding_ipropertypageimpl_activate) .

- Nesneyi en son özellik değerleriyle güncelleştirmek için [IPropertyPageImpl:: Apply öğesini geçersiz kılın](#vcconoverride_ipropertypageimpl_apply) .

- Basit bir yardımcı nesne oluşturarak [özellik sayfasını görüntüleyin](#vccontesting_the_property_page) .

- Özellik sayfasını test edecek [bir makro oluşturun](#vcconcreating_a_macro) .

## <a name="adding-the-atl-property-page-class"></a><a name="vcconusing_the_atl_object_wizard"></a> ATL Özellik sayfası sınıfını ekleme

İlk olarak, adlı bir DLL sunucusu için yeni bir ATL projesi oluşturun `ATLPages7` . Şimdi bir özellik sayfası oluşturmak için [atl özellik sayfası Sihirbazı 'nı](../atl/reference/atl-property-page-wizard.md) kullanın. Özellik sayfasına **DocProperties** 'In **kısa adı** verin ve ardından aşağıdaki tabloda gösterildiği gibi özellik sayfasına özgü öğeleri ayarlamak için **dizeler** sayfasına geçin.

|Öğe|Değer|
|----------|-----------|
|Başlık|TextDocument|
|Belge dizesi|VCUE TextDocument özellikleri|
|HelpFile|*\<blank>*|

Sihirbazın bu sayfasında ayarladığınız değerler, çağrı sırasında özellik sayfası kapsayıcısına döndürülür `IPropertyPage::GetPageInfo` . Bir kapsayıcıya bağımlı olduktan sonra dizelere ne olur, ancak genellikle bu, sayfanızı Kullanıcı için tanımlamak üzere kullanılır. Başlık genellikle sayfanızın üzerindeki bir sekmede görünür ve belge dizesi bir durum çubuğunda veya araç Ipucunda görüntülenebilir (ancak standart özellik çerçevesi bu dizeyi hiç kullanmıyor olsa da).

> [!NOTE]
> Burada ayarladığınız dizeler, sihirbaz tarafından projenizde dize kaynakları olarak depolanır. Sayfanızın kodu oluşturulduktan sonra bu bilgileri değiştirmeniz gerekiyorsa, bu dizeleri kaynak düzenleyicisini kullanarak kolayca düzenleyebilirsiniz.

Sihirbazın Özellik sayfanızı oluşturmasını sağlamak için **Tamam** ' ı tıklatın.

## <a name="editing-the-dialog-resource"></a><a name="vcconediting_the_dialog_resource"></a> Iletişim kaynağı düzenleniyor

Artık Özellik sayfanız oluşturuldığına göre, Sayfanızı temsil eden iletişim kaynağı için birkaç denetim eklemeniz gerekir. Bir düzenleme kutusu, statik metin denetimi ve onay kutusu ekleyin ve kimliklerini aşağıda gösterildiği gibi ayarlayın:

![İletişim kaynağı düzenleniyor](../atl/media/ppgresourcelabeled.gif "İletişim kaynağı düzenleniyor")

Bu denetimler, belgenin dosya adını ve salt okunurdur durumunu göstermek için kullanılacaktır.

> [!NOTE]
> İletişim kutusu kaynağı bir çerçeve veya komut düğmeleri içermez, ya da beklenolabileceğiniz sekmeli görünümü içermez. Bu özellikler, [OleCreatePropertyFrame](/windows/win32/api/olectl/nf-olectl-olecreatepropertyframe)çağırarak oluşturulmuş bir özellik sayfası çerçevesi tarafından sağlanır.

## <a name="adding-message-handlers"></a><a name="vcconadding_message_handlers"></a> Ileti Işleyicileri ekleme

Denetimlerle, denetimlerin her birinin değeri değiştiğinde sayfanın kirli durumunu güncelleştirmek için ileti işleyicileri ekleyebilirsiniz:

[!code-cpp[NVC_ATL_Windowing#73](../atl/codesnippet/cpp/example-implementing-a-property-page_1.h)]

Bu kod, sayfa sitesine sayfanın değiştiğini bildiren [IPropertyPageImpl:: SetDirty](../atl/reference/ipropertypageimpl-class.md#setdirty)çağırarak düzenleme denetimine veya onay kutusuna yapılan değişikliklere yanıt verir. Genellikle sayfa sitesi, özellik sayfası çerçevesindeki bir **Uygula** düğmesini etkinleştirerek veya devre dışı bırakarak yanıt verir.

> [!NOTE]
> Kendi özellik sayfalarınızda, değişmeyen özelliklerin güncelleştirilmesini önlemek için Kullanıcı tarafından hangi özelliklerin değiştirildiğini tam olarak izlemeniz gerekebilir. Bu örnek, özgün özellik değerlerini izleyerek bu kodu uygular ve değişiklikleri uygulamak için zaman olduğu zaman kullanıcı arabiriminden geçerli değerlerle karşılaştırır.

## <a name="housekeeping"></a><a name="vcconhousekeeping"></a> Temizlik

Şimdi `#import` , bir derleyicinin arabirimi hakkında bilmesi Için DocProperties. h öğesine birkaç deyim ekleyin `Document` :

[!code-cpp[NVC_ATL_Windowing#74](../atl/codesnippet/cpp/example-implementing-a-property-page_2.h)]

Ayrıca `IPropertyPageImpl` temel sınıfa başvurmanız gerekir; aşağıdakileri **`typedef`** sınıfına ekleyin `CDocProperties` :

[!code-cpp[NVC_ATL_Windowing#75](../atl/codesnippet/cpp/example-implementing-a-property-page_3.h)]

## <a name="overriding-ipropertypageimplsetobjects"></a><a name="vcconoverriding_ipropertypageimpl_setobjects"></a> IPropertyPageImpl:: SetObjects geçersiz kılınıyor

`IPropertyPageImpl`Geçersiz kılmanız gereken ilk yöntem [SetObjects](../atl/reference/ipropertypageimpl-class.md#setobjects)' dir. Burada yalnızca tek bir nesnenin geçtiğini ve beklediğiniz arabirimi desteklediğini denetlemek için kod ekleyeceksiniz `Document` :

[!code-cpp[NVC_ATL_Windowing#76](../atl/codesnippet/cpp/example-implementing-a-property-page_4.h)]

> [!NOTE]
> Kullanıcının nesnenin dosya adını ayarlayacağından, tek bir konumda yalnızca bir dosya bulunabilir olduğundan, Bu sayfa için yalnızca tek bir nesneyi desteklemeye yönelik bir fikir verir.

## <a name="overriding-ipropertypageimplactivate"></a><a name="vcconoverriding_ipropertypageimpl_activate"></a> IPropertyPageImpl:: Activate geçersiz kılınıyor

Sonraki adım, sayfa ilk oluşturulduğunda özellik sayfasını temeldeki nesnenin özellik değerleriyle başlatmalıdır.

Bu durumda, sayfanın kullanıcıları değişikliklerini uygulaması durumunda karşılaştırma için ilk özellik değerlerini de kullanacağınız için aşağıdaki üyeleri sınıfa eklemeniz gerekir:

[!code-cpp[NVC_ATL_Windowing#77](../atl/codesnippet/cpp/example-implementing-a-property-page_5.h)]

[Activate](../atl/reference/ipropertypageimpl-class.md#activate) yönteminin temel sınıf uygulamasında iletişim kutusu ve denetimleri oluşturulmasından sorumludur. bu sayede, bu yöntemi geçersiz kılabilir ve temel sınıfı çağırdıktan sonra kendi başlatıınızı ekleyebilirsiniz:

[!code-cpp[NVC_ATL_Windowing#78](../atl/codesnippet/cpp/example-implementing-a-property-page_6.h)]

Bu kod, `Document` ilgilendiğiniz özellikleri almak için ARABIRIMIN com yöntemlerini kullanır. Daha sonra, [Cdialogimpl](../atl/reference/cdialogimpl-class.md) tarafından sunulan Win32 API sarmalayıcıları ve Kullanıcı için özellik değerlerini göstermek için temel sınıfları kullanır.

## <a name="overriding-ipropertypageimplapply"></a><a name="vcconoverride_ipropertypageimpl_apply"></a> IPropertyPageImpl:: Apply geçersiz kılınıyor

Kullanıcılar nesneleri nesnelerine uygulamak istedikleri zaman, özellik sayfası sitesi [Uygula](../atl/reference/ipropertypageimpl-class.md#apply) yöntemini çağırır. Bu, içindeki kodun ters işlemini yapmak için gereken yerdir. Bu, `Activate` `Activate` nesnesinden değerler alıp özellik sayfasındaki denetimlere itilmiş olacak şekilde, `Apply` özellik sayfasındaki denetimlerden değerleri alır ve nesneye gönderir.

[!code-cpp[NVC_ATL_Windowing#79](../atl/codesnippet/cpp/example-implementing-a-property-page_7.h)]

> [!NOTE]
> Bu uygulamanın başlangıcında [m_bDirty](../atl/reference/ipropertypageimpl-class.md#m_bdirty) karşı denetim, birden çok kez çağrılırsa nesneler için gereksiz güncelleştirmelerden kaçınmaya yönelik bir ilk denetim olur `Apply` . Ayrıca, bir yöntem çağrısının yalnızca değişiklik sonucu olduğunu sağlamak için özellik değerlerinin her birine karşı denetimler de vardır `Document` .

> [!NOTE]
> `Document``FullName`salt okunurdur özelliği olarak gösterir. Özellik sayfasında yapılan değişikliklere dayalı olarak belgenin dosya adını güncelleştirmek için, bu `Save` yöntemi kullanarak dosyayı farklı bir adla kaydedin. Bu nedenle, özellik sayfasındaki kodun, özellikleri almak veya ayarlamak için kendisini sınırlaması gerekmez.

## <a name="displaying-the-property-page"></a><a name="vccontesting_the_property_page"></a> Özellik sayfasını görüntüleme

Bu sayfayı göstermek için basit bir yardımcı nesnesi oluşturmanız gerekir. Yardımcı nesne, `OleCreatePropertyFrame` tek bir nesneye bağlı tek bir sayfayı görüntülemek için API 'yi basitleştiren bir yöntem sağlar. Bu yardımcı, Visual Basic kullanılabilmesi için tasarlanacaktır.

Yeni bir sınıf oluşturmak ve kısa adı olarak kullanmak için [Sınıf Ekle iletişim kutusunu](../ide/adding-a-class-visual-cpp.md#add-class-dialog-box) ve [atl basit nesne Sihirbazı](../atl/reference/atl-simple-object-wizard.md) ' nı kullanın `Helper` . Oluşturulduktan sonra, aşağıdaki tabloda gösterildiği gibi bir yöntem ekleyin.

|Öğe|Değer|
|----------|-----------|
|Yöntem adı|`ShowPage`|
|Parametreler|`[in] BSTR bstrCaption, [in] BSTR bstrID, [in] IUnknown* pUnk`|

*BstrCaption* parametresi, iletişim kutusunun başlığı olarak görüntülenecek olan başlıktır. *Bçabad* parametresi, bir CLSID veya görüntülenecek özellik sayfasının ProgID 'sini temsil eden bir dizedir. *Punk* parametresi, `IUnknown` özellikleri özellik sayfası tarafından yapılandırılacak nesnenin işaretçisi olacaktır.

Yöntemi aşağıda gösterildiği gibi uygulayın:

[!code-cpp[NVC_ATL_Windowing#80](../atl/codesnippet/cpp/example-implementing-a-property-page_8.cpp)]

## <a name="creating-a-macro"></a><a name="vcconcreating_a_macro"></a> Makro oluşturma

Projeyi derledikten sonra, Visual Studio geliştirme ortamında oluşturabileceğiniz ve çalıştırabileceğiniz basit bir makro kullanarak özellik sayfasını ve yardımcı nesnesini test edebilirsiniz. Bu makro bir yardımcı nesne oluşturacak, sonra `ShowPage` **DocProperties** Özellik sayfasının ProgID 'Sini ve `IUnknown` Visual Studio Düzenleyicisi 'nde Şu anda etkin olan belgenin işaretçisini kullanarak yöntemini çağırır. Bu makro için gereken kod aşağıda gösterilmiştir:

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

Bu makroyu çalıştırdığınızda, geçerli etkin metin belgesinin dosya adını ve salt okunurdur durumunu gösteren özellik sayfası görüntülenecektir. Belgenin salt okunurdur durumu yalnızca geliştirme ortamında belgeye yazma özelliğini yansıtır; diskteki dosyanın salt okunurdur özniteliğini etkilemez.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Özellik Sayfaları](../atl/atl-com-property-pages.md)<br/>
[ATLPages örneği](../overview/visual-cpp-samples.md)
