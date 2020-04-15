---
title: 'MFC ActiveX Denetimleri: Özellik Sayfaları'
ms.date: 11/19/2018
helpviewer_keywords:
- DDP_ functions [MFC]
- MFC ActiveX controls [MFC], properties
- property pages [MFC], MFC ActiveX controls
- DoDataExchange method [MFC]
- OLEIVERB_PROPERTIES
- CPropertyPageDialog class [MFC]
- MFC ActiveX controls [MFC], property pages
ms.assetid: 1506f87a-9fd6-4505-8380-0dbc9636230e
ms.openlocfilehash: c31d13e03483f8632f17a526da75ebe8e21bccbf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364576"
---
# <a name="mfc-activex-controls-property-pages"></a>MFC ActiveX Denetimleri: Özellik Sayfaları

Özellik sayfaları, ActiveX denetim kullanıcısının ActiveX denetim özelliklerini görüntülemesine ve değiştirmesine olanak tanır. Bu özelliklere, denetim özelliklerini görüntülemek ve düzenlemek için özelleştirilmiş, grafiksel bir arabirim sağlayan bir veya daha fazla özellik sayfası içeren bir denetim özellikleri iletişim kutusu çağırılarak erişilir.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılmaması gereken eski bir teknolojidir. ActiveX'in yerini alabilecek modern teknolojiler hakkında daha fazla bilgi için [ActiveX Denetimleri'ne](activex-controls.md)bakın.

ActiveX denetim özelliği sayfaları iki şekilde görüntülenir:

- Denetimin Özellikleri fiili **(OLEIVERB_PROPERTIES)** çağrıldığında, denetim, denetimin özellik sayfalarını içeren bir modal özellik iletişim kutusunu açar.

- Kapsayıcı, seçili denetimin özellik sayfalarını gösteren kendi modeless iletişim kutusunu görüntüleyebilir.

Özellikler iletişim kutusu (aşağıdaki şekilde gösterilmiştir), geçerli özellik sayfasını görüntülemek için bir alan, özellik sayfaları arasında geçiş yapmak için sekmeler ve özellik sayfası iletişim kutusunu kapatma, yapılan değişiklikleri iptal etme veya activex denetimine hemen herhangi bir değişiklik uygulama gibi yaygın görevleri gerçekleştiren düğmeler koleksiyonundan oluşur.

![Circ3 için Özellikler iletişim kutusu](../mfc/media/vc373i1.gif "Circ3 için Özellikler iletişim kutusu") <br/>
Özellikler İletişim Kutusu

Bu makalede, ActiveX denetiminde özellik sayfalarını kullanmayla ilgili konular ele alınarak ele alınabilirsiniz. Bunlar:

- [ActiveX denetimi için varsayılan özellik sayfasını uygulama](#_core_implementing_the_default_property_page)

- [Özellik sayfasına denetim ekleme](#_core_adding_controls_to_a_property_page)

- [DoDataExchange işlevini özelleştirme](#_core_customizing_the_dodataexchange_function)

ActiveX denetiminde özellik sayfalarını kullanma hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [MFC ActiveX Denetimleri: Başka Bir Özel Özellik Sayfası Ekleme](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)

- [MFC ActiveX Denetimleri: Stok Özellik Sayfalarını Kullanma](../mfc/mfc-activex-controls-using-stock-property-pages.md)

ActiveX denetimi dışındaki bir MFC uygulamasında özellik sayfalarını kullanma hakkında bilgi için [Bkz.](../mfc/property-sheets-mfc.md)

## <a name="implementing-the-default-property-page"></a><a name="_core_implementing_the_default_property_page"></a>Varsayılan Özellik Sayfasını Uygulama

Denetim projenizi oluşturmak için ActiveX Denetim Sihirbazı'nı kullanırsanız, ActiveX Denetim Sihirbazı [COlePropertyPage Class'tan](../mfc/reference/colepropertypage-class.md)türetilen denetim için varsayılan özellik sayfası sınıfı sağlar. Başlangıçta, bu özellik sayfası boştur, ancak herhangi bir iletişim kutusu denetimi veya denetim kümesi ekleyebilirsiniz. ActiveX Denetim Sihirbazı varsayılan olarak yalnızca bir özellik sayfası sınıfı oluşturduğundan, Sınıf Görünümü kullanılarak ek özellik sayfası sınıfları (ayrıca `COlePropertyPage`türetilmiş) oluşturulmalıdır. Bu yordam hakkında daha fazla bilgi için, [Bkz. MFC ActiveX Denetimleri: Başka bir Özel Özellik Sayfası Ekleme.](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)

Bir özellik sayfası (bu durumda, varsayılan) uygulanması üç adımlı bir işlemdir:

#### <a name="to-implement-a-property-page"></a>Özellik sayfasını uygulamak için

1. Denetim `COlePropertyPage`projesine türetilmiş bir sınıf ekleyin. Proje ActiveX Denetim Sihirbazı kullanılarak oluşturulduysa (bu durumda olduğu gibi), varsayılan özellik sayfası sınıfı zaten vardır.

1. Özellik sayfası şablonuna denetim eklemek için iletişim düzenleyicisini kullanın.

1. Özellik sayfası `DoDataExchange` denetimi `COlePropertyPage`ile ActiveX denetimi arasında değer alışverişi yapmak için türetilmiş sınıfın işlevini özelleştirin.

Örneğin, aşağıdaki yordamlar basit bir denetim kullanır ("Örnek" olarak adlandırılır). Örnek ActiveX Denetim Sihirbazı kullanılarak oluşturuldu ve yalnızca stok Resim Yazısı özelliğini içerir.

## <a name="adding-controls-to-a-property-page"></a><a name="_core_adding_controls_to_a_property_page"></a>Özellik Sayfasına Denetim Ekleme

#### <a name="to-add-controls-to-a-property-page"></a>Özellik sayfasına denetim eklemek için

1. Denetim projeniz açıkken Kaynak Görünümü'ni açın.

1. **İletişim** dizini simgesini çift tıklatın.

1. IDD_PROPPAGE_SAMPLE iletişim kutusunu açın.

   ActiveX Denetim Sihirbazı, bu durumda Örnek, iletişim kimliğinin sonuna projenin adını ekler.

1. Seçili denetimi Araç Kutusu'ndan iletişim kutusu alanına sürükleyin ve bırakın.

1. Bu örnekiçin, metin etiketi denetimi "Caption :" ve IDC_CAPTION tanımlayıcılı bir edit kutusu denetimi yeterlidir.

1. Değişikliklerinizi kaydetmek için Araç Çubuğu'nu **Kaydet'i** tıklatın.

Kullanıcı arabirimi değiştirildigine göre, dünya sürme kutusunu Resim Yazılı özelliğine bağlatmışolmanız gerekir. Bu `CSamplePropPage::DoDataExchange` fonksiyon düzenleyerek aşağıdaki bölümde yapılır.

## <a name="customizing-the-dodataexchange-function"></a><a name="_core_customizing_the_dodataexchange_function"></a>DoDataExchange Işlevini Özelleştirme

Özellik sayfanız [CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) işlevi, özellik sayfası değerlerini denetimdeki özelliklerin gerçek değerleriyle bağlamanızı sağlar. Bağlantılar oluşturmak için, ilgili özellik sayfası alanlarını ilgili denetim özellikleriyle eşlemelisiniz.

Bu eşlemeler özellik sayfası **DDP_** işlevleri kullanılarak uygulanır. **DDP_** işlevleri, tek bir istisna dışında standart MFC iletişim kutularında kullanılan **DDX_** işlevleri gibi çalışır. Bir üye değişkene yapılan başvuruya ek olarak, **DDP_** işlevleri denetim özelliğinin adını alır. Aşağıda, bir özellik sayfasının işlevinde `DoDataExchange` tipik bir giriş yer alan bir giriş yer adatır.

[!code-cpp[NVC_MFC_AxUI#31](../mfc/codesnippet/cpp/mfc-activex-controls-property-pages_1.cpp)]

Bu işlev, işlevi kullanarak özellik sayfasının *m_caption* üye `DDP_TEXT` değişkenini Başlık'la ilişkilendirer.

Özellik sayfası denetimi ne sokulmuşsa, yukarıda açıklandığı gibi `DDP_Text` işlevi kullanarak özellik sayfası denetimi, IDC_CAPTION ve gerçek denetim özelliği Resim Yazısı arasında bir bağlantı kurmanız gerekir.

[Özellik Sayfaları,](../mfc/reference/property-pages-mfc.md) onay kutuları, radyo düğmeleri ve liste kutuları gibi diğer iletişim denetimi türleri için kullanılabilir. Aşağıdaki tabloda tüm özellik sayfası **DDP_** işlevleri ve amaçları listelemektedir:

### <a name="property-page-functions"></a>Özellik Sayfası Fonksiyonları

|İşlev adı|Bağlantı vermek için bu işlevi kullanın|
|-------------------|-------------------------------|
|`DDP_CBIndex`|Seçili dizenin dizini, denetim özelliğine sahip bir açılan kutuda.|
|`DDP_CBString`|Denetim özelliğine sahip açılan kutuda seçili dize. Seçili dize özelliğin değeriyle aynı harflerle başlayabilir, ancak tam olarak eşleşmesi gerekmez.|
|`DDP_CBStringExact`|Denetim özelliğine sahip açılan kutuda seçili dize. Seçili dize ve özelliğin dize değeri tam olarak eşleşmelidir.|
|`DDP_Check`|Kontrol özelliği olan bir onay kutusu.|
|`DDP_LBIndex`|Seçili dizenin dizini, denetim özelliğine sahip bir liste kutusunda.|
|`DDP_LBString`|Denetim özelliğine sahip bir liste kutusunda seçili dize. Seçili dize özelliğin değeriyle aynı harflerle başlayabilir, ancak tam olarak eşleşmesi gerekmez.|
|`DDP_LBStringExact`|Denetim özelliğine sahip bir liste kutusunda seçili dize. Seçili dize ve özelliğin dize değeri tam olarak eşleşmelidir.|
|`DDP_Radio`|Kontrol özelliği olan bir radyo düğmesi.|
|`DDP_Text`|Denetim özelliği olan metin.|

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Kontrolleri](../mfc/mfc-activex-controls.md)<br/>
[COlePropertyPage Sınıfı](../mfc/reference/colepropertypage-class.md)
