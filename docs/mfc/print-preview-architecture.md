---
description: 'Daha fazla bilgi edinin: baskı önizleme mimarisi'
title: Baskı Önizleme Mimarisi
ms.date: 11/04/2016
helpviewer_keywords:
- print preview [MFC], process
- previewing printing
- print preview [MFC], architecture
- printing [MFC], print preview
- print preview [MFC], modifications to MFC
ms.assetid: 0efc87e6-ff8d-43c5-9d72-9b729a169115
ms.openlocfilehash: 34dcd02b189a0065b34cff756596c5c5b1576dc6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205869"
---
# <a name="print-preview-architecture"></a>Baskı Önizleme Mimarisi

Bu makalede, MFC çerçevesinin baskı önizleme işlevini nasıl uyguladığı açıklanmaktadır. Ele alınan konular:

- [Baskı Önizleme işlemi](#_core_the_print_preview_process)

- [Baskı önizlemeyi değiştirme](#_core_modifying_print_preview)

Yazdırma önizlemesi ekran görüntüsünden ve yazıcıdan biraz farklıdır çünkü bir cihaza doğrudan bir görüntü çizerek, uygulama ekranı kullanarak yazıcının benzetimini yapmanız gerekir. Buna uyum sağlamak için, Microsoft Foundation Class Kitaplığı [CDC sınıfından](reference/cdc-class.md)türetilmiş özel (belgelenmemiş) bir sınıfı tanımlar `CPreviewDC` . Tüm `CDC` nesneler iki cihaz bağlamı içerir, ancak genellikle aynıdır. Bir `CPreviewDC` nesnesinde, bunlar farklıdır: ilki, sanal olan yazıcıyı temsil eder ve ikincisi çıktının gerçekten görüntülendiği ekranı temsil eder.

## <a name="the-print-preview-process"></a><a name="_core_the_print_preview_process"></a> Baskı Önizleme Işlemi

Kullanıcı, **Dosya** menüsünden Baskı Önizleme komutunu seçtiğinde, çerçeve bir `CPreviewDC` nesne oluşturur. Uygulamanız, yazıcı cihaz bağlamının bir özelliğini ayarlayan bir işlem gerçekleştirdiğinde, çerçeve ekran cihaz bağlamında benzer bir işlem de gerçekleştirir. Örneğin, uygulamanız yazdırma için bir yazı tipi seçerse, çerçeve, yazıcı yazı tipini taklit eden ekran görüntüsü için bir yazı tipi seçer. Uygulamanızın yazıcıya çıktı göndermesi gerektiğinde, Framework çıktıyı ekrana gönderir.

Baskı Önizleme, her birinin bir belge sayfasını çizdiği sırada yazdırma eyleminden de farklıdır. Yazdırma sırasında çerçeve, belirli bir sayfa aralığı işlenene kadar bir yazdırma döngüsüne devam eder. Baskı Önizleme sırasında, bir veya iki sayfa herhangi bir zamanda görüntülenir ve ardından uygulama bekler; Kullanıcı yanıt verene kadar başka sayfa görüntülenmiyor. Yazdırma önizlemesi sırasında, uygulamanın sıradan ekran görüntüleme sırasında olduğu gibi WM_PAINT iletilerine de yanıt vermesi gerekir.

Bir yazdırma işinin başlangıcında olduğu gibi, önizleme modu çağrıldığında [CView:: OnPreparePrinting](reference/cview-class.md#onprepareprinting) işlevi çağırılır. İşleve geçirilen [CPrintInfo yapısı](reference/cprintinfo-structure.md) yapısı, yazdırma önizlemesi işleminin belirli özelliklerini ayarlamak için ayarlayabileceğiniz çeşitli Üyeler içeriyor. Örneğin, *m_nNumPreviewPages* üyesini, belgeyi tek sayfalı veya iki sayfalı modda önizlemek isteyip istemediğinizi belirtmek için ayarlayabilirsiniz.

## <a name="modifying-print-preview"></a><a name="_core_modifying_print_preview"></a> Baskı önizlemeyi değiştirme

Baskı önizlemenin davranışını ve görünümünü kolay bir şekilde değiştirebilirsiniz. Örneğin, diğer işlerin yanı sıra şunları yapabilirsiniz:

- Baskı Önizleme penceresinin, belgenin herhangi bir sayfasına kolay erişim için bir kaydırma çubuğu görüntülemesine neden olur.

- Geçerli sayfada görüntüsünü başlatarak kullanıcının belgedeki konumunu korumasını sağlamak için baskı önizlemeye neden olur.

- Baskı Önizleme ve yazdırma için farklı başlatma gerçekleştirilmesine neden olur.

- Sayfa numaralarını kendi biçimlerinizin içinde görüntülemek için baskı önizlemeye neden olur.

Belgenin ne kadar süreyle olduğunu ve uygun değere çağrı yapıldığını biliyorsanız `SetMaxPage` , çerçeve bu bilgileri önizleme modunda, yazdırma sırasında da kullanabilir. Çerçeve belgenin uzunluğunu öğrendiğinde, önizleme penceresine bir kaydırma çubuğu sağlayabilir ve kullanıcının, önizleme modunda belge üzerinde geri ve ileri doğru bir şekilde gezinmesine olanak tanır. Belge uzunluğunu ayarlamadıysanız, çerçeve kaydırma kutusunu geçerli konumu belirtecek şekilde konumlandıramaz, bu nedenle çerçeve bir kaydırma çubuğu eklemez. Bu durumda, kullanıcının belge üzerinde gezinmek için Önizleme penceresinin denetim çubuğundaki sonraki sayfayı ve önceki sayfa düğmelerini kullanması gerekir.

Baskı Önizleme için,  `CPrintInfo` Normal yazdırma için hiçbir şekilde yapmasanız bile m_nCurPage üyesine bir değer atamanız yararlı olabilir. Sıradan yazdırma sırasında, bu üye çerçeveden görünüm sınıfına bilgi taşır. Bu, çerçeve hangi sayfanın yazdırılması gerektiğini görünüme söyler.

Buna karşılık, baskı önizleme modu başlatıldığında, *m_nCurPage* üye bilgileri karşı yönde taşır: görünümden çerçeveye. Framework, ilk olarak hangi sayfanın önizlenmesi gerektiğini öğrenmek için bu üyenin değerini kullanır. Bu üyenin varsayılan değeri 1 ' dir, bu nedenle belgenin ilk sayfası başlangıçta görüntülenir. `OnPreparePrinting`Bu üyeyi, baskı önizleme komutunun çağrıldığı sırada görüntülenen sayfanın numarasına ayarlamak için geçersiz kılabilirsiniz. Bu şekilde, uygulama normal görüntü modundan Baskı Önizleme moduna geçilerek kullanıcının geçerli konumunu korur.

Bazen, `OnPreparePrinting` bir yazdırma işi veya baskı önizleme için çağrılıp çağrıldığına bağlı olarak farklı başlatma işlemleri yapmak isteyebilirsiniz. Yapıda *m_bPreview* üye değişkenini inceleyerek bunu belirleyebilirsiniz `CPrintInfo` . Yazdırma önizlemesi çağrıldığında bu üye **true** olarak ayarlanır.

`CPrintInfo`Yapı Ayrıca, tek sayfalı ve çok sayfalı modlarındaki ekranın alt kısmında görüntülenecek dizeleri biçimlendirmek için kullanılan *m_strPageDesc* adlı bir üyeyi içerir. Varsayılan olarak, bu dizeler "sayfa *n*" ve "sayfa *n*  -  *m*" biçimindedir, ancak içinden *m_strPageDesc* değiştirebilir `OnPreparePrinting` ve dizeleri daha ayrıntılı bir şekilde ayarlayabilirsiniz. Daha fazla bilgi için bkz. *MFC başvurusu* Içindeki [CPrintInfo yapısı](reference/cprintinfo-structure.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Yazdırma ve baskı önizleme](printing-and-print-preview.md)<br/>
[Yazdırma](printing.md)<br/>
[CView sınıfı](reference/cview-class.md)<br/>
[CDC sınıfı](reference/cdc-class.md)
