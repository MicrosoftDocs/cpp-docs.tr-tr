---
title: 'Hızlı Başlangıç: C/C++ için Kod Analizi'
description: Yaygın kodlama sorunlarını ve C++ kusurlarını algılamak Için Visual Studio 'daki kodda statik analiz çalıştırın.
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- C/C++ code analysis
- code analysis,C/C++
ms.openlocfilehash: 5ee8f702ddf489732f664ae73eed75b18dc46e86
ms.sourcegitcommit: 7bea0420d0e476287641edeb33a9d5689a98cb98
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77418783"
---
# <a name="quickstart-code-analysis-for-cc"></a>Hızlı başlangıç: C/C++ için kod analizi

Kod analizini, C veya C++ Code 'da düzenli olarak çalıştırarak uygulamanızın kalitesini artırabilirsiniz. Bu, yaygın sorunları, iyi programlama uygulaması ihlallerini veya test aracılığıyla bulmanın zor olduğu kusurları bulmanıza yardımcı olabilir. Geçerli olan, ancak yine de siz veya kodunuzu kullanan diğer kişilerin sorunlarına neden olabilir, belirli bir kod desenleri için Kod Analizi arar çünkü kod çözümleme uyarıları derleyici hataları ve Uyarıları farklılık gösterir.

## <a name="configure-rule-sets-for-a-project"></a>Bir proje için kural kümelerini yapılandırma

1. **Çözüm Gezgini**, proje adı için kısayol menüsünü açın ve ardından **Özellikler**' i seçin.

1. İsteğe bağlı olarak, **yapılandırma** ve **Platform** listelerinde, yapı yapılandırması ve hedef platform ' u seçin.

1. Projenin seçili yapılandırma kullanılarak oluşturulduğu her seferinde Kod analizini çalıştırmak için, **derlemede Kod analizini etkinleştir** onay kutusunu seçin. Ayrıca, **Çözümle** menüsünü açıp daha sonra *ProjectName* **üzerinde Kod analizini Çalıştır** ' ı seçip **dosya üzerinde Kod analizini**Çalıştır ' ı seçerek Kod analizini el ile de çalıştırabilirsiniz.

1. Kullanmak istediğiniz [kural kümesini](using-rule-sets-to-specify-the-cpp-rules-to-run.md) seçin veya [özel bir kural kümesi](using-rule-sets-to-specify-the-cpp-rules-to-run.md#to-create-a-rule-set-in-a-text-editor)oluşturun. LLVM/Clang-CL kullanılıyorsa bkz. Clang-Tidy analiz seçeneklerini yapılandırmak için [Visual Studio 'Da Clang-Tidy kullanma](../code-quality/clang-tidy.md) .

### <a name="standard-cc-rule-sets"></a>Standart C/C++ kural kümeleri

Visual Studio yerel kod için iki standart kural kümesi içerir:

|Kural kümesi|Açıklama|
|--------------|-----------------|
|Microsoft yerel en düşük önerilen kurallar|Bu kural kümesi, olası güvenlik delikleri ve uygulama kilitlenmeleri dahil olmak üzere yerel kodunuzda en kritik sorunlara odaklanır. Bu kural kümesini yerel projeleriniz için oluşturduğunuz herhangi bir özel kural kümesine dahil etmelisiniz.|
|Microsoft yerel önerilen kurallar|Bu kural kümesi, çok çeşitli sorunları ele alır. Microsoft yerel en düşük önerilen kuralların tüm kurallarını içerir.|

## <a name="run-code-analysis"></a>Kod analizini Çalıştır

Proje Özellikleri sayfasının kod analizi sayfasında, Kod analizini projenizi her oluşturduğunuzda çalışacak şekilde yapılandırabilirsiniz. Ayrıca, Kod analizini el ile de çalıştırabilirsiniz.

Bir çözümde Kod Analizi çalıştırmak için:

- **Build** menüsünde, **çözüm üzerinde Kod analizini Çalıştır**' ı seçin.

Bir projede kod analizini çalıştırmak için:

1. Çözüm Gezgini, projenin adını seçin.

1. **Yapı** menüsünde, *Proje adı* **üzerinde Kod analizini Çalıştır** ' ı seçin.

Kod analizini bir dosyada çalıştırmak için:

1. Çözüm Gezgini, dosyanın adını seçin.

1. **Build** menüsünde, **dosya üzerinde Kod analizini Çalıştır** ' ı seçin veya **CTRL + SHIFT + ALT + F7**tuşlarına basın.

   Proje veya çözüm derlenir ve kod analizi çalışır. Sonuçlar Hata Listesi görüntülenir.

## <a name="analyze-and-resolve-code-analysis-warnings"></a>Kod Analizi uyarılarını çözümleyin ve çözümleyin

Belirli bir uyarıyı çözümlemek için Hata Listesi uyarının başlığını seçin. Uyarı, sorunla ilgili ek bilgileri görüntüleyecek şekilde genişler. Mümkün olduğunda, kod analizi uyarıya yol gösteren satır numaralarını ve analiz mantığını görüntüler. Soruna yönelik olası çözümler dahil olmak üzere uyarı hakkında ayrıntılı bilgi için, ilgili çevrimiçi Yardım konusunu göstermek üzere uyarı KIMLIĞINI seçin.

Bir uyarı seçtiğinizde, uyarıya neden olan kod satırı, Visual Studio kod Düzenleyicisi 'nde vurgulanır.

Sorun anladıktan sonra kodunuzu çözebilirsiniz. Ardından, uyarının artık Hata Listesi göründüğünden ve Düzeltmelerinizin yeni bir uyarı gerçekleştirmediğinden emin olmak için kod analizini yeniden çalıştırın.

## <a name="suppress-code-analysis-warnings"></a>Kod Analizi uyarılarını gösterme

Kod Analizi uyarısı düzeltmemeyi ne zaman karar verebilirsiniz zamanlar vardır. Uyarı çözümleme sorunu kodunuzun tüm gerçek uygulamasında ortaya çıkacağını olasılık ile ilgili çok fazla değiştirilemeyen gerektirir karar verebilirsiniz. Veya uyarıda kullanılan analiz belirli bir içerik için uygun olduğunu düşündüğünüz. Uyarıları artık Hata Listesi görünmeyecek şekilde tek tek izleyebilirsiniz.

### <a name="to-suppress-a-warning"></a>Bir uyarıyı gizlemek için

1. Ayrıntılı bilgiler görüntülenmiyorsa, genişletilecek uyarının başlığını seçin.

1. Uyarının altındaki **Eylemler** bağlantısını seçin.

1. **Iletiyi Gizle** ' yi ve ardından **kaynak '** ı seçin.

   Bir ileti, kod satırı için uyarıyı belirten `#pragma warning (disable:[warning ID])` ekler.

## <a name="create-work-items-for-code-analysis-warnings"></a>Kod Analizi uyarıları için iş öğeleri oluşturma

Visual Studio içinden hataları günlüğe kaydetmek için çalışma öğesi izleme özelliğini kullanabilirsiniz. Bu özelliği kullanmak için bir Team Foundation Server örneğine bağlanmanız gerekir.

### <a name="to-create-a-work-item-for-one-or-more-cc-code-warnings"></a>Bir veya daha fazla C/C++ kod uyarısı için bir iş öğesi oluşturmak için

1. Hata Listesi, Genişlet ve uyarıları Seç

1. Uyarıların kısayol menüsünde, **Iş öğesi oluştur**' u seçin ve sonra iş öğesi türünü seçin.

1. Visual Studio Seçili uyarılar için tek bir iş öğesi oluşturur ve iş öğesini IDE 'nin bir belge penceresinde görüntüler.

1. Ek bilgileri ekleyin ve sonra **Iş öğesini kaydet**' i seçin.

## <a name="search-and-filter-code-analysis-results"></a>Kod analizi sonuçlarını arama ve filtreleme

Uzun listesi uyarı iletilerini arayabilir ve çoklu proje çözümlerinde uyarıları filtreleyebilirsiniz.

- **Uyarıları başlığa veya uyarı kimliğine göre filtrelemek için**: arama kutusuna anahtar sözcüğü girin.

- **Uyarıları önem derecesine göre filtrelemek için**: varsayılan olarak, kod analizi Iletilerine bir **Uyarı**önem derecesi atanır. Bir veya daha fazla iletinin önem derecesini özel bir kural kümesinde **hata** olarak atayabilirsiniz. **Hata listesi** **önem derecesi** sütununda, açılan oku ve ardından filtre simgesini seçin. Yalnızca ilgili önem derecesine atanmış iletileri göstermek için **Uyarı** veya **hata** ' ı seçin. Tüm iletileri göstermek için **Tümünü Seç ' i** seçin.

## <a name="see-also"></a>Ayrıca bkz.

- [C/için kod analiziC++](../code-quality/code-analysis-for-c-cpp-overview.md)
