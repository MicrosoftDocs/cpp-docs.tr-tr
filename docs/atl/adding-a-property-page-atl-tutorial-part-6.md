---
title: Özellik sayfası (ATL Eğitmeni, Bölüm 6) ekleme | Microsoft Docs
ms.custom: get-started-article
ms.date: 11/04/2016
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
ms.openlocfilehash: bf7f0383697fbc1e23e179936a2616d1d236b5f2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="adding-a-property-page-atl-tutorial-part-6"></a>Özellik Sayfası Ekleme (ATL Eğitmeni, Bölüm 6)
Özellik sayfaları izin vermeniz gerekirse paylaşılan ayrı COM nesneleri uygulanır. Bu adımda, bir özellik sayfası denetimine eklemek için aşağıdaki görevleri yapar:  
  
-   Özellik sayfası kaynağı oluşturuluyor  
  
-   Kod oluşturma ve yönetme özellik sayfası ekleme  
  
-   Denetime özellik sayfası ekleme  
  
## <a name="creating-the-property-page-resource"></a>Özellik sayfası kaynağı oluşturuluyor  
 Özellik sayfası denetiminize eklemek için ATL ekleme sınıfı Sihirbazı'nı kullanın.  
  
#### <a name="to-add-a-property-page"></a>Özellik sayfası ekleme  
  
1.  Çözüm Gezgini'nde Çokgen sağ tıklayın.  
  
2.  Kısayol menüsünde **Ekle**ve ardından **sınıfı Ekle**.  
  
3.  Şablonları listesinden seçin **ATL özellik sayfası** tıklatıp **Ekle**.  
  
4.  ATL Özellik Sayfası Sihirbazı'nı belirdiğinde girin `PolyProp` olarak **kısa** adı.  
  
5.  Tıklatın **dizeleri** açmak için **dizeleri** sayfasında ve girin **& Çokgen** olarak **başlık**.  
  
     **Başlık** sayfa bu sayfa için sekmesindeki görünen dize özelliğidir. **Belge dize** bir durum satırı veya araç ipucunda koymak için bir özellik çerçevesi kullanan bir açıklamadır. Varsayılan içerikle bırakın standart özellik çerçeve şu anda bu dize kullanmadığından olduğunu unutmayın. Değil oluşturacak bir **Yardım dosyası** şu anda, bu yüzden metin kutusuna girişi silin.  
  
6.  Tıklatın **son**, ve özellik sayfası nesnesi oluşturulur.  
  
 Aşağıdaki üç dosyalar oluşturulur:  
  
|Dosya|Açıklama|  
|----------|-----------------|  
|PolyProp.h|C++ sınıfı içeren `CPolyProp`, özellik sayfasında uygular.|  
|PolyProp.cpp|PolyProp.h dosyası içerir.|  
|PolyProp.rgs|Özellik sayfası nesnesi kaydeder kayıt defteri komut dosyası.|  
  
 Aşağıdaki kod değişikliklerini de oluşturulur:  
  
-   Yeni özellik sayfası Polygon.cpp nesne girişi eşlemesinde eklenir.  
  
-   `PolyProp` Sınıfı Polygon.idl dosyasına eklenir.  
  
-   Yeni kayıt defteri komut dosyası PolyProp.rgs proje kaynağı eklenir.  
  
-   Bir iletişim kutusu Şablonu proje kaynak için özellik sayfası eklenir.  
  
-   Belirtilen özellik dizelerini kaynak dize tabloya eklenir.  
  
 Şimdi özellik sayfasında görüntülenmesini istediğiniz alanları ekleyin.  
  
#### <a name="to-add-fields-to-the-property-page"></a>Özellik alanları eklemek için  
  
1.  Çözüm Gezgini'nde Polygon.rc kaynak dosyasını çift tıklatın. Bu kaynak görünümü açılır.  
  
2.  Kaynak Görünümü IDD_POLYPROP çift tıklayın ve iletişim düğümünü genişletin. Görüntülenen iletişim kutusunda denetimleri burada eklemek için bildiren bir etiket dışında boş olduğunu unutmayın.  
  
3.  Etiket seçin ve okunacak şekilde değiştirin `Sides:` değiştirilmesine tarafından **resim yazısı** metinde **özellikleri** penceresi.  
  
4.  Etiket kutusu metnin boyutuna uygun şekilde yeniden boyutlandırın.  
  
5.  Düzenleme Denetimi Araç Kutusu'ndan etiketi sağına sürükleyin.  
  
6.  Son olarak, değişiklik **kimliği** düzenleme denetiminin `IDC_SIDES` Özellikler penceresini kullanarak.  
  
 Bu özellik sayfası kaynağı oluşturma işlemi tamamlar.  
  
## <a name="adding-code-to-create-and-manage-the-property-page"></a>Kod oluşturma ve yönetme özellik sayfası ekleme  
 Özellik sayfası kaynak oluşturduğunuza göre uygulama kod yazmanız gerekir.  
  
 İlk olarak, etkinleştirme `CPolyProp` , nesne tarafı sayısını ayarlamak için sınıf zaman **Uygula** düğmesine basıldığında.  
  
#### <a name="to-modify-the-apply-function-to-set-the-number-of-sides"></a>Kenar sayısını ayarlamak için Uygula işlevi değiştirmek için  
  
1.  Değiştir `Apply` PolyProp.h işlevinde aşağıdaki kod ile:  
  
     [!code-cpp[NVC_ATL_Windowing#58](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_1.h)]  
  
 Birden çok istemci aynı anda bağlı bir özellik sayfasında bulunabilir böylece `Apply` işlevi geçici döngüler ve çağırır `put_Sides` düzenleme kutusundan alınan her istemcide değerine sahip. Kullanmakta olduğunuz [CComQIPtr](../atl/reference/ccomqiptr-class.md) gerçekleştirir sınıfı `QueryInterface` elde etmek için her bir nesne üzerinde `IPolyCtl` alanından arabirim **IUnknown** arabirimi (depolanan `m_ppUnk` array).  
  
 Kod artık bu ayar denetler `Sides` gerçekten çalışılan özelliği. Başarısız olursa, kod hata ayrıntılarını görüntüleme bir ileti kutusu görüntüler **IErrorInfo** arabirimi. Genellikle, bir nesne için bir kapsayıcı ister **ISupportErrorInfo** arabirimi ve çağrıları `InterfaceSupportsErrorInfo` nesne ayarı hata bilgilerini destekleyip desteklemediğini belirlemek için öncelikle,. Bu görev atlayabilirsiniz.  
  
 [CComPtr](../atl/reference/ccomptr-class.md) çağrısı gerek yoktur başvuru sayımı otomatik olarak işleyerek yardımcı `Release` arabirimde. `CComBSTR` sizinle yardımcı `BSTR` son gerçekleştirmek zorunda değil, işleme `SysFreeString` çağırın. Dönüştürme ayrıca çeşitli dize dönüştürme sınıflarından birini kullanmanız `BSTR` gerekirse (nedeni budur `USES_CONVERSION` makrosu işlevi başlangıcında olduğu).  
  
 Belirtmek için özellik sayfasının kirli bayrağının ayarlanması gerekir **Uygula** düğmesi etkinleştirilmesi gerekir. Bu kullanıcı değeri değiştirdiğinde oluşur **kenara** düzenleme kutusu.  
  
#### <a name="to-handle-the-apply-button"></a>Uygula düğmesini işleme  
  
1.  Sınıf Görünümü'nde CPolyProp sağ tıklatın ve **özellikleri** kısayol menüsünde.  
  
2.  Özellikler penceresinde **olayları** simgesi.  
  
3.  Genişletme `IDC_SIDES` düğüm olay liste.  
  
4.  Seçin `EN_CHANGE`ve sağındaki açılan menüden  **\<Ekle > OnEnChangeSides**. `OnEnChangeSides` İşleyici bildirimi Polyprop.h ve Polyprop.cpp işleyici kullanımla eklenir.  
  
 Ardından, işleyici değiştirecektir.  
  
#### <a name="to-modify-the-onenchangesides-method"></a>OnEnChangeSides yöntemini değiştirmek için  
  
1.  Polyprop.cpp için aşağıdaki kodu ekleyin `OnEnChangeSides` yöntemi (Sihirbaz oraya yerleştirebilir herhangi bir kod silme):  
  
     [!code-cpp[NVC_ATL_Windowing#59](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_2.cpp)]  
  
 `OnEnChangeSides` ne zaman çağrılacağı bir **WM_COMMAND** iletinin gönderildiği ile **EN_CHANGE** bildirimi `IDC_SIDES` denetim. `OnEnChangeSides` Daha sonra çağırır `SetDirty` ve geçirir `TRUE` özelliği belirtmek için sayfa şimdi kirli ve **Uygula** düğmesi etkinleştirilmesi gerekir.  
  
## <a name="adding-the-property-page-to-the-control"></a>Denetime özellik sayfası ekleme  
 Projenizde birden çok denetim olabilir çünkü ATL ekleme sınıfı Sihirbazı'nı ve ATL Özellik Sayfası Sihirbazı'nı özellik sayfası denetiminize sizin için otomatik olarak eklemeyin. Denetimin özellik eşlemesi için bir giriş eklemeniz gerekir.  
  
#### <a name="to-add-the-property-page"></a>Özellik sayfası ekleme  
  
1.  PolyCtl.h açın ve özellik eşlemesi için bu satırı ekleyin:  
  
     [!code-cpp[NVC_ATL_Windowing#60](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_3.h)]  
  
 Denetimin özellik eşlemesi şimdi şöyle görünür:  
  
 [!code-cpp[NVC_ATL_Windowing#61](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_4.h)]  
  
 Eklediğiniz bir `PROP_PAGE` makrosu kullanırsanız, ancak özellik sayfası CLSID `PROP_ENTRY` gösterildiği gibi makrosu `Sides` özellik değeri denetimi kaydedildiğinde de kaydediliyor.  
  
 Üç makro özelliğinin DISPID ve özellik üzerinde sahip özellik sayfası CLSID özellik açıklaması parametreleridir. Örneğin, Visual Basic denetimi yükleyebilir ve tasarım zamanında kenar sayısını ayarlayın, bu yararlı olur. Visual Basic projenizi yeniden zaman kenar sayısını kaydedilmiş olduğundan, kenar sayısını geri yüklenir.  
  
## <a name="building-and-testing-the-control"></a>Derleme ve denetim test etme  
 Şimdi bu denetimi oluşturmak ve ActiveX denetimi Test kapsayıcısı ekleyin. Test kapsayıcısı içinde üzerinde **Düzenle** menüsünde tıklatın **PolyCtl sınıf nesnesi**. Özellik sayfası görüntülenir; tıklatın **Çokgen** sekmesi.  
  
 **Uygula** düğmesi başlangıçta devre dışı. Bir değer yazmaya başlayın **kenara** kutusu ve **Uygula** düğmesi etkin hale gelir. Değer girme bitirdikten sonra tıklatın **Uygula** düğmesi. Denetim görüntüleme değişikliklerini ve **Uygula** düğmesi yeniden devre dışı. Geçersiz bir değer girmeyi deneyin. Kümeden hata açıklamasını içeren bir ileti kutusu görürsünüz `put_Sides` işlevi.  
  
 Ardından, bir Web sayfası denetiminizde sokar.  
  
 [5. adım dön](../atl/adding-an-event-atl-tutorial-part-5.md) &#124; [adıma 7](../atl/putting-the-control-on-a-web-page-atl-tutorial-part-7.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Öğretici](../atl/active-template-library-atl-tutorial.md)

