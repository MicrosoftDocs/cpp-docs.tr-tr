---
description: 'Hakkında daha fazla bilgi edinin: Özellik sayfası ekleme (ATL öğreticisi, Bölüm 6)'
title: Özellik Sayfası Ekleme (ATL Eğitmeni, Bölüm 6)
ms.custom: get-started-article
ms.date: 09/27/2018
ms.assetid: df80d255-e7ea-49d9-b940-3f012e90cf9b
ms.openlocfilehash: c33789919e104cc1600622dc3972a23069afe573
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166297"
---
# <a name="adding-a-property-page-atl-tutorial-part-6"></a>Özellik Sayfası Ekleme (ATL Eğitmeni, Bölüm 6)

> [!NOTE]
> ATL OLE DB sağlayıcı Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz.

Özellik sayfaları ayrı COM nesneleri olarak uygulanır ve bu, gerektiğinde paylaşılmalarını sağlar. Bu adımda, denetime bir özellik sayfası eklemek için aşağıdaki görevleri yapacaksınız:

- Özellik sayfası kaynağı oluşturma

- Özellik sayfası oluşturmak ve yönetmek için kod ekleme

- Denetime Özellik sayfası ekleme

## <a name="creating-the-property-page-resource"></a>Özellik sayfası kaynağı oluşturma

Denetimi bir özellik sayfası eklemek için, ATL Özellik sayfası şablonunu kullanın.

### <a name="to-add-a-property-page"></a>Özellik sayfası eklemek için

1. **Çözüm Gezgini**' da sağ tıklayın `Polygon` .

1. Kısayol menüsünde,   >  **Yeni öğe** Ekle ' ye tıklayın.

1. Şablonlar listesinden **ATL**  >  **atl özellik sayfası** ' nı seçin ve **Ekle**' ye tıklayın.

1. **Atl özellik sayfası Sihirbazı** göründüğünde, **kısa** ad olarak *PolyProp* yazın.

1. **Dizeler sayfasını açmak** için **dizeler** ' e tıklayın ve **başlık** olarak **&Çokgen** girin.

   Özellik sayfasının **başlığı** , bu sayfanın sekmesinde görüntülenen dizedir. **Belge dizesi** bir özellik çerçevesinin bir durum satırına veya araç ipucuna koymak için kullandığı bir açıklamadır. Standart özellik çerçevesinin Şu anda bu dizeyi kullanmadığını unutmayın. bu nedenle, varsayılan içeriklerle bırakabilirsiniz. Kısa bir süre içinde bir **Yardım dosyası** üretilecektir, bu nedenle bu metin kutusundaki girdiyi silin.

1. **Son**' a tıklayın ve özellik sayfası nesnesi oluşturulur.

Aşağıdaki üç dosya oluşturulur:

|Dosya|Açıklama|
|----------|-----------------|
|PolyProp. h|`CPolyProp`Özellik sayfasını uygulayan C++ sınıfını içerir.|
|PolyProp. cpp|PolyProp. h dosyasını içerir.|
|PolyProp. rgs|Özellik sayfası nesnesini kaydeden kayıt defteri betiği.|

Aşağıdaki kod değişiklikleri de yapılır:

- Yeni özellik sayfası, Çokgen. cpp nesne girdisi eşlemesine eklenir.

- `PolyProp`Sınıf, Çokgen. IDL dosyasına eklenir.

- Yeni kayıt defteri betik dosyası PolyProp. rgs proje kaynağına eklenir.

- Özellik sayfası için proje kaynağına bir iletişim kutusu şablonu eklenir.

- Belirttiğiniz özellik dizeleri kaynak dize tablosuna eklenir.

Şimdi, özellik sayfasında görünmesini istediğiniz alanları ekleyin.

### <a name="to-add-fields-to-the-property-page"></a>Özellik sayfasına alanlar eklemek için

1. **Çözüm Gezgini**, Çokgen. RC kaynak dosyasına çift tıklayın. Bu, **kaynak görünümü** açar.

1. **Kaynak görünümü**, `Dialog` düğümünü genişletin ve çift tıklayın `IDD_POLYPROP` . Denetimlerin buraya eklenmesini söyleyen bir etiket hariç görünen iletişim kutusunun boş olduğunu unutmayın.

1. Bu etiketi seçin ve `Sides:` **Özellikler** penceresinde **başlık** metnini değiştirerek okunacak şekilde değiştirin.

1. Etiket kutusunu metnin boyutuna sığacak şekilde yeniden boyutlandırın.

1. **Araç kutusundan** bir **düzenleme denetimini** etiketin sağına sürükleyin.

1. Son olarak, düzenleme denetiminin **kimliğini** `IDC_SIDES` **Özellikler** penceresini kullanarak değiştirin.

Bu işlem, özellik sayfası kaynağı oluşturma sürecini tamamlar.

## <a name="adding-code-to-create-and-manage-the-property-page"></a>Özellik sayfası oluşturmak ve yönetmek için kod ekleme

Artık Özellik sayfası kaynağını oluşturduğunuza göre, uygulama kodunu yazmanız gerekir.

İlk olarak, `CPolyProp` **Uygula** düğmesine basıldığında, nesne içindeki kenar sayısını ayarlamak için sınıfı etkinleştirin.

### <a name="to-modify-the-apply-function-to-set-the-number-of-sides"></a>Kenar sayısını ayarlamak için Uygula işlevini değiştirme

1. `Apply`PolyProp. h içindeki işlevi şu kodla değiştirin:

    [!code-cpp[NVC_ATL_Windowing#58](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_1.h)]

Bir özellik sayfasına aynı anda birden fazla istemci eklenmiş olabilir, bu nedenle `Apply` işlev `put_Sides` her bir istemcide, düzenleme kutusundan alınan değerle döngü ve çağrılar olur. Arabirimi [](../atl/reference/ccomqiptr-class.md) `QueryInterface` `IPolyCtl` `IUnknown` arabiriminden (dizide depolanan) elde etmek için her bir nesne üzerinde öğesini gerçekleştiren CComQIPtr sınıfını kullanıyorsunuz `m_ppUnk` .

Kod şimdi, `Sides` özelliğin gerçekten çalıştığı ayarı kontrol eder. Başarısız olursa, kod arabirimden hata ayrıntılarını görüntüleyen bir ileti kutusu görüntüler `IErrorInfo` . Genellikle, bir kapsayıcı arabirim için bir nesne sorar `ISupportErrorInfo` ve `InterfaceSupportsErrorInfo` öncelikle nesnenin hata bilgilerini ayarlamayı destekleyip desteklemediğini tespit etmek için çağırır. Bu görevi atlayabilirsiniz.

[CComPtr](../atl/reference/ccomptr-class.md) , başvuru sayımını otomatik olarak işleyerek size yardımcı olur, bu nedenle arabirim üzerinde çağırmanız gerekmez `Release` . `CComBSTR` BSTR işleme yardımcı olur, bu yüzden son çağrıyı gerçekleştirmeniz gerekmez `SysFreeString` . Ayrıca, çeşitli dize dönüştürme sınıflarından birini de kullanabilirsiniz. bu sayede, gerekirse BSTR 'yi dönüştürebilirsiniz (Bu neden USES_CONVERSION makrosunun işlevin başlangıcında yer alabilir).

Ayrıca, **Uygula** düğmesinin etkinleştirilmesi gerektiğini göstermek için özellik sayfasının kirli bayrağını ayarlamanız gerekir. Bu durum, Kullanıcı, **kenarlar** düzenleme kutusundaki değeri değiştirdiğinde oluşur.

### <a name="to-handle-the-apply-button"></a>Uygula düğmesini işlemek için

1. **Sınıf görünümü**' de sağ tıklayıp `CPolyProp` kısayol menüsünde **Özellikler** ' e tıklayın.

1. **Özellikler** penceresinde **Olaylar** simgesine tıklayın.

1. `IDC_SIDES`Olay listesindeki düğümü genişletin.

1. Aşağı `EN_CHANGE` açılan menüden sağ taraftaki ' ı seçin ve ardından **\<Add> onenchangeyüzler**' e tıklayın. `OnEnChangeSides`İşleyici bildirimi PolyProp. h ' ye ve Ida PolyProp. cpp ' ye işleyici uygulamasına eklenecektir.

Sonra, işleyiciyi değiştirirsiniz.

### <a name="to-modify-the-onenchangesides-method"></a>Onenchangekenarlar yöntemini değiştirmek için

1. Aşağıdaki kodu PolyProp. cpp `OnEnChangeSides` yöntemine ekleyin (sihirbazın oraya yerleştirdiği kodu silme):

    [!code-cpp[NVC_ATL_Windowing#59](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_2.cpp)]

`OnEnChangeSides``WM_COMMAND`, denetim bildirimi ile bir ileti gönderildiğinde çağrılacaktır `EN_CHANGE` `IDC_SIDES` . `OnEnChangeSides` ardından `SetDirty` , özellik sayfasının artık kirli olduğunu ve **Uygula** düğmesinin etkin olması GEREKTIĞINI belirtmek için true olarak geçirilir.

## <a name="adding-the-property-page-to-the-control"></a>Denetime Özellik sayfası ekleme

Projenizde birden çok denetim olabileceğinden, ATL Özellik sayfası şablonu ve Sihirbazı sizin için denetimi özellik sayfasını sizin için otomatik olarak eklemez. Denetimin özellik eşlemesine bir giriş eklemeniz gerekecektir.

### <a name="to-add-the-property-page"></a>Özellik sayfasını eklemek için

1. PolyCtl. h öğesini açın ve bu satırları özellik eşlemesine ekleyin:

    [!code-cpp[NVC_ATL_Windowing#60](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_3.h)]

Denetimin özellik eşlemesi şu şekilde görünür:

[!code-cpp[NVC_ATL_Windowing#61](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_4.h)]

`PROP_PAGE`Özellik sayfanızın CLSID 'sine sahip bir makro eklemiş olabilirsiniz, ancak `PROP_ENTRY` makroyu gösterildiği gibi kullanırsanız, `Sides` denetim kaydedildiğinde Özellik değeri de kaydedilir.

Makroya yönelik üç parametre, özellik açıklamasıdır, özelliğin DISPID 'si ve üzerinde özelliği olan özellik sayfasının CLSID 'SI. Bu, örneğin, denetimi Visual Basic yüklediğinizde ve tasarım zamanında kenar sayısını ayarlarsanız yararlı olur. Kenar sayısı kaydedildiğinden Visual Basic projenizi yeniden yüklediğinizde kenar sayısı geri yüklenir.

## <a name="building-and-testing-the-control"></a>Denetim oluşturma ve test etme

Şimdi bu denetimi derleyin ve ActiveX denetimi test kapsayıcısına ekleyin. **Test kapsayıcısında**, **Düzenle** menüsünde **PolyCtl sınıf nesnesi ' ne** tıklayın. Özellik sayfası, eklediğiniz bilgilerle birlikte görüntülenir.

**Uygula** düğmesi başlangıçta devre dışıdır. **Kenarlar** kutusuna bir değer yazmaya başlayın ve **Uygula** düğmesi etkin hale gelir. Değeri girmeyi tamamladıktan sonra **Uygula** düğmesine tıklayın. Denetim görünümü değişiklikleri ve **Uygula** düğmesi yeniden devre dışıdır. Geçersiz bir değer girmeyi deneyin. İşlevinden ayarladığınız hata açıklamasını içeren bir ileti kutusu görürsünüz `put_Sides` .

Daha sonra, denetiminizi bir Web sayfasına koyacaksınız.

Adım [5 ' e geri döndüğünüzde](../atl/adding-an-event-atl-tutorial-part-5.md) adım [7 ' de](../atl/putting-the-control-on-a-web-page-atl-tutorial-part-7.md) &#124;

## <a name="see-also"></a>Ayrıca bkz.

[Öğretici](../atl/active-template-library-atl-tutorial.md)
