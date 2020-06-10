---
title: Belge-görünüm mimarisinin alternatifleri
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], applications without
- CDocument class [MFC], space requirements
- views [MFC], applications without
ms.assetid: 2c22f352-a137-45ce-9971-c142173496fb
ms.openlocfilehash: 66325d1ae087b29f59f37197fb8695504bbddbc6
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619750"
---
# <a name="alternatives-to-the-documentview-architecture"></a>Belge/Görünüm Mimarisinin Alternatifleri

MFC uygulamaları normalde bilgileri, dosya biçimlerini ve kullanıcılara verilerin görsel temsilini yönetmek için belge/görünüm mimarisini kullanır. Masaüstü uygulamalarının çoğu için, belge/görünüm mimarisi uygun ve verimli bir uygulama mimarisidir. Bu mimari, verileri görüntülemeden ayırır ve çoğu durumda uygulamanızı basitleştirir ve gereksiz kodu azaltır.

Ancak, belge/görünüm mimarisi bazı durumlarda uygun değildir. Aşağıdaki örnekleri göz önünde bulundurun:

- Windows için C dilinde yazılmış bir uygulama oluşturuyorsanız, uygulamanıza belge/görünüm desteği eklemeden önce bağlantı noktanızın tamamlanmasını isteyebilirsiniz.

- Hafif bir yardımcı program yazıyorsanız, belge/görünüm mimarisi olmadan yapabileceğinizi fark edebilirsiniz.

- Özgün kodunuz veri görüntüleme ile veri yönetimini zaten karıştırırsa, iki ayrı ayırmanız gerektiğinden, kodu belge/görünüm modeline taşımak efor değer vermez. Kodu olduğu gibi bırakmayı tercih edebilirsiniz.

Belge/görünüm mimarisini kullanmayan bir uygulama oluşturmak için MFC Uygulama Sihirbazı 'nın 1. adımında **belge/görünüm mimarisi desteği** onay kutusunun işaretini kaldırın. Ayrıntılar için [MFC Uygulama Sihirbazı](reference/mfc-application-wizard.md) 'na bakın.

> [!NOTE]
> MFC Uygulama Sihirbazı tarafından oluşturulan iletişim kutusu tabanlı uygulamalar belge/görünüm mimarisini kullanmaz, bu nedenle iletişim kutusu uygulama türünü seçerseniz **belge/görünüm mimarisi desteği** onay kutusu devre dışı bırakılır.

Visual C++ sihirbazları ve kaynak ve iletişim düzenleyicilerinin yanı sıra, diğer sihirbaz tarafından oluşturulan herhangi bir uygulamada olduğu gibi oluşturulan uygulamayla birlikte çalışın. Uygulama, araç çubuklarını, kaydırma çubuklarını ve bir durum çubuğunu destekleyebilir ve bir **hakkında** kutusu vardır. Uygulamanız herhangi bir belge şablonunu kaydetmez ve belge sınıfı içermez.

Oluşturulan uygulamanızın öğesinden türetilmiş bir görünüm sınıfı olduğunu unutmayın `CChildView` `CWnd` . MFC, uygulamanız tarafından oluşturulan çerçeve pencereleri içinde görünüm sınıfının bir örneğini oluşturur ve konumlandırır. MFC, uygulamanın içeriğini konumlandırmayı ve yönetmeyi basitleştiğinden bir görünüm penceresi kullanmayı hala zorluyor. `OnPaint`Bu sınıfın üyesine boyama kodu ekleyebilirsiniz. Kodunuzun, çerçeveye değil, görünüme kaydırma çubukları eklemesi gerekir.

MFC tarafından sunulan belge/görünüm mimarisi uygulamanın temel özelliklerinin çoğunu uygulamaktan sorumlu olduğundan, projenizdeki devamsızlığı, uygulamanızın birçok önemli özelliğini uygulamaktan sorumlu olduğunuz anlamına gelir:

- MFC Uygulama Sihirbazı tarafından sağlandığı gibi, uygulamanız için menü **Dosya** menüsünde yalnızca **Yeni** ve **Çıkış** komutlarını içerir. ( **Yeni** komut yalnızca MDI uygulamaları için desteklenir, belge/görünüm desteği olmayan SDI uygulamalarına değil.) Oluşturulan menü kaynağı, MRU (en son kullanılan) listesini desteklemez.

- **Dosya** menüsünde **Aç** ve **Kaydet** dahil olmak üzere, uygulamanızın destekleyeceği herhangi bir komut için işleyici işlevleri ve uygulamalar eklemeniz gerekir. MFC normalde bu özellikleri desteklemek için kod sağlar, ancak bu destek belge/görünüm mimarisine sıkı bir şekilde bağlanır.

- Uygulamanız için bir araç çubuğu istenirse, en az bir işlem olur.

Sihirbaz doğru bir MFC mimarisini garanti ettiğinden, belge/görünüm mimarisi olmadan uygulamalar oluşturmak için MFC Uygulama Sihirbazı 'Nı kullanmanız önemle tavsiye edilir. Ancak, Sihirbazı kullanmaktan kaçınmak gerekirse, kodunuzda belge/görünüm mimarisini atlamak için birkaç yaklaşım vardır:

- Belgeyi kullanılmayan bir appentrge olarak değerlendirin ve veri yönetimi kodunuzu, yukarıda önerildiği gibi View sınıfında uygulayın. Belge için ek yük görece düşüktür. Tek bir [CDocument](reference/cdocument-class.md) nesnesi, kendisi tarafından küçük miktarda ek yük doğurur ve `CDocument` temel sınıfların, [CCmdTarget](reference/ccmdtarget-class.md) ve [CObject](reference/cobject-class.md)'in küçük ek yüküne sahiptir. İkinci sınıfların her ikisi de küçüktür.

   Bildirildiği yer `CDocument` :

  - İki `CString` nesne.

  - Üç **bool**.

  - Bir `CDocTemplate` işaretçi.

  - `CPtrList`Belge görünümlerinin listesini içeren bir nesne.

  Ayrıca belge, belge nesnesi, görünüm nesneleri, bir çerçeve penceresi ve belge şablonu nesnesi oluşturmak için gereken süreyi gerektirir.

- Hem belgeyi hem de görünüm ' ü kullanılmayan uygulama olarak değerlendirin. Veri yönetimi ve çizim kodunuzu, görünüm yerine çerçeve penceresine koyun. Bu yaklaşım, C dili programlama modeline daha yakındır.

- Her seferinde oluşturmayı ortadan kaldırmak için, belge ve görünümü oluşturan MFC çerçevesinin parçalarını geçersiz kılın. Belge oluşturma işlemi bir çağrısıyla başlar `CWinApp::AddDocTemplate` . Uygulama sınıfınızın üye işlevinizden bu çağrıyı kaldırın `InitInstance` ve bunun yerine kendiniz bir çerçeve penceresi oluşturun `InitInstance` . Veri yönetimi kodunuzu çerçeve pencere sınıfınıza koyun. Belge/görünüm oluşturma işlemi [belge/görünüm oluşturma](document-view-creation.md)bölümünde gösterilmiştir. Bu daha fazla çalışmadır ve Framework 'ün daha derin bir şekilde anlaşılmasına gerek kalmaz, ancak tamamen belge/görünüm ek yükünü serbest bırakır.

[MFC: belgeler ve görünümler olmadan veritabanı sınıflarını kullanma](../data/mfc-using-database-classes-without-documents-and-views.md) , veritabanı uygulamaları bağlamında belge/görünüm alternatiflerine yönelik daha somut örnekler sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Belge/görünüm mimarisi](document-view-architecture.md)
