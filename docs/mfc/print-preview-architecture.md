---
title: Baskı Önizleme Mimarisi
ms.date: 11/04/2016
helpviewer_keywords:
- print preview [MFC], process
- previewing printing
- print preview [MFC], architecture
- printing [MFC], print preview
- print preview [MFC], modifications to MFC
ms.assetid: 0efc87e6-ff8d-43c5-9d72-9b729a169115
ms.openlocfilehash: ea80b67b3f6bb6980e4e8f7f12a967cb7bb5b6c7
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57261524"
---
# <a name="print-preview-architecture"></a>Baskı Önizleme Mimarisi

Bu makalede, MFC çerçevesi baskı önizlemeyi işlevselliğini nasıl uyguladığını açıklanmaktadır. Kapsanan konular şunlardır:

- [Baskı Önizleme işlemi](#_core_the_print_preview_process)

- [Baskı Önizleme ile değiştirme](#_core_modifying_print_preview)

Görüntüyü bir cihazda doğrudan çizim yerine, uygulama ekran kullanarak yazıcı benzetimini gerekir çünkü baskı önizlemeyi ekran görüntüsünü ve yazdırma biraz farklıdır. Buna uyum sağlamak için Microsoft Foundation Class Kitaplığı öğesinden türetilen özel (belgelenmemiş) bir sınıf tanımlar [CDC sınıfı](../mfc/reference/cdc-class.md)adlı `CPreviewDC`. Tüm `CDC` nesneleri içeren iki cihaz bağlamları, ancak genellikle bunlar aynıdır. İçinde bir `CPreviewDC` nesne farklı olduklarını: ilk benzetimli yazıcı ve ikinci üzerinde çıktı gerçekten görüntülendiği ekran temsil eder.

##  <a name="_core_the_print_preview_process"></a> Baskı Önizleme işlemi

Kullanıcı yazdırma önizleme komutu seçtiğinde **dosya** framework menüsünde, oluşturur bir `CPreviewDC` nesne. Uygulamanızı bir karakteristik yazıcı cihaz bağlamının ayarlar bir işlem gerçekleştirdiğinde, framework de benzer bir ekran cihaz bağlamı işlemi gerçekleştirir. Örneğin, uygulamanızın bir yazı tipi yazdırma için seçerse, framework yazıcı yazı tipi benzetim ekran için bir yazı tipi seçer. Uygulamanızı yazıcıya çıktı gönderir gibi her framework ekrana bunun yerine çıkış gönderir.

Baskı Önizleme ayrıca her bir belge sayfaları çizer sırada yazdırma farklıdır. Yazdırma sırasında belirli bir aralıkla sayfaların oluşturulmasını kadar framework yazdırma döngü devam eder. Baskı Önizleme sırasında herhangi bir anda bir veya iki sayfa görüntülenir ve uygulama bekler; kullanıcının yanıt verene kadar başka hiçbir sayfa görüntülenir. Baskı Önizleme sırasında uygulama sırasında normal ekran çalıştığı gibi WM_PAINT iletiler için ayrıca yanıtlamalıdır.

[CView::OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) çağrıldığında Önizleme modunu çağrıldığında bir yazdırma işinin başlangıcında olduğu gibi. [Cprintınfo yapısı](../mfc/reference/cprintinfo-structure.md) işleve geçirilen yapı değerleri baskı önizlemeyi işlemi belirli özelliklerini ayarlamak için ayarlayabileceğiniz birçok üye içerir. Örneğin, ayarlayabilirsiniz *m_nNumPreviewPages* üyesi tek sayfalık veya iki sayfa modu belgede Önizleme isteyip istemediğinizi belirtin.

##  <a name="_core_modifying_print_preview"></a> Baskı Önizleme ile değiştirme

Bunun yerine bir kolayca baskı önizlemede çeşitli şekillerde görünümünü ve davranışını değiştirebilirsiniz. Örneğin, diğerlerinin yanında yapabilecekleriniz:

- Herhangi bir belge sayfasına bir kolayca erişmek için kaydırma çubuğunu görüntülemek yazdırma önizleme penceresini neden.

- Baskı Önizleme, geçerli sayfa ekranına başlayarak kullanıcının belge içindeki konumunu korumak neden.

- Yazdırma ve baskı önizlemeyi gerçekleştirilen farklı başlatmanın neden.

- Sayfa numaralarını kendi biçimlerde görüntülemek için yazdırma önizleme neden.

Belgenin ne olduğunu bilmeniz ve çağrı `SetMaxPage` uygun değerle framework bu bilgileri önizleme modunda yazdırma sırasında yanı sıra kullanabilirsiniz. Belgenin uzunluğunu framework belirledikten sonra bir kaydırma çubuğu, kullanıcının belgeyi önizleme modunda aracılığıyla sürekli sayfasında izin ile Önizleme penceresini sağlayabilir. Belgenin uzunluğunu ayarlamadıysanız, kaydırma kutusunun kaydırma çubuğu framework eklemez şekilde geçerli konumunu göstermek için framework yerleştiremezsiniz. Bu durumda, kullanıcı bir sonraki sayfa ve önceki sayfa düğmelerini Önizleme pencerenin denetim çubuğundaki Belge aracılığıyla sayfasına kullanmanız gerekir.

Baskı Önizleme için bir değer atamak faydalı *m_nCurPage* üyesi `CPrintInfo`rağmen hiçbir zaman sıradan yazdırma için yapmanız. Sıradan yazdırma sırasında bu üye çerçeveden bilgi görünümü sınıfınıza taşır. Hangi sayfa yazdırılıp framework görünümü nasıl söyler budur.

Bunun aksine, yazdırma Önizleme modundan başlatıldığında, *m_nCurPage* üye izleme bilgilerini ters yönde: Framework görünümünden. Framework, hangi sayfa ilk önizlemesi belirlemek için bu üyenin değeri kullanır. Başlangıçta belgenin'ın ilk sayfasında görüntülenmesini sağlamak, bu üyenin varsayılan değeri 1 ' dir. Geçersiz kılabilirsiniz `OnPreparePrinting` Baskı Önizleme komutunu çağrıldığı zaman görüntülenmekte olan sayfa numarası için bu üye ayarlamak için. Bu şekilde, uygulama normal görüntüleme modunda Baskı Önizleme modunu taşırken kullanıcının geçerli konumunu korur.

Bazen isteyebilirsiniz `OnPreparePrinting` olup bir yazdırma işi ya da yazdırma önizleme adlandırılır bağlı olarak farklı başlatma gerçekleştirmek için. Bu incelenerek belirlenir *m_bPreview* üye değişkeni `CPrintInfo` yapısı. Bu üye kümesine **TRUE** baskı önizlemeyi zaman çağrılır.

`CPrintInfo` Yapı ayrıca adında bir üye içeriyor *m_strPageDesc*, tek sayfalık ve birden çok sayfalı modda ekranın alt kısmındaki görüntülenen dizeleri biçimlendirmek için kullanılır. Varsayılan olarak bu dize biçimindedir "sayfası *n*" ve "sayfaları *n* - *m*," ancak değiştirebilirsiniz *m_strPageDesc* gelen içinde `OnPreparePrinting` ve daha karmaşık bir şey için dizeleri ayarlayın. Bkz: [Cprintınfo yapısı](../mfc/reference/cprintinfo-structure.md) içinde *MFC başvurusu* daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca bkz.

[{1&gt;Yazdırma ve yazdırma önizleme&lt;1}](../mfc/printing-and-print-preview.md)<br/>
[Yazdırma](../mfc/printing.md)<br/>
[CView Sınıfı](../mfc/reference/cview-class.md)<br/>
[CDC Sınıfı](../mfc/reference/cdc-class.md)
