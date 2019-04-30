---
title: Form Tabanlı MFC Uygulaması Oluşturma
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfcforms.project
helpviewer_keywords:
- applications [MFC], forms-based
- forms-based applications [MFC]
ms.assetid: 048d2f7d-b60d-4386-ad8e-71d49af9c05e
ms.openlocfilehash: 6810a6c7fce91865a92d048129da29305e22abc1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372341"
---
# <a name="creating-a-forms-based-mfc-application"></a>Form Tabanlı MFC Uygulaması Oluşturma

Bir kullanıcının erişim ve veri değişikliği olabilir olanak tanıyan denetimler içeren bir iletişim kutusu biçimidir. Kullanıcı form seçimden seçer uygulama geliştirme isteyebilirsiniz. Yaygın olarak, form tabanlı bir uygulama tarafından tıklatın kullanıcı erişim formları sağlar **yeni** gelen **dosya** menüsü. Kullanıcılar için erişim sağlamaz bir iletişim kutusu tabanlı uygulama, bir **yeni** seçeneğini **dosya** menüsünde, form tabanlı bir uygulama da kabul edilir.

Tek Belgeli Arabirim (SDI), form tabanlı uygulamanın aynı anda çalıştırmak için belirli bir formu yalnızca bir örneğini sağlar. Farklı form, yeni bir formdan seçerek form tabanlı bir SDI uygulamasından aynı anda çalıştırmak mümkündür **yeni** seçeneğini **dosya** menüsü.

Bir çok Belgeli Arabirim (MDI), form tabanlı bir uygulama oluşturursanız uygulamayı formun birden çok örneğini desteklemek üzere mümkün olacaktır.

Birden çok en üst düzey belge desteği ile bir uygulama oluşturursanız, örtük ana belge için Masaüstü olduğu ve belgenin çerçeve uygulama istemci alanının sınırlı değildir. Birden fazla belge her kendi çerçevesi, menü ve görev çubuğu simgesi ile açabilirsiniz. Seçerseniz ancak sonraki belgeleri örneklerini tek tek kapatabilirsiniz **çıkış** seçeneğini **dosya** menüsünde uygulamanın ilk örneğinin tüm örneklerini kapatır.

SDI ve MDI birden çok en üst düzey belge uygulamaları tüm forms tabanlı ve belge/görünüm mimarisini kullanan olan.

Bir iletişim kutusu tabanlı, tanımına göre form tabanlı bir uygulamadır. Oluşturma ve erişim yöntemleri için kendi ek forms yönetmelisiniz belge/görünüm mimarisinin bir iletişim kutusu tabanlı uygulamaya kullanmaz.

Form tabanlı uygulamalar için temel sınıf [CFormView](../../mfc/reference/cformview-class.md). Uygulamanızı veritabanı desteğine sahip ardından türetilen herhangi bir sınıf belirleyebilirsiniz `CFormView`. Öğesinden türetilen herhangi bir pencereyi biçimidir `CFormView` veya devralınan herhangi bir sınıftan `CFormView`.

Gibi bir temel sınıf kullanıyor olsanız bile [CView](../../mfc/reference/cview-class.md), form tabanlı ile uygulamalarınızı daha sonra yapabilirsiniz [bir MFC sınıfı ekleme](../../mfc/reference/adding-an-mfc-class.md) türetilen `CFormView` ve denetimi **DocTemplate oluştur Kaynakları** onay kutusu [MFC Sınıf Sihirbazı](../../mfc/reference/document-template-strings-mfc-add-class-wizard.md).

Sihirbazı tamamladıktan sonra projenizi açar, ve seçtiyseniz `CFormView` (veya devralınan bir sınıf `CFormView`), temel sınıf olarak veya iletişim tabanlı bir uygulama oluşturduysanız, Visual C++ iletişim kutusu Düzenleyicisi açılır. Bu noktada, ilk formunuzu tasarlamak hazır olursunuz.

### <a name="to-begin-creating-a-forms-based-mfc-executable"></a>Bir form tabanlı MFC yürütülebilir oluşturmaya başlamak için

1. Bölümündeki yönergeleri izleyin [MFC uygulaması oluşturma](../../mfc/reference/creating-an-mfc-application.md).

1. MFC Uygulama Sihirbazı'nda [uygulama türü](../../mfc/reference/application-type-mfc-application-wizard.md) sayfasında **belge/görünüm mimarisi desteği** onay kutusu.

1. Seçin **tek belge**, **birden çok belge**, veya **birden çok en üst düzey belge**.

    > [!NOTE]
    >  Bir SDI, MDI veya birden çok en üst düzey belge arabirimi uygulaması, varsayılan olarak seçerseniz, `CView` uygulamanızın Görünümü'nde için temel sınıf olarak ayarlandığından [oluşturulan sınıflar](../../mfc/reference/generated-classes-mfc-application-wizard.md) Sihirbazı sayfası. Form tabanlı bir uygulama oluşturmak için seçmelisiniz `CFormView` uygulamanın görünüm için temel sınıf olarak. Sihirbaz form tabanlı bir uygulama için yazdırma desteği sağladığını unutmayın.

1. Diğer sihirbaz sayfalarında istediğiniz diğer proje seçeneklerini ayarlayın.

1. Tıklayın **son** çatı uygulama oluşturun.

Daha fazla bilgi için bkz.:

- [Türetilmiş görünüm sınıfları](../../mfc/derived-view-classes-available-in-mfc.md)

- [Belge/görünüm mimarisinin alternatifleri](../../mfc/alternatives-to-the-document-view-architecture.md)

- [Uygulama Tasarımı Seçimleri](../../mfc/application-design-choices.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)<br/>
[Form görünümleri](../../mfc/form-views-mfc.md)<br/>
[Dosya Gezgini Stilinde MFC Uygulaması Oluşturma](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)<br/>
[Web Tarayıcısı Stilinde MFC Uygulaması Oluşturma](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)
