---
title: Uygulamanızdaki Özellik Sayfalarını Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- dialog templates [MFC], property sheets
- dialog resources
- property pages [MFC], property sheets
- DoModal method property sheets
- AddPage method [MFC]
- property sheets, about property sheets
- Create method [MFC], property sheets
- CPropertyPage class [MFC], styles
ms.assetid: 240654d4-152b-4e3f-af7b-44234339206e
ms.openlocfilehash: 4fd68f57db082ab0b0da0e8248e0be239c63c99a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411532"
---
# <a name="using-property-sheets-in-your-application"></a>Uygulamanızdaki Özellik Sayfalarını Kullanma

Bir özellik sayfası kullanmak için aşağıdaki adımları tamamlayın:

1. Her bir özellik sayfası için bir iletişim şablonunu kaynağı oluşturun. Her çıkış yerleşim sayfası olarak tutarlı bir şekilde olabildiğince, böylece kullanıcı bir sayfadan diğerine geçiş göz önünde bulundurun.

   Tüm sayfalar için iletişim kutusu şablonları aynı boyutta olması gerekmez. Framework, özellik sayfaları için özellik sayfası ayırmak için ne kadar alan belirlemek için sayfanın en büyük boyutunu kullanır.

   Özellik sayfası iletişim şablon kaynağı oluşturduğunuzda, aşağıdaki stilleri Dialog özellikleri özellik sayfasında belirtmeniz gerekir:

   - Ayarlama **açıklamalı alt yazı** üzerinde düzenleme kutusu **genel** sayfasına bu sayfa için sekmesinde görünmesini istediğiniz metin.

   - Ayarlama **stili** liste kutusunu **stilleri** sayfasına **alt**.

   - Ayarlama **kenarlık** liste kutusunu **stilleri** sayfasına **ince**.

   - Emin **Titlebar** onay kutusunu **stilleri** sayfası seçili.

   - Emin **devre dışı bırakılmış** onay kutusunu **daha fazla stil** sayfası seçili.

1. Oluşturma bir [CPropertyPage](../mfc/reference/cpropertypage-class.md)-türetilmiş sınıf karşılık gelen her bir özellik sayfası iletişim şablonu. Bkz: [sınıf ekleme](../ide/adding-a-class-visual-cpp.md). Seçin `CPropertyPage` temel sınıf olarak.

1. Üye, bu özellik sayfası için değerleri tutması için değişkenleri oluşturun. Özelleştirilmiş bir iletişim kutusu bir özellik sayfası olduğu için üye değişkenleri için özellik sayfası ekleme işlemi tam olarak bir iletişim kutusu için üye değişkenleri ekleme aynıdır. Daha fazla bilgi için [iletişim kutusu denetimleri için üye değişkenleri tanımlama](../windows/defining-member-variables-for-dialog-controls.md).

1. Oluşturmak bir [CPropertySheet](../mfc/reference/cpropertysheet-class.md) , kaynak kodunuzdaki nesne. Genellikle, işlevi `CPropertySheet` özellik sayfası görüntüler komut işleyicisi nesnesi. Bu nesne tüm özellik sayfasını temsil eder. Bir kalıcı özellik sayfasını ile oluşturursanız [DoModal](../mfc/reference/cpropertysheet-class.md#domodal) işlevi, framework, varsayılan olarak üç komut düğmeleri sağlar: Tamam, iptal etmek ve uygulayın. Kalıcı olmayan özellik sayfaları ile oluşturulan hiçbir komut düğmeleri framework oluşturur [Oluştur](../mfc/reference/cpropertysheet-class.md#create) işlevi. Öğesinden bir sınıf türetin gerekmez `CPropertySheet` diğer denetimler (örneğin, bir önizleme penceresi) ekleyebilir veya kalıcı olmayan özellik sayfası görüntülemek istediğiniz sürece. Özellik sayfasını kapatmak için kullanılabilecek herhangi bir varsayılan denetim içermez çünkü kalıcı olmayan özellik sayfaları için bu adım gereklidir.

1. Özellik sayfasına eklenecek her sayfa için aşağıdakileri yapın:

   - Her biri için bir nesne oluşturmak `CPropertyPage`-türetilmiş bu işlemde daha önce oluşturduğunuz sınıfı.

   - Çağrı [CPropertySheet::AddPage](../mfc/reference/cpropertysheet-class.md#addpage) her sayfa için.

   Genellikle, oluşturan nesne `CPropertySheet` da oluşturur `CPropertyPage` Bu adımda nesneleri. Ancak, uygularsanız bir `CPropertySheet`-türetilmiş sınıf, katıştırabilirsiniz `CPropertyPage` nesneler `CPropertySheet` nesne ve çağrı `AddPage` her sayfadan için `CPropertySheet`-türetilmiş sınıf oluşturucu. `AddPage` ekler `CPropertyPage` nesne özelliği sayfanın sayfalar listesine ancak aslında bu sayfanın penceresini oluşturmaz. Bu nedenle, çağırmak için özellik sayfası pencerenin oluşturulmasını kadar beklenecek gerekli değil `AddPage`; çağırabilirsiniz `AddPage` özelliği sayfanın oluşturucudan.

   Özellik sayfasını, tek bir satır sığmayacak kadar çok daha fazla sekme bir özellik sayfası varsa, varsayılan olarak, sekmeleri birden çok satır yığın. Yığınlama devre dışı bırakmak için çağrı [CPropertySheet::EnableStackedTabs](../mfc/reference/cpropertysheet-class.md#enablestackedtabs) ayarlanan parametre ile **FALSE**. Çağırmalısınız `EnableStackedTabs` özellik sayfası oluşturduğunuzda.

1. Çağrı [CPropertySheet::DoModal](../mfc/reference/cpropertysheet-class.md#domodal) veya [Oluştur](../mfc/reference/cpropertysheet-class.md#create) özellik sayfasını görüntülemek için. Çağrı `DoModal` kalıcı bir iletişim kutusu olarak bir özellik sayfası oluşturmak için. Çağrı **Oluştur** modsuz iletişim kutusu olarak özellik sayfası oluşturma.

1. Özellik sayfaları ve özellik sayfasının sahibi arasında veri değişimi. Bu makalede açıklanan [veri değişimi](../mfc/exchanging-data.md).

MFC genel örnek özellik sayfalarını kullanma örneği için bkz. [PROPDLG](../overview/visual-cpp-samples.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özellik sayfaları](../mfc/property-sheets-mfc.md)
