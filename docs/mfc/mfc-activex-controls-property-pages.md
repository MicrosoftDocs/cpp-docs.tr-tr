---
title: 'MFC ActiveX denetimleri: Özellik sayfaları | Microsoft Docs'
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DDP_ functions [MFC]
- MFC ActiveX controls [MFC], properties
- property pages [MFC], MFC ActiveX controls
- DoDataExchange method [MFC]
- OLEIVERB_PROPERTIES
- CPropertyPageDialog class [MFC]
- MFC ActiveX controls [MFC], property pages
ms.assetid: 1506f87a-9fd6-4505-8380-0dbc9636230e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 053a6dcf009fa65bbba9c864803db78866037196
ms.sourcegitcommit: a3c9e7888b8f437a170327c4c175733ad9eb0454
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2018
ms.locfileid: "50204424"
---
# <a name="mfc-activex-controls-property-pages"></a>MFC ActiveX Denetimleri: Özellik Sayfaları

Özellik sayfaları ActiveX denetimi özelliklerini görüntülemek ve değiştirmek bir ActiveX denetimi verin. Bu özellikler, görüntüleme ve denetim özelliklerini düzenleme için özelleştirilmiş, grafik bir arabirim sağlayan bir veya daha fazla özellik sayfaları içeren bir denetim özellikleri iletişim kutusu çağırarak erişilir.

>[!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. ActiveX yerine geçen modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimlerini](activex-controls.md).

ActiveX denetimi özellik sayfaları, iki şekilde görüntülenir:

- Olduğunda denetimin özellikler fiili (**OLEIVERB_PROPERTIES**) olan çağrılır, denetimin denetimin özellik sayfaları içeren bir kalıcı özellik iletişim kutusu açılır.

- Kapsayıcı seçilen denetimin özellik sayfalarını gösterir, kendi modsuz iletişim kutusu görüntüleyebilir.

(Aşağıdaki şekilde gösterilen) Özellikleri iletişim kutusu sekmeleri özellik sayfaları ve özellik sayfası iletişim kutusu kapatma gibi genel görevleri gerçekleştirmenize düğmelerinin koleksiyonunu arasında geçiş yapmak için geçerli özellik sayfasını görüntülemek için bir alan oluşur, yapılan tüm değişiklikler iptal etme veya hemen ActiveX denetimine değişiklikleri uygulanıyor.

![Özellikler iletişim kutusunu Circ3](../mfc/media/vc373i1.gif "vc373i1") Özellikleri iletişim kutusu

Bu makalede, bir ActiveX denetimi özellik sayfaları kullanmayla ilgili konular ele alınmaktadır. Bu güncelleştirmeler şunlardır:

- [Bir ActiveX denetimi için varsayılan özellik sayfası uygulama](#_core_implementing_the_default_property_page)

- [Bir özellik sayfasına denetim ekleme](#_core_adding_controls_to_a_property_page)

- [DoDataExchange işlevi özelleştirme](#_core_customizing_the_dodataexchange_function)

ActiveX denetiminde özellik sayfalarını kullanma hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [MFC ActiveX Denetimleri: Başka Bir Özel Özellik Sayfası Ekleme](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)

- [MFC ActiveX Denetimleri: Stok Özellik Sayfalarını Kullanma](../mfc/mfc-activex-controls-using-stock-property-pages.md)

Bir MFC uygulaması dışında bir ActiveX denetimi içinde özellik sayfalarını kullanma hakkında daha fazla bilgi için bkz: [özellik sayfalarını](../mfc/property-sheets-mfc.md).

##  <a name="_core_implementing_the_default_property_page"></a> Varsayılan özellik sayfası uygulama

ActiveX Denetim Sihirbazı'nı Denetim projenizi oluşturmak için kullandığınız öğesinden türetilen denetim için ActiveX Denetim Sihirbazı'nı varsayılan özellik sayfası sınıfının sağlar [COlePropertyPage sınıfı](../mfc/reference/colepropertypage-class.md). Başlangıçta, bu özellik sayfası boş olur, ancak herhangi bir iletişim kutusu denetimi veya denetimleri için ekleyebilirsiniz. Varsayılan olarak, ek özellik sayfası sınıfları ActiveX Denetim Sihirbazı'nı yalnızca bir özellik sayfası sınıfının oluşturduğundan (Ayrıca türetilen `COlePropertyPage`) Sınıf Görünümü kullanılarak oluşturulmalıdır. Bu yordamı hakkında daha fazla bilgi için bkz. [MFC ActiveX denetimleri: başka bir özel özellik sayfası ekleme](../mfc/mfc-activex-controls-adding-another-custom-property-page.md).

Uygulayan bir özellik sayfa (Bu durumda, varsayılan), üç adımlık bir işlemdir:

#### <a name="to-implement-a-property-page"></a>Özellik sayfası uygulamak için

1. Ekleme bir `COlePropertyPage`-türetilmiş sınıf için denetimi proje. Varsayılan özellik sayfası sınıfının, proje ActiveX Denetim Sihirbazı'nı (olduğu gibi bu durumda) kullanarak oluşturulmuş olsa bile, zaten mevcut.

1. İletişim kutusu Düzenleyicisi için özellik sayfası şablonu herhangi bir denetim eklemek için kullanın.

1. Özelleştirme `DoDataExchange` işlevi `COlePropertyPage`-türetilmiş sınıf özellik sayfası ve ActiveX denetimi arasındaki değerleri Exchange.

Örneğin ("Sample" adlı) basit bir denetim amacıyla, aşağıdaki yordamları kullanın. Örnek ActiveX Denetim Sihirbazı'nı kullanarak oluşturulmuş ve stok resim yazısı özelliğini içerir.

##  <a name="_core_adding_controls_to_a_property_page"></a> Bir özellik sayfasına denetim ekleme

#### <a name="to-add-controls-to-a-property-page"></a>Bir özellik sayfasına denetimler ekleme

1. Denetim projenize açık kaynak görünümünü açın.

1. Çift **iletişim** dizin simgesi.

1. IDD_PROPPAGE_SAMPLE iletişim kutusunu açın.

   ActiveX Denetim Sihirbazı'nı projesinin adı iletişim kimliği, bu durumda, örnek sonuna ekler.

1. Sürükleyin ve Seçili denetim iletişim kutusunun alanın araç kutusundan bırakın.

1. Bu örnekte, bir metin etiketi denetimi "resim yazısı:" ve IDC_CAPTION tanıtıcıya sahip bir düzenleme kutusu denetimi yeterli.

1. Tıklayın **Kaydet** yaptığınız değişiklikleri kaydetmek için araç çubuğunda.

Kullanıcı arabirimini değiştirildi, açıklamalı alt yazı özelliği ile düzenleme kutusuna bağlamanız gerekir. Aşağıdaki bölümde düzenleyerek yapıldığını `CSamplePropPage::DoDataExchange` işlevi.

##  <a name="_core_customizing_the_dodataexchange_function"></a> DoDataExchange işlevi özelleştirme

Özellik sayfanızı [CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) işlevi özellik sayfası değerleri denetiminde özelliklerinin gerçek değerlerle bağlamanıza olanak tanır. Bağlantıları kurmak için uygun özellik sayfasının alanları elemanının kendi kontrolünü özelliklerini eşlemeniz gerekir.

Özellik sayfasını kullanarak bu eşlemelerin uygulanan **DDP_** işlevleri. **DDP_** işlevler çalışır gibi **DDX_** işlevleri standart MFC iletişim kutuları, bir özel durumla birlikte kullanılır. Bir üye değişkenine başvuruya ek olarak **DDP_** işlevler denetim özelliğin adını alır. Aşağıdaki tipik bir giriştir `DoDataExchange` özellik sayfası için işlevi.

[!code-cpp[NVC_MFC_AxUI#31](../mfc/codesnippet/cpp/mfc-activex-controls-property-pages_1.cpp)]

Bu işlev özellik sayfanın ilişkilendirir *m_caption* üye değişkeni, açıklamalı alt yazıyla birlikte kullanarak `DDP_TEXT` işlevi.

Eklenen özellik sayfası denetimi yaptıktan sonra özellik sayfası denetimi, IDC_CAPTION ve gerçek denetim özelliği arasında bir bağlantı kurmak gereken kullanarak resim yazısı `DDP_Text` yukarıda açıklandığı gibi işlev.

[Özellik sayfaları](../mfc/reference/property-pages-mfc.md) radyo düğmeleri, onay kutuları gibi diğer iletişim denetim tipleri için kullanılabilir ve liste kutuları. Özellik sayfası kümesinin tamamını aşağıdaki tabloda listelenmiştir **DDP_** işlevleri ve bunların amacıyla:

### <a name="property-page-functions"></a>Özellik sayfası işlevleri

|İşlev adı|Bağlanmak için bu işlevi kullanın.|
|-------------------|-------------------------------|
|`DDP_CBIndex`|Seçili dizenin dizin bir birleşik giriş kutusu denetimi özelliğine sahip.|
|`DDP_CBString`|Seçili bir birleşik giriş kutusu denetimi özelliğine sahip dizesi. Seçili dizeyi özelliğinin değeri olarak aynı harfler ile başlayabilir, ancak tam olarak eşleşen yok.|
|`DDP_CBStringExact`|Seçili bir birleşik giriş kutusu denetimi özelliğine sahip dizesi. Seçili dizeyi ve özelliğinin dize değerini tam olarak eşleşmelidir.|
|`DDP_Check`|Onay kutusu denetimi özelliğine sahip.|
|`DDP_LBIndex`|Bir denetim özelliği ile bir liste kutusunda seçili dizenin dizini.|
|`DDP_LBString`|Bir denetim özelliği ile bir liste kutusunda seçili dize. Seçili dizeyi özelliğinin değeri olarak aynı harfler ile başlayabilir, ancak tam olarak eşleşen yok.|
|`DDP_LBStringExact`|Bir denetim özelliği ile bir liste kutusunda seçili dize. Seçili dizeyi ve özelliğinin dize değerini tam olarak eşleşmelidir.|
|`DDP_Radio`|Bir radyo düğmesi denetimi özelliğine sahip.|
|`DDP_Text`|Metin denetimi özelliğine sahip.|

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)<br/>
[COlePropertyPage Sınıfı](../mfc/reference/colepropertypage-class.md)
