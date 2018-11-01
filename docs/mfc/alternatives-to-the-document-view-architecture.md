---
title: Belge-görünüm mimarisinin alternatifleri
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], applications without
- CDocument class [MFC], space requirements
- views [MFC], applications without
ms.assetid: 2c22f352-a137-45ce-9971-c142173496fb
ms.openlocfilehash: 5a9026ca400c3e7c403ff8f2b86f486bcde79cf8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569786"
---
# <a name="alternatives-to-the-documentview-architecture"></a>Belge/Görünüm Mimarisinin Alternatifleri

MFC uygulamaları, belge/görünüm mimarisinin normalde bilgiler, dosya biçimlerini ve verilerin kullanıcılara görsel temsilini yönetmek için kullanın. Masaüstü uygulamalarının çoğu için belge/görünüm mimarisinin bir uygun ve etkili uygulama mimaridir. Bu mimari görüntüleme alanından ve çoğu durumda veri ayırır, uygulamanızın basitleştirir ve gereksiz kod azaltır.

Ancak, belge/görünüm mimarisinin bazı durumlar için uygun değildir. Bu örnekler göz önünde bulundurun:

- Windows için C yazılmış bir uygulama bağlantı noktası oluşturma, belge/görünüm destek uygulamanıza eklemeden önce bağlantı noktası tamamlamak isteyebilirsiniz.

- Basit bir yardımcı program yazıyorsanız, belge/görünüm mimarisinin yapabileceğiniz bulabilirsiniz.

- Özgün kodunuzu zaten veri yönetimi verileriyle karıştırır, iki ayrı gerekir çünkü görüntüleme, taşıma belge/görünüm modeli için kod değer değil. Olduğu gibi kod bırakmayı tercih edebilirsiniz.

Belge/görünüm mimarisinin kullanmayan bir uygulama oluşturmak için Temizle **belge/görünüm mimarisi desteği** MFC Uygulama Sihirbazı 1. adımda onay kutusu. Bkz: [MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md) Ayrıntılar için.

> [!NOTE]
>  İletişim kutusu tabanlı uygulamaları MFC Uygulama sihirbazından oluşturulan belge/görünüm mimarisi kullanmayın böylece **belge/görünüm mimarisi desteği** iletişim uygulama türü seçerseniz onay kutusunu devre dışı.

Başka sihirbaz tarafından oluşturulan bir uygulama ile olduğu gibi kaynak ve iletişim düzenleyicileri yanı sıra, Visual C++ sihirbazları oluşturulan uygulama ile çalışır. Uygulama araç çubukları, kaydırma çubukları ve durum çubuğu destekleyebilir ve sahip bir **hakkında** kutusu. Uygulamanızı herhangi bir belge şablonları kaydedilmiyor ve belge sınıfı içermez.

Uygulamanızı oluşturulan bir görünüm sınıfı olduğuna dikkat edin `CChildView`, türetilmiş `CWnd`. MFC oluşturur ve uygulamanız tarafından oluşturulan çerçeve pencereleri içinde görünümü sınıfının bir örneğini yerleştirir. MFC kolaylaştırır konumlandırma ve uygulamanın içeriğini yönetmek için bir görünüm penceresini kullanarak yine de zorlar. Boyama kod ekleyebilirsiniz `OnPaint` bu sınıfın üyesi. Kodunuzu kaydırma çubukları görünümü yerine çerçeve eklemeniz gerekir.

MFC tarafından sağlanan belge/görünüm mimarisinin bir uygulamanın temel özelliklerin çoğu uygulamak için sorumlu olduğu için projenizdeki yokluğu uygulamanızın birçok önemli özellikleri uygulamak için sorumlu olduğunuz anlamına gelir:

- MFC Uygulama Sihirbazı tarafından sağlanan gibi yalnızca uygulamanız için bir menü içerir **yeni** ve **çıkış** komutlarını **dosya** menüsü. ( **Yeni** komutu yalnızca MDI uygulamaları için desteklenir, belge/görünüm olmadan SDI uygulamaları destekler.) Oluşturulan menü kaynağı (en son kullanılan) MRU Listesi desteklemez.

- İşleyici işlevleri ve uygulamaları dahil olmak üzere uygulamanızın destekleyeceği herhangi bir komut için eklemelisiniz **açık** ve **Kaydet** üzerinde **dosya** menüsü. Destek için belge/görünüm mimarisinin sıkı bir şekilde bağlıdır, ancak MFC normal olarak bu özellikleri destekleyecek kodu sağlar.

- İstenirse, araç, uygulamanız için en az olacaktır.

Sihirbaz doğru bir MFC mimarisi gönderilmesini sağladığından MFC Uygulama Sihirbazı belge/görünüm mimarisi olmadan uygulamalar oluşturmak için kullanmanız önerilir. Ancak, sihirbaz kullanmaktan kaçının gerekir, kodunuzda belge/görünüm mimarisi atlama için çeşitli yaklaşımlar şunlardır:

- Belge kullanılmayan bir appendage işle ve görünüm sınıfında, yukarıda önerilen veri yönetimi kodunuzu uygulayın. Belge için ek yükü oldukça düşüktür. Tek bir [CDocument](../mfc/reference/cdocument-class.md) nesne doğurur az miktarda ek yükü kendisi tarafından yanı sıra, küçük yükü `CDocument`ait temel sınıflar, [CCmdTarget](../mfc/reference/ccmdtarget-class.md) ve [CObject](../mfc/reference/cobject-class.md). İkinci sınıfların her ikisi de küçük.

   Bildirilen `CDocument`:

   - İki `CString` nesneleri.

   - Üç **BOOL**s.

   - Bir `CDocTemplate` işaretçi.

   - Bir `CPtrList` belgenin görünümleri listesini içeren bir nesne.

   Ayrıca, belgeyi belge nesnesi, görünüm nesnelerini, bir çerçeve penceresi ve belge şablonu nesnesi oluşturmak için gereken süreyi gerektirir.

- Belge ve görünüm kullanılmayan appendages kabul eder. Veri Yönetimi ve çizim kodu çerçeve penceresi görünümü yerine koyun. Bu yaklaşım, C dili programlama modelini daha yakın olur.

- Belge ve görünüm hiç oluşturma ortadan kaldırmak için oluşturduğunuz MFC çerçevesi bölümlerini geçersiz kılar. Bir çağrı ile belge oluşturma işlemi başlar `CWinApp::AddDocTemplate`. Uygulama sınıfınızın o çağrıdan ortadan `InitInstance` üye işlev ve bunun yerine, bir çerçeve penceresinde oluşturma `InitInstance` kendiniz. Veri Yönetimi kodunuzu, çerçeve penceresi sınıfında yerleştirin. Belge/görünüm oluşturma işlemi gösterilmiştir [belge/görünüm oluşturma](../mfc/document-view-creation.md). Bu daha fazla iş ve framework'ün derin bir anlayış gerektirir, ancak tamamen belge/görünüm yükü serbest bırakır.

Makaleyi [MFC: olmadan veritabanı sınıflarını belgeleri kullanarak ve görünümleri](../data/mfc-using-database-classes-without-documents-and-views.md) veritabanı uygulamaları bağlamında belge/görünüm alternatifleri daha somut örnekleri sağlar.

## <a name="see-also"></a>Ayrıca Bkz.

[Belge/görünüm mimarisi](../mfc/document-view-architecture.md)

