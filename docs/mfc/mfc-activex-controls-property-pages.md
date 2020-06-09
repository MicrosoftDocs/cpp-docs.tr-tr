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
ms.openlocfilehash: 3d22085daa503a7c778111718445920f98b98a89
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615434"
---
# <a name="mfc-activex-controls-property-pages"></a>MFC ActiveX Denetimleri: Özellik Sayfaları

Özellik sayfaları, ActiveX denetim kullanıcısının ActiveX denetim özelliklerini görüntülemesine ve değiştirmesine izin verir. Bu özelliklere, denetim özelliklerini görüntülemek ve düzenlemekte özelleştirilmiş, grafik arabirimi sağlayan bir veya daha fazla özellik sayfası içeren bir denetim özellikleri iletişim kutusu çağırarak erişilir.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. ActiveX 'in yerini alan modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimleri](activex-controls.md).

ActiveX denetimi özellik sayfaları iki şekilde görüntülenir:

- Denetimin Özellikler fiili (**OLEIVERB_PROPERTIES**) çağrıldığında denetim, denetimin özellik sayfalarını içeren bir kalıcı özellik iletişim kutusu açar.

- Kapsayıcı, seçili denetimin özellik sayfalarını gösteren kendi kalıcı olmayan iletişim kutusunu görüntüleyebilir.

Özellikler iletişim kutusu (aşağıdaki şekilde gösterilmiştir), geçerli özellik sayfasını görüntülemek için bir alandır, özellik sayfaları arasında geçiş için sekmeler ve özellik sayfası iletişim kutusu kapatma, yapılan değişiklikleri iptal etme ya da ActiveX denetiminde yapılan değişiklikleri hemen uygulama gibi ortak görevleri gerçekleştiren bir düğme koleksiyonu.

![Circ3 için Özellikler iletişim kutusu](../mfc/media/vc373i1.gif "Circ3 için Özellikler iletişim kutusu") <br/>
Özellikler Iletişim kutusu

Bu makalede, bir ActiveX denetiminde özellik sayfalarını kullanmayla ilgili konular ele alınmaktadır. Bu güncelleştirmeler şunlardır:

- [Bir ActiveX denetimi için varsayılan özellik sayfasını uygulama](#_core_implementing_the_default_property_page)

- [Özellik sayfasına denetim ekleme](#_core_adding_controls_to_a_property_page)

- [DoDataExchange işlevini özelleştirme](#_core_customizing_the_dodataexchange_function)

ActiveX denetiminde Özellik sayfaları kullanma hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [MFC ActiveX Denetimleri: Başka Bir Özel Özellik Sayfası Ekleme](mfc-activex-controls-adding-another-custom-property-page.md)

- [MFC ActiveX Denetimleri: Stok Özellik Sayfalarını Kullanma](mfc-activex-controls-using-stock-property-pages.md)

ActiveX denetimi dışında bir MFC uygulamasında özellik sayfalarını kullanma hakkında bilgi için, bkz. [Özellik sayfaları](property-sheets-mfc.md).

## <a name="implementing-the-default-property-page"></a><a name="_core_implementing_the_default_property_page"></a>Varsayılan özellik sayfasını uygulama

Denetim projenizi oluşturmak için ActiveX Denetim Sihirbazı 'nı kullanırsanız, ActiveX Denetim Sihirbazı [COlePropertyPage sınıfından](reference/colepropertypage-class.md)türetilen denetim için varsayılan bir özellik sayfası sınıfı sağlar. Başlangıçta bu özellik sayfası boştur, ancak buna herhangi bir iletişim kutusu denetimi veya denetim kümesi ekleyebilirsiniz. ActiveX Denetim Sihirbazı varsayılan olarak yalnızca bir özellik sayfası sınıfı oluşturduğundan, Sınıf Görünümü kullanılarak ek özellik sayfası sınıflarının (Ayrıca öğesinden türetilmiş `COlePropertyPage` ) oluşturulması gerekir. Bu yordam hakkında daha fazla bilgi için bkz. [MFC ActiveX denetimleri: başka bir özel özellik sayfası ekleme](mfc-activex-controls-adding-another-custom-property-page.md).

Özellik sayfası uygulama (Bu durumda, varsayılan) üç adımlı bir işlemdir:

#### <a name="to-implement-a-property-page"></a>Özellik sayfası uygulamak için

1. `COlePropertyPage`Denetim projesine bir türetilmiş sınıf ekleyin. Proje ActiveX Denetim Sihirbazı kullanılarak oluşturulduysa (Bu durumda olduğu gibi), varsayılan özellik sayfası sınıfı zaten mevcuttur.

1. Özellik sayfası şablonuna herhangi bir denetim eklemek için iletişim düzenleyicisini kullanın.

1. `DoDataExchange` `COlePropertyPage` Özellik sayfası denetimi ve ActiveX denetimi arasındaki değerleri değiş tokuş etmek için-türetilmiş sınıfının işlevini özelleştirin.

Örneğin, aşağıdaki yordamlar basit bir denetim ("Sample" adlı) kullanır. Örnek, ActiveX Denetim Sihirbazı kullanılarak oluşturulmuştur ve yalnızca hisse senedi başlık özelliğini içerir.

## <a name="adding-controls-to-a-property-page"></a><a name="_core_adding_controls_to_a_property_page"></a>Özellik sayfasına denetim ekleme

#### <a name="to-add-controls-to-a-property-page"></a>Bir özellik sayfasına denetimler eklemek için

1. Denetim projem açıkken Kaynak Görünümü açın.

1. **Iletişim kutusu** Dizin simgesine çift tıklayın.

1. IDD_PROPPAGE_SAMPLE iletişim kutusunu açın.

   ActiveX Denetim Sihirbazı projenin adını iletişim kutusunun sonuna ekler, bu örnekte örneği.

1. Seçili denetimi araç kutusundan sürükleyin ve iletişim kutusu alanına bırakın.

1. Bu örnekte, bir metin etiketi denetimi "Caption:" ve IDC_CAPTION tanımlayıcısı olan bir düzenleme kutusu denetimi yeterlidir.

1. Değişikliklerinizi kaydetmek için araç çubuğunda **Kaydet** ' e tıklayın.

Artık Kullanıcı arabirimi değiştiriltiğine göre, düzenleme kutusunu açıklamalı alt yazı özelliği ile bağlamanız gerekir. Bu, işlevi düzenleyerek aşağıdaki bölümde yapılır `CSamplePropPage::DoDataExchange` .

## <a name="customizing-the-dodataexchange-function"></a><a name="_core_customizing_the_dodataexchange_function"></a>DoDataExchange Işlevini özelleştirme

Özellik sayfası [CWnd::D oDataExchange](reference/cwnd-class.md#dodataexchange) işlevi, özellik sayfası değerlerini denetimdeki özelliklerin gerçek değerleriyle bağlayabilmeniz için izin verir. Bağlantı kurmak için uygun özellik sayfası alanlarını ilgili denetim özellikleriyle eşlemeniz gerekir.

Bu eşlemeler özellik sayfası **ddp_** işlevleri kullanılarak uygulanır. **Ddp_** işlevler, standart MFC iletişim kutularında kullanılan **ddx_** işlevleri gibi çalışır ve tek bir istisnadır. Bir üye değişkenine başvuruya ek olarak, **ddp_** işlevleri denetim özelliğinin adını alır. `DoDataExchange`Bir özellik sayfası için işlevinde tipik bir giriş aşağıda verilmiştir.

[!code-cpp[NVC_MFC_AxUI#31](codesnippet/cpp/mfc-activex-controls-property-pages_1.cpp)]

Bu işlev, işlevini kullanarak özellik sayfasının *m_caption* üye değişkenini başlık ile ilişkilendirir `DDP_TEXT` .

Özellik sayfası denetimini ekledikten sonra, yukarıda açıklanan işlevi kullanarak özellik sayfası denetimi, IDC_CAPTION ve gerçek denetim özelliği, resim yazısı arasında bir bağlantı oluşturmanız gerekir `DDP_Text` .

[Özellik sayfaları](reference/property-pages-mfc.md) , onay kutuları, radyo düğmeleri ve liste kutuları gibi diğer iletişim kutusu denetim türleri için kullanılabilir. Aşağıdaki tabloda, tüm özellik sayfası **ddp_** işlevleri ve bunların amaçları listelenmiştir:

### <a name="property-page-functions"></a>Özellik sayfası Işlevleri

|İşlev adı|Bağlamak için bu işlevi kullanın|
|-------------------|-------------------------------|
|`DDP_CBIndex`|Seçilen dizenin Dizin bir denetim özelliği olan Birleşik giriş kutusunda.|
|`DDP_CBString`|Bir denetim özelliği olan Birleşik giriş kutusunda seçilen dize. Seçilen dize, özelliğin değeri ile aynı harfle başlayabilir, ancak tam olarak eşleşmesi gerekmez.|
|`DDP_CBStringExact`|Bir denetim özelliği olan Birleşik giriş kutusunda seçilen dize. Seçilen dize ve özelliğin dize değeri tam olarak eşleşmelidir.|
|`DDP_Check`|Denetim özelliğine sahip bir onay kutusu.|
|`DDP_LBIndex`|Bir denetim özelliği olan bir liste kutusunda seçilen dizenin dizini.|
|`DDP_LBString`|Denetim özelliği olan bir liste kutusunda seçili dize. Seçilen dize, özelliğin değeri ile aynı harfle başlayabilir, ancak tam olarak eşleşmesi gerekmez.|
|`DDP_LBStringExact`|Denetim özelliği olan bir liste kutusunda seçili dize. Seçilen dize ve özelliğin dize değeri tam olarak eşleşmelidir.|
|`DDP_Radio`|Denetim özelliğine sahip radyo düğmesi.|
|`DDP_Text`|Denetim özelliğine sahip metin.|

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)<br/>
[COlePropertyPage sınıfı](reference/colepropertypage-class.md)
