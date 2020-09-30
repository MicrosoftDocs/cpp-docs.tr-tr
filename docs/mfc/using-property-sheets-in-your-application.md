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
ms.openlocfilehash: 789764c9af988135219bd710d4f8aec1cda9143a
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91504653"
---
# <a name="using-property-sheets-in-your-application"></a>Uygulamanızdaki Özellik Sayfalarını Kullanma

Uygulamanızda bir özellik sayfası kullanmak için aşağıdaki adımları izleyin:

1. Her özellik sayfası için bir iletişim şablonu kaynağı oluşturun. Kullanıcının bir sayfadan diğerine geçiş yapılabileceğini aklınızda bulundurun, bu nedenle her bir sayfayı mümkün olduğunca tutarlı şekilde düzenleyin.

   Tüm sayfalar için iletişim kutusu şablonlarının aynı boyutta olması gerekmez. Çerçeve, özellik sayfaları için özellik sayfasında ne kadar alan ayrılacağını belirlemekte en büyük sayfanın boyutunu kullanır.

   Bir özellik sayfası için iletişim şablonu kaynağı oluşturduğunuzda, Iletişim kutusu özellikleri özellik sayfasında aşağıdaki stilleri belirtmeniz gerekir:

   - **Genel** sayfasındaki **başlık** düzenleme kutusunu, bu sayfanın sekmesinde görünmesini istediğiniz metin olarak ayarlayın.

   - **Stiller** sayfasındaki **Stil** listesi kutusunu **alt**olarak ayarlayın.

   - **Stiller** sayfasındaki **Kenarlık** liste kutusunu **ölçülü**olarak ayarlayın.

   - **Stiller** sayfasındaki **başlıkkutusu** onay kutusunun seçili olduğundan emin olun.

   - **Daha fazla stil** sayfasındaki **devre dışı** onay kutusunun seçili olduğundan emin olun.

1. Her özellik sayfası iletişim kutusu şablonuna karşılık gelen bir [CPropertyPage](../mfc/reference/cpropertypage-class.md)ile türetilmiş sınıf oluşturun. Bkz. [sınıf ekleme](../ide/adding-a-class-visual-cpp.md). `CPropertyPage`Temel sınıf olarak öğesini seçin.

1. Bu özellik sayfası için değerleri tutmak üzere üye değişkenleri oluşturun. Özellik sayfası özelleştirilmiş bir iletişim kutusu olduğundan, bir özellik sayfasına üye değişkenleri ekleme işlemi, bir iletişim kutusuna üye değişkenleri eklemekle tamamen aynıdır. Daha fazla bilgi için bkz. [Iletişim kutusu denetimleri Için üye değişkenleri tanımlama](../windows/adding-editing-or-deleting-controls.md).

1. Kaynak kodunuzda bir [CPropertySheet](../mfc/reference/cpropertysheet-class.md) nesnesi oluşturun. Genellikle, `CPropertySheet` nesne, özellik sayfasını görüntüleyen komut için işleyicide oluşturursunuz. Bu nesne, tüm özellik sayfasını temsil eder. [DoModal](../mfc/reference/cpropertysheet-class.md#domodal) işlevi ile kalıcı bir özellik sayfası oluşturursanız, çerçeve varsayılan olarak üç komut düğmesi sağlar: Tamam, iptal et ve Uygula. Framework, Create işleviyle oluşturulan modsuz Özellik sayfaları için komut düğmeleri [oluşturmaz](../mfc/reference/cpropertysheet-class.md#create) . `CPropertySheet`Başka denetimler eklemek (örneğin, Önizleme penceresi) veya engelleyici olmayan bir özellik sayfasını görüntülemek istemediğiniz sürece bir sınıfı türetmeniz gerekmez. Bu adım, özellik sayfasını kapatmak için kullanılabilecek herhangi bir varsayılan denetim içermediğinden kalıcı olmayan özellik sayfaları için gereklidir.

1. Özellik sayfasına eklenecek her bir sayfa için aşağıdakileri yapın:

   - `CPropertyPage`Bu işlemde daha önce oluşturduğunuz her türetilmiş sınıf için bir nesne oluşturun.

   - Her sayfa için [CPropertySheet:: AddPage](../mfc/reference/cpropertysheet-class.md#addpage) öğesini çağırın.

   Genellikle, öğesini oluşturan nesnesi `CPropertySheet` `CPropertyPage` Bu adımdaki nesneleri de oluşturur. Ancak, bir `CPropertySheet` türetilmiş sınıf uygularsanız, `CPropertyPage` nesneleri `CPropertySheet` nesneye ekleyebilir ve `AddPage` `CPropertySheet` türetilmiş sınıf oluşturucusundan her sayfa için çağrı yapabilirsiniz. `AddPage``CPropertyPage`nesneyi Özellik sayfasının sayfa listesine ekler, ancak gerçekten Bu sayfa için pencere oluşturmaz. Bu nedenle, çağrılacak Özellik sayfası penceresinin oluşturulması bitinceye kadar beklemeniz gerekmez `AddPage` ; `AddPage` özellik sayfası oluşturucusundan çağrı yapabilirsiniz.

   Varsayılan olarak, bir özellik sayfasında, özellik sayfasının tek bir satırına sığacak kadar daha fazla sekme varsa, sekmeler birden çok satırda yığılır. Yığını devre dışı bırakmak için parametresi **false**olarak ayarlanmış [CPropertySheet:: enablestackedtab](../mfc/reference/cpropertysheet-class.md#enablestackedtabs) ' ı çağırın. Özellik sayfasını oluştururken ' i çağırmanız gerekir `EnableStackedTabs` .

1. Özellik sayfasını göstermek için [CPropertySheet::D oModal](../mfc/reference/cpropertysheet-class.md#domodal) veya [Create](../mfc/reference/cpropertysheet-class.md#create) ' i çağırın. `DoModal`Bir özellik sayfasını kalıcı iletişim kutusu olarak oluşturma çağrısı. Özellik sayfasını kalıcı olmayan bir iletişim kutusu olarak oluşturmak için **Oluştur** ' a çağrı yapın.

1. Özellik sayfaları ve özellik sayfasının sahibi arasındaki Exchange verileri. Bu, [verileri değiştirme](../mfc/exchanging-data.md)makalesinde açıklanmaktadır.

Özellik sayfalarını nasıl kullanacağınızı gösteren bir örnek için bkz. MFC genel örnek [propdlg](../overview/visual-cpp-samples.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özellik sayfaları](../mfc/property-sheets-mfc.md)
