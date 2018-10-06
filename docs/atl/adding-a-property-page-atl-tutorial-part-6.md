---
title: Özellik sayfası (ATL Eğitmeni, Bölüm 6) ekleme | Microsoft Docs
ms.custom: get-started-article
ms.date: 09/27/2018
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: df80d255-e7ea-49d9-b940-3f012e90cf9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9d0db4d53d64def1c1f55929aa9d7514142955cf
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2018
ms.locfileid: "48821149"
---
# <a name="adding-a-property-page-atl-tutorial-part-6"></a>Özellik Sayfası Ekleme (ATL Eğitmeni, Bölüm 6)

Özellik sayfaları, gerekirse paylaşılmasına izin vermek ayrı COM nesneleri uygulanır. Bu adımda, bir özellik sayfası denetimi eklemek için aşağıdaki görevleri yapar:

- Özellik sayfası kaynağı oluşturma

- Kod oluşturma ve yönetme özellik sayfası ekleme

- Denetime özellik sayfası ekleme

## <a name="creating-the-property-page-resource"></a>Özellik sayfası kaynağı oluşturma

Özellik sayfası denetiminize eklemek için ATL özellik sayfası şablonunu kullanın.

### <a name="to-add-a-property-page"></a>Özellik sayfası ekleme

1. İçinde **Çözüm Gezgini**, sağ `Polygon`.

1. Kısayol menüsünde **Ekle** > **yeni öğe**.

1. Şablonlar listesinden **ATL** > **ATL özellik sayfası** tıklatıp **Ekle**.

1. Zaman **ATL Özellik Sayfası Sihirbazı** görünen girin *PolyProp* olarak **kısa** adı.

1. Tıklayın **dizeleri** açmak için **dizeleri** sayfasında ve girin **& Çokgen** olarak **başlık**.

     **Başlık** özelliği sayfasında bu sayfa için sekmesinde görünen dizedir. **Doc dizesi** bir durum satırı veya araç ipucunda koymak için bir özellik çerçevesi kullanan bir açıklaması. Varsayılan içeriklerle bırakmak için standart özellik çerçevesi şu anda bu dize kullanımda bulunmadığını unutmayın. Değil oluşturacak bir **Yardım dosyası** şu anda, bu yüzden bu metin kutusunda girişi silin.

1. Tıklayın **son**, ve özellik sayfa nesnesi oluşturulur.

Aşağıdaki üç dosyayı oluşturulur:

|Dosya|Açıklama|
|----------|-----------------|
|PolyProp.h|C++ sınıfı içeren `CPolyProp`, özellik sayfasını uygular.|
|PolyProp.cpp|PolyProp.h dosyası içerir.|
|PolyProp.rgs|Kayıt betiği özellik sayfa nesnesi kaydeder.|

Aşağıdaki kod değişikliklerini de oluşturulur:

- Yeni özellik sayfası Polygon.cpp nesne giriş eşlemesine eklenir.

- `PolyProp` Sınıfı Polygon.idl dosyasına eklenir.

- Yeni kayıt defteri betik dosyası PolyProp.rgs proje kaynak eklenir.

- İletişim kutusu Şablondan proje kaynak için özellik sayfası eklenir.

- Belirtilen özellik dizelerini kaynak dize tablosuna eklenir.

Şimdi, özellik sayfasında görünmesini istediğiniz alanları ekleyin.

### <a name="to-add-fields-to-the-property-page"></a>Özellik sayfasında alanları eklemek için

1. İçinde **Çözüm Gezgini**, Polygon.rc kaynak dosyasına çift tıklayın. Bu açılır **kaynak görünümü**.

1. İçinde **kaynak görünümü**, genişletme `Dialog` düğüm ve çift `IDD_POLYPROP`. Görüntülenen iletişim kutusunda denetimlerinizi buraya girin bildiren bir etiket dışında boş olduğunu unutmayın.

1. Etiket seçin ve okumak için değiştirin `Sides:` değiştirme tarafından **açıklamalı alt yazı** metinde **özellikleri** penceresi.

1. Etiket kutusuna metin boyutuna sığacak şekilde yeniden boyutlandırın.

1. Sürükleme bir **düzenleme denetimi** gelen **araç kutusu** etiketin sağında.

1. Son olarak, değişiklik **kimliği** düzenleme denetiminin `IDC_SIDES` kullanarak **özellikleri** penceresi.

Bu özellik sayfasında kaynak oluşturma işlemini tamamlar.

## <a name="adding-code-to-create-and-manage-the-property-page"></a>Kod oluşturma ve yönetme özellik sayfası ekleme

Özellik sayfası kaynağı oluşturduğunuza göre uygulama kod yazmanız gerekir.

İlk olarak, etkinleştirme `CPolyProp` , kenar sayısını ayarlamak için sınıf olduğunda **Uygula** düğmesine basıldığında.

### <a name="to-modify-the-apply-function-to-set-the-number-of-sides"></a>Kenar sayısını ayarlamak için Uygula işlevi değiştirmek için

1. Değiştirin `Apply` PolyProp.h bir işlevde aşağıdaki kod ile:

    [!code-cpp[NVC_ATL_Windowing#58](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_1.h)]

Birden fazla istemci aynı anda en bağlı bir özellik sayfası olabilir böylece `Apply` işlevi etrafında döngüye girer ve çağıran `put_Sides` Düzenle iletişim kutusundan alınan her istemcide değerine sahip. Kullanmakta olduğunuz [CComQIPtr](../atl/reference/ccomqiptr-class.md) gerçekleştiren sınıfı `QueryInterface` elde etmek için her bir nesnedeki `IPolyCtl` alanından arabirim `IUnknown` arabirimi (depolanan `m_ppUnk` dizisi).

Kod artık bu ayarı denetler `Sides` aslında çalışan özelliği. Başarısız olursa, kod hata ayrıntılarını görüntüleyen bir ileti kutusu görüntüler `IErrorInfo` arabirimi. Genellikle, bir nesne için bir kapsayıcı ister `ISupportErrorInfo` arabirimi ve çağrıları `InterfaceSupportsErrorInfo` nesne ayarı hata bilgilerini destekleyip desteklemediğini belirlemek için ilk. Bu görev atlayabilirsiniz.

[CComPtr](../atl/reference/ccomptr-class.md) çağırmaya gerek kalmayacak şekilde başvuru sayımı otomatik olarak işleyerek yardımcı `Release` arabirimde. `CComBSTR` en son yapmak zorunda kalmazsınız BSTR işleme ile yardımcı olan `SysFreeString` çağırın. Gerekirse, (işlevin başında USES_CONVERSION makrodur nedeni budur) BSTR dönüştürme, ayrıca çeşitli dize dönüştürme sınıflarından birini kullanın.

Kirli bayrağı göstermek için özellik sayfa gerekir **Uygula** düğmesi etkinleştirilmelidir. Kullanıcı değeri değiştiğinde gerçekleşir **yüz** düzenleme kutusu.

### <a name="to-handle-the-apply-button"></a>Uygula düğmesini işlemek için

1. İçinde **sınıf görünümü**, sağ `CPolyProp` tıklatıp **özellikleri** kısayol menüsünde.

1. İçinde **özellikleri** penceresinde tıklayın **olayları** simgesi.

1. Genişletin `IDC_SIDES` düğümü olay listesi.

1. Seçin `EN_CHANGE`ve sağındaki açılan menüden  **\<Ekle > OnEnChangeSides**. `OnEnChangeSides` İşleyici bildirimi Polyprop.h ve Polyprop.cpp işleyici uygulamasına eklenecektir.

Ardından, işleyici değiştirir.

### <a name="to-modify-the-onenchangesides-method"></a>OnEnChangeSides yöntemini değiştirmek için

1. Polyprop.cpp için aşağıdaki kodu ekleyin `OnEnChangeSides` yöntemi (Sihirbaz buraya koymanız herhangi bir kod silme):

    [!code-cpp[NVC_ATL_Windowing#59](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_2.cpp)]

`OnEnChangeSides` ne zaman çağrılacağı bir `WM_COMMAND` ile gönderilen ileti `EN_CHANGE` bildirimi `IDC_SIDES` denetimi. `OnEnChangeSides` Daha sonra çağırır `SetDirty` ve özellik sayfası kirli, artık belirtmek için true değerini geçirir ve **Uygula** düğmesi etkinleştirilmelidir.

## <a name="adding-the-property-page-to-the-control"></a>Denetime özellik sayfası ekleme

Projenizde birden çok denetim olabilir çünkü ATL özellik sayfası şablonu ve sihirbaz özellik sayfası denetiminize sizin için otomatik olarak eklemeyin. Denetimin özellik eşlemesi için bir girdi eklemeniz gerekir.

### <a name="to-add-the-property-page"></a>Özellik sayfasını eklemek için

1. PolyCtl.h açın ve özellik eşlemesi için şu satırları ekleyin:

    [!code-cpp[NVC_ATL_Windowing#60](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_3.h)]

Denetimin özellik eşlemesi artık şöyle görünür:

[!code-cpp[NVC_ATL_Windowing#61](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_4.h)]

Eklediğiniz bir `PROP_PAGE` makro kullanırsanız, ancak özellik sayfası CLSID `PROP_ENTRY` gösterildiği gibi makro `Sides` özellik değeri denetim kaydedildiğinde da kaydedilir.

Makro üç parametreleri özellik açıklaması, DISPID özellik ve özelliği içeren özellik sayfasının CLSID bilgileridir. Örneğin, Visual Basic içinde yük denetimi ve kenar sayısını tasarım zamanında ayarlarsanız, bu yararlıdır. Kenar sayısını kaydedildiğinden Visual Basic projenizi yeniden yükleyin, kenar sayısını geri yüklenir.

## <a name="building-and-testing-the-control"></a>Derleme ve denetimini test etme

Artık bu denetimi oluşturmak ve ActiveX denetimi Test kapsayıcısı ekleyin. İçinde **Test kapsayıcısı**, **Düzenle** menüsünde tıklatın **PolyCtl sınıf nesnesi**. Özellik sayfası eklediğiniz bilgileri görüntülenir.

**Uygula** düğmesi başlangıçta devre dışı. Bir değer yazmaya başlayın **yüz** kutusu ve **Uygula** düğmesi etkin hale gelir. Değer girme işlemini tamamladıktan sonra tıklayın **Uygula** düğmesi. Denetim görüntüleme değişiklikleri ve **Uygula** düğmesini tekrar devre dışı. Geçersiz bir değer girmeyi deneyin. Kümesi, hata açıklamasını içeren bir ileti kutusu görürsünüz `put_Sides` işlevi.

Ardından, denetiminizi Web sayfasında koyacaktır.

[5. adım dön](../atl/adding-an-event-atl-tutorial-part-5.md) &#124; [açın 7. adım](../atl/putting-the-control-on-a-web-page-atl-tutorial-part-7.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Öğretici](../atl/active-template-library-atl-tutorial.md)
