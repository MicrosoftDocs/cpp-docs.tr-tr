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
ms.openlocfilehash: 5943edc22cd48ed10d152f72624467ff87104b96
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375942"
---
# <a name="print-preview-architecture"></a>Baskı Önizleme Mimarisi

Bu makalede, MFC çerçevesinin yazdırma önizleme işlevini nasıl uyguladığı açıklanmaktadır. Ele alınan konular:

- [Önizleme işlemini yazdırma](#_core_the_print_preview_process)

- [Yazdırma önizlemesini değiştirme](#_core_modifying_print_preview)

Yazdırma önizlemesi ekran ekranından ve yazdırmadan biraz farklıdır, çünkü uygulamanın doğrudan bir aygıta görüntü çizmek yerine ekranı kullanarak yazıcıyı simüle etmesi gerekir. Bunu karşılamak için, Microsoft Hazırlık Sınıf Kitaplığı [CDC Sınıfından](../mfc/reference/cdc-class.md)türetilen özel `CPreviewDC`(belgesiz) bir sınıf tanımlar. Tüm `CDC` nesneler iki aygıt bağlamı içerir, ancak genellikle aynıdır. Bir `CPreviewDC` nesnede, bunlar farklıdır: birincisi simüle edilen yazıcıyı, ikincisi ise çıktının gerçekte görüntülendiği ekranı temsil eder.

## <a name="the-print-preview-process"></a><a name="_core_the_print_preview_process"></a>Yazdırma Önizleme Süreci

Kullanıcı **Dosya** menüsünden Yazdır Önizleme komutunu seçtiğinde, çerçeve `CPreviewDC` bir nesne oluşturur. Uygulamanız yazıcı aygıtı bağlamının bir özelliğini belirleyen bir işlem gerçekleştirdiğinde, çerçeve ekran aygıtı bağlamında da benzer bir işlem gerçekleştirir. Örneğin, uygulamanız yazdırmak için bir yazı tipi seçerse, çerçeve yazıcı yazı tipini taklit eden ekran ekranı için bir yazı tipi seçer. Uygulamanız çıktıyı yazıcıya gönderdiğinde, çerçeve bunun yerine çıktıyı ekrana gönderir.

Yazdırma önizlemesi, her birinin bir belgenin sayfalarını çizdiği sırayla yazdırmaktan da farklıdır. Yazdırma sırasında, çerçeve belirli bir sayfa aralığı işlenene kadar yazdırma döngüsüne devam eder. Yazdırma önizlemesi sırasında, herhangi bir zamanda bir veya iki sayfa görüntülenir ve uygulama bekler; kullanıcı yanıt layana kadar başka sayfa görüntülenmez. Yazdırma önizlemesi sırasında uygulama, sıradan ekran ekranında olduğu gibi WM_PAINT iletilerine de yanıt vermelidir.

[CView::OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) işlevi, tıpkı bir yazdırma işinin başında olduğu gibi önizleme modu çağrıldığında çağrılır. İşleve geçirilen [CPrintInfo Yapısı](../mfc/reference/cprintinfo-structure.md) yapısı, yazdırma önizleme işleminin belirli özelliklerini ayarlamak için ayarlayabildiğiniz değerleri birkaç üye içerir. Örneğin, *m_nNumPreviewPages* üyeyi, belgeyi bir sayfa veya iki sayfa modunda önizlemek isteyip istemediğinizbelirtecek şekilde ayarlayabilirsiniz.

## <a name="modifying-print-preview"></a><a name="_core_modifying_print_preview"></a>Yazdırma Önizlemesini Değiştirme

Yazdırma önizlemesinin davranışını ve görünümünü çok kolay bir şekilde çeşitli şekillerde değiştirebilirsiniz. Örneğin, diğer şeylerin yanı sıra şunları yapabilirsiniz:

- Belgenin herhangi bir sayfasına kolay erişim için yazdırma önizleme penceresinin kaydırma çubuğunu görüntülemesine neden olun.

- Geçerli sayfada görüntülemeye başlayarak kullanıcının belgedeki konumunu korumak için yazdırma önizlemesine neden olun.

- Yazdırma önizleme ve yazdırma için farklı başlatmanın gerçekleştirilmesine neden olun.

- Sayfa numaralarını kendi biçimlerinizde görüntülemek için yazdırma önizlemesine neden olun.

Belgenin ne kadar uzun olduğunu `SetMaxPage` biliyorsanız ve uygun değerle arama yapıyorsanız, çerçeve bu bilgileri önizleme modunda ve yazdırma sırasında kullanabilir. Çerçeve belgenin uzunluğunu öğrendiğinde, önizleme penceresine bir kaydırma çubuğu sağlayarak kullanıcının önizleme modunda belge boyunca ileri geri sayfa atmasını sağlar. Belgenin uzunluğunu ayarlamadıysanız, çerçeve kaydırma kutusunu geçerli konumu belirtmek üzere konumlandıramaz, bu nedenle çerçeve kaydırma çubuğu eklemez. Bu durumda, kullanıcının belgeyi sayfalamak için önizleme penceresinin denetim çubuğundaki Sonraki Sayfa ve Önceki Sayfa düğmelerini kullanması gerekir.

Yazdırma önizlemesi için, normal yazdırma için bunu *m_nCurPage* asla `CPrintInfo`yapmazolsanız bile, m_nCurPage üyesine bir değer atamanız yararlı olabilir. Sıradan yazdırma sırasında, bu üye çerçeveden görünüm sınıfınıza bilgi taşır. Çerçeve, görünüme hangi sayfanın yazdırılması gerektiğini bu şekilde bildirir.

Bunun aksine, yazdırma önizleme modu başlatıldığında, *m_nCurPage* üye bilgileri ters yönde taşır: görünümden çerçeveye. Çerçeve, önce hangi sayfanın önizlemesi gerektiğini belirlemek için bu üyenin değerini kullanır. Bu üyenin varsayılan değeri 1'dir, bu nedenle belgenin ilk sayfası başlangıçta görüntülenir. Yazdır Önizleme `OnPreparePrinting` komutu çağrıldığı sırada görüntülenen sayfanın numarasına bu üyeyi ayarlamak için geçersiz kılınabilirsiniz. Bu şekilde, uygulama normal ekran modundan yazdırma önizleme moduna geçerken kullanıcının geçerli konumunu korur.

Bazen, yazdırma `OnPreparePrinting` işi veya yazdırma önizlemesi için çağrılıp çağrılmadığına bağlı olarak farklı başlatma gerçekleştirmek isteyebilirsiniz. Bunu, yapıdaki *m_bPreview* üye değişkeni `CPrintInfo` inceleyerek belirleyebilirsiniz. Yazdırma önizlemesi çağrıldığınızda bu üye **TRUE** olarak ayarlanır.

Yapı `CPrintInfo` da tek sayfa ve çoklu sayfa modlarında ekranın alt kısmında görüntülenen dizeleri biçimlendirmek için kullanılan *m_strPageDesc*adlı bir üye içerir. Varsayılan olarak bu dizeleri formu "Page *n*" ve "Pages *n* - *m*," ancak *içinde* `OnPreparePrinting` m_strPageDesc değiştirebilir ve daha ayrıntılı bir şey dizeleri ayarlayın. Daha fazla bilgi için *MFC Başvurusu'ndaki* [CPrintInfo Yapısı'na](../mfc/reference/cprintinfo-structure.md) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Yazdırma ve Yazdırma Önizlemesi](../mfc/printing-and-print-preview.md)<br/>
[Yazdırma](../mfc/printing.md)<br/>
[CView Sınıfı](../mfc/reference/cview-class.md)<br/>
[CDC Sınıfı](../mfc/reference/cdc-class.md)
