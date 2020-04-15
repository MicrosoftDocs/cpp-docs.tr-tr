---
title: Belge Görünümü Mimarisine Alternatifler
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], applications without
- CDocument class [MFC], space requirements
- views [MFC], applications without
ms.assetid: 2c22f352-a137-45ce-9971-c142173496fb
ms.openlocfilehash: 41af30d25d7ddb9e2bdbb7a0f7b86cb741ae1048
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370794"
---
# <a name="alternatives-to-the-documentview-architecture"></a>Belge/Görünüm Mimarisinin Alternatifleri

MFC uygulamaları normalde bilgileri, dosya biçimlerini ve verilerin kullanıcılara görsel temsilini yönetmek için belge/görünüm mimarisini kullanır. Masaüstü uygulamalarının çoğu için belge/görünüm mimarisi uygun ve verimli bir uygulama mimarisidir. Bu mimari verileri görüntülemeden ayırır ve çoğu durumda uygulamanızı basitleştirir ve gereksiz kodu azaltır.

Ancak, belge/görünüm mimarisi bazı durumlar için uygun değildir. Bu örnekleri göz önünde bulundurun:

- Windows için C ile yazılmış bir uygulamayı taşımanız gerekiyorsa, uygulamanız için belge/görünüm desteği eklemeden önce bağlantı noktanızı tamamlamak isteyebilirsiniz.

- Hafif bir yardımcı program yazıyorsanız, belge/görünüm mimarisi olmadan yapabileceğinizi görebilirsiniz.

- Özgün kodunuz zaten veri yönetimi ile veri görüntülemeyi karıştırıyorsa, kodu belge/görünüm modeline taşımak çabaya değmez, çünkü ikisini ayırmanız gerekir. Kodu olduğu gibi bırakmayı tercih edebilirsiniz.

Belge/görünüm mimarisini kullanmayan bir uygulama oluşturmak için MFC Uygulama Sihirbazı'nın adım 1'inde **Belge/Görünüm mimarisi destek** onay kutusunu temizleyin. Ayrıntılar için [MFC Uygulama Sihirbazı'na](../mfc/reference/mfc-application-wizard.md) bakın.

> [!NOTE]
> MFC Uygulama Sihirbazı tarafından üretilen iletişim tabanlı uygulamalar belge/görünüm mimarisini kullanmaz, bu nedenle iletişim uygulama türünü seçerseniz **Belge/Görünüm mimarisi destek** onay kutusu devre dışı bırakılır.

Visual C++ sihirbazlarının yanı sıra kaynak ve iletişim düzenleyicileri, oluşturulan uygulamayla tıpkı diğer Sihirbaztarafından oluşturulan uygulamalarda olduğu gibi çalışır. Uygulama araç çubuklarını, kaydırma çubuklarını ve durum çubuğunu destekleyebilir ve **Bir About** kutusu vardır. Uygulamanız herhangi bir belge şablonu kaydetmez ve belge sınıfı içermez.

Oluşturulan uygulamanızın `CChildView` `CWnd`bir görünüm sınıfı olduğunu unutmayın, türetilmiştir. MFC, uygulamanız tarafından oluşturulan çerçeve pencereleri içinde görünüm sınıfının bir örneğini oluşturur ve konumlandırıyor. MFC, uygulamanın içeriğini konumlandırmayı ve yönetmeyi basitleştirdiği için bir görünüm penceresi kullanmaya devam eder. Bu sınıfın üyesine `OnPaint` boyama kodu ekleyebilirsiniz. Kodunuz çerçeveyerine görünüme kaydırma çubukları eklemelidir.

MFC tarafından sağlanan belge/görünüm mimarisi bir uygulamanın temel özelliklerinin çoğunu uygulamaktan sorumlu olduğundan, projenizde bulunmaması, uygulamanızın birçok önemli özelliğini uygulamaktan sorumlu olduğunuz anlamına gelir:

- MFC Uygulama Sihirbazı tarafından sağlandığı gibi, uygulamanızın menüsünde **Dosya** menüsünde yalnızca **Yeni** ve **Çıkış** komutları yer almaktadır. (Yeni **New** komut yalnızca Belge/Görünüm desteği olmadan SDİ uygulamaları için değil, Yalnızca MDI uygulamaları için desteklenir.) Oluşturulan menü kaynağı BIR MRU (en son kullanılan) listesini desteklemez.

- **Dosya** menüsünde **Aç** ve **Kaydet** dahil olmak üzere uygulamanızın destekleyeceği komutlar için işleyici işlevleri ve uygulamaları eklemeniz gerekir. MFC normalde bu özellikleri desteklemek için kod sağlar, ancak bu destek belge/görünüm mimarisine sıkı sıkıya bağlıdır.

- Uygulamanız için araç çubuğu, eğer isterseniz, en az olacaktır.

Sihirbaz doğru bir MFC mimarisini garanti ettiği için belge/görünüm mimarisi olmadan uygulamalar oluşturmak için MFC Uygulama Sihirbazı'nı kullanmanız önerilir. Ancak, sihirbazı kullanmaktan kaçınmanız gerekiyorsa, kodunuzda belge/görünüm mimarisini atlayabilmeniz için birkaç yaklaşım aşağıda verilmelidir:

- Belgeyi kullanılmayan bir uzantı olarak değerlendirin ve yukarıda önerildiği gibi veri yönetim kodunuzu görünüm sınıfında uygulayın. Belgenin genel yükü nispeten düşüktür. Tek bir [CDocument](../mfc/reference/cdocument-class.md) nesnesi, 'temel sınıfların, `CDocument` [CCmdTarget](../mfc/reference/ccmdtarget-class.md) ve [CObject'in](../mfc/reference/cobject-class.md)küçük yükünün yanı sıra, tek başına küçük miktarda ek yükün de ek yüküne neden olur. İkinci sınıfların her ikisi de küçüktür.

   Beyan `CDocument`edilen:

  - İki `CString` nesne.

  - Üç **BOOL**s.

  - Bir `CDocTemplate` işaretçi.

  - Belgenin görünümlerinin listesini içeren bir `CPtrList` nesne.

  Ayrıca, belge, belge nesnesini, görünüm nesnelerini, çerçeve penceresini ve belge şablonnesnesini oluşturmak için gereken süreyi gerektirir.

- Hem belgeyi hem de kullanılmayan uzantıları görüntüleyin. Veri yönetiminizi ve çizim kodunuzu görünüm yerine çerçeve penceresine koyun. Bu yaklaşım C-dil programlama modeline daha yakındır.

- Belgeyi oluşturan ve bunları hiç oluşturmayı ortadan kaldırmak için görüntüleyen MFC çerçevesinin bölümlerini geçersiz kılın. Belge oluşturma işlemi `CWinApp::AddDocTemplate`bir çağrı ile başlar. Bu aramayı uygulama sınıfınızın `InitInstance` üye işlevinden ortadan kaldırın ve `InitInstance` bunun yerine kendinizde bir çerçeve penceresi oluşturun. Veri yönetim kodunuzu çerçeve penceresi sınıfınıza koyun. Belge/görünüm oluşturma işlemi [Belge/Görünüm Oluşturma'da](../mfc/document-view-creation.md)gösterilmiştir. Bu daha fazla iş ve çerçevenin daha derin bir anlayış gerektirir, ancak tamamen belge / görünüm yükü sizi kurtarır.

MFC [makalesi: Belge ve Görünüm olmadan Veritabanı Sınıfları](../data/mfc-using-database-classes-without-documents-and-views.md) kullanarak veritabanı uygulamaları bağlamında belge / görünüm alternatifleri daha somut örnekler verir.

## <a name="see-also"></a>Ayrıca bkz.

[Belge/Görünüm Mimarisi](../mfc/document-view-architecture.md)
