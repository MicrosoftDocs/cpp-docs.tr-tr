---
title: 'Hızlı başlangıç: C/C++ için kod analizi'
description: Sık karşılaşılan kodlama sorunlarını ve kusurlarını algılamak için Visual Studio'da C++ kodu üzerinde statik çözümleme çalıştırın.
ms.date: 04/08/2020
ms.topic: conceptual
helpviewer_keywords:
- C/C++ code analysis
- code analysis, C/C++
ms.openlocfilehash: 43866564915ac84d227ccbf347280efe59e33351
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370581"
---
# <a name="quickstart-code-analysis-for-cc"></a>Hızlı başlangıç: C/C++ için kod analizi

C veya C++ kodunda düzenli olarak kod analizi çalıştırarak uygulamanızın kalitesini artırabilirsiniz. Kod çözümlemesi, sık karşılaşılan sorunları ve iyi programlama uygulama ihlallerini bulmanıza yardımcı olabilir. Ve, test yoluyla keşfedilmesi zor kusurları bulur. Uyarıları derleyici hatalarından ve uyarılardan farklıdır: Sorunlara neden olduğu bilinen belirli kod desenleri arar. Diğer bir deyişle, geçerli olan kod, ancak yine de, sizin veya kodunuzu kullanan diğer kişiler için sorunlar oluşturabilir.

## <a name="configure-rule-sets-for-a-project"></a>Proje için kural kümelerini yapılandırma

1. **Çözüm Gezgini'nde,** proje adı için kısayol menüsünü açın ve ardından **Özellikler'i**seçin.

1. İsteğe bağlı olarak, **Yapılandırma** ve **Platform** listelerinde yapı yapılandırmasını ve hedef platform'u seçin.

1. Proje seçili yapılandırmayı kullanarak her oluşturultuca kod çözümlemesi çalıştırmak için Yapı denetim kutusunda **Kod Çözümlemesini Etkinleştir'i** seçin. **Ayrıca, Analyze** menüsünü açıp *ProjectName'de* Çalıştır **Kod Çözümlemesi'ni** seçerek veya **Dosyada Kod Çözümlemesi'ni**el ile çalıştırabilirsiniz.

1. Kullanmak istediğiniz [kural kümesini](using-rule-sets-to-specify-the-cpp-rules-to-run.md) seçin veya özel bir [kural kümesi](using-rule-sets-to-specify-the-cpp-rules-to-run.md#to-create-a-rule-set-in-a-text-editor)oluşturun. LLVM/clang-cl kullanıyorsanız, Clang-Tidy analiz seçeneklerini yapılandırmak için [Visual Studio'da Clang-Tidy kullanma'ya](../code-quality/clang-tidy.md) bakın.

### <a name="standard-cc-rule-sets"></a>Standart C/C++ kural kümeleri

Visual Studio, yerel kod için bu standart kural kümelerini içerir:

| Kural Seti | Açıklama |
|--|--|
| **C++ Çekirdek Kontrol Aritmetik Kuralları** | Bu [kurallar, C++ Çekirdek Yönergeleri'ndeki aritmetik işlemlerle](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es-expressions-and-statements)ilgili denetimleri uygular. |
| **C++ Çekirdek Kontrol Sınırları Kuralları** | Bu kurallar [C++ Çekirdek Yönergeleri'nin Ciltler profilini](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile)uygular. |
| **C++ Çekirdek Kontrol Sınıf Kuralları** | Bu [kurallar, C++ Temel Yönergeleri'ndeki sınıflarla](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c-classes-and-class-hierarchies)ilgili denetimleri uygular. |
| **C++ Çekirdek Kontrol Eşzamanlılık Kuralları** | Bu [kurallar, C++ Temel Yönergeleri'ndeki eşzamanlılıkla](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#cpcon-concurrency)ilgili denetimleri uygular. |
| **C++ Çekirdek Kontrol Const Kuralları** | Bu kurallar [C++ Çekirdek Yönergeleri'nden const ile ilgili denetimleri](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con-constants-and-immutability)uygular. |
| **C++ Çekirdek Çek Beyan Kuralları** | Bu [kurallar, C++ Temel Yönergeleri'ndeki bildirimlerle](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#i-interfaces)ilgili denetimleri uygular. |
| **C++ Çekirdek Çek Enum Kuralları** | Bu [kurallar, C++ Çekirdek Yönergeleri'nden enumla ilgili denetimleri](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-enum)uygular. |
| **C++ Çekirdek Kontrolü Deneysel Kuralları** | Bu kurallar bazı deneysel kontroller toplar. Sonuç olarak, bu denetimlerin diğer kural kümelerine taşınmasını veya tamamen kaldırılmasını bekliyoruz. |
| **C++ Çekirdek Kontrol Fonksiyonu Kuralları** | Bu [kurallar, C++ Çekirdek Yönergeleri'ndeki işlevler](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f-functions)ile ilgili denetimleri uygular. |
| **C++ Çekirdek Kontrol GSL Kuralları** | Bu [kurallar, C++ Temel Yönergeleri'nden Yönergeler Destek Kitaplığı](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-gsl)ile ilgili denetimleri uygular. |
| **C++ Çekirdek Kontrol Ömür Boyu Kuralları** | Bu kurallar [C++ Çekirdek Yönergeleri'nin Ömür Boyu profilini](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#prolifetime-lifetime-safety-profile)uygular. |
| **C++ Çekirdek Denetimi Sahibi İşaretçisi Kuralları** | Bu kurallar, [C++ Temel&lt;&gt; Yönergeleri'nden sahibi T](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)ile ilgili kaynak yönetimi denetimlerini uygular. |
| **C++ Çekirdek Denetimi Ham İşaretçi Kuralları** | Bu [kurallar, C++ Çekirdek Yönergeleri'ndeki ham işaretçilerle](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)ilgili kaynak yönetimi denetimlerini uygular. |
| **C++ Çekirdek Kontrol Kuralları** | Bu [kurallar, C++ Çekirdek Yönergeleri'ndeki](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c-core-guidelines)denetimlerin bir alt kümesini uygular. Enum ve Deneysel kural kümeleri dışındaki Tüm C++ Çekirdek Denetimi kurallarını içerecek şekilde bu kural kümesini kullanın. |
| **C++ Çekirdek Denetimi Paylaşılan İşaretçi Kuralları** | Bu [kurallar, C++ Temel Yönergeleri'nden paylaşılan işaretçi semantiklerine sahip türlerle](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)ilgili kaynak yönetimi denetimlerini uygular. |
| **C++ Çekirdek Kontrol STL Kuralları** | Bu kurallar, [C++ Temel Yönergeleri'nden C++ Standart Şablon Kitaplığı (STL)](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-stdlib)ile ilgili denetimleri uygular. |
| **C++ Çekirdek Kontrol Stili Kuralları** | Bu [kurallar, C++ Temel Yönergeleri'ndeki ifadelerin ve deyimlerin](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es-expressions-and-statements)kullanımına ilişkin denetimleri uygular. |
| **C++ Çekirdek Kontrol Türü Kuralları** | Bu kurallar [C++ Çekirdek Yönergelerinin Tür profilini](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#prosafety-type-safety-profile)uygular. |
| **C++ Çekirdek Denetimi Benzersiz İşaretçi Kuralları** | Bu [kurallar, C++ Temel Yönergeleri'nden benzersiz işaretçi semantiklerine](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)sahip türleri ile ilgili kaynak yönetimi denetimlerini uygular. |
| **Eşzamanlılık Kontrol Kuralları** | Bu kurallar C++'da win32 eşzamanlılık deseni denetimleri kümesini uygular. |
| **Eşzamanlılık Kuralları** | C++ Temel Yönergeleri'nden **Eşzamanlılık Denetim Kuralları'na**eşzamanlılık kuralları ekler. |
| **Microsoft Yerel Minimum Kuralları** | Bu kurallar, olası güvenlik açıkları ve uygulama çökmeleri de dahil olmak üzere yerel kodunuzdaki en kritik sorunlara odaklanır. Bu kural kümesini, yerel projeleriniz için oluşturduğunuz herhangi bir özel kural kümesine eklemenizi öneririz. |
| **Microsoft Yerel Önerilen Kurallar** | Bu kurallar, yerel kodunuzdaki en kritik ve yaygın sorunlara odaklanır. Bu sorunlar, olası güvenlik açıklarını ve uygulama çökmelerini içerir. Bu kural kümesini, yerel projeleriniz için oluşturduğunuz herhangi bir özel kural kümesine eklemenizi öneririz. Bu kural kümesi Visual Studio Professional sürümü ve daha yüksek ile çalışmak üzere tasarlanmıştır. Microsoft Yerel Minimum **Kuralları'ndaki**tüm kuralları içerir. |

Visual Studio yönetilen kod için bu standart kural kümelerini içerir:

| Kural Seti | Açıklama |
|--|--|
| **Microsoft Temel Doğruluk Kuralları** | Bu kurallar, çerçeve API'lerinin kullanımında yapılan mantık hataları ve yaygın hatalara odaklanır. Önerilen minimum kurallar tarafından bildirilen uyarılar listesinde genişletmek için ayarlanan bu kuralı ekleyin. |
| **Microsoft Temel Tasarım Kılavuzu Kuralları** | Bu kurallar, kodunuzu kolay anlaşılır ve kullanımını kolaylaştırmak için en iyi uygulamaları zorlamaya odaklanır. Projeniz kitaplık kodu içeriyorsa veya kolayca korunabilen kod için en iyi uygulamaları uygulamak istiyorsanız bu kural kümesini ekleyin. |
| **Microsoft Genişletilmiş Doğruluk Kuralları** | Bu kurallar, bildirilen mantık ve çerçeve kullanım hatalarını en üst düzeye çıkarmak için temel doğruluk kurallarını genişletir. COM interop ve mobil uygulamalar gibi belirli senaryolara ekstra önem verilir. Bu senaryolardan biri projeniz için geçerliyse veya projenizde ek sorunlar bulmak için bu kural kümesini dahil etmeyi düşünün. |
| **Microsoft Genişletilmiş Tasarım Kılavuzu Kuralları** | Bu kurallar, bildirilen kullanılabilirlik ve sürdürülebilirlik sorunlarını en üst düzeye çıkarmak için temel tasarım kılavuzu kurallarını genişletir. Adlandırma yönergelerine ekstra önem verilir. Projeniz kitaplık kodu içeriyorsa veya sürdürülebilir kod yazmak için en yüksek standartları uygulamak istiyorsanız, bu kural kümesini dahil etmeyi düşünün. |
| **Microsoft Genelleştirme Kuralları** | Bu kurallar, uygulamanızdaki verilerin farklı dillerde, yerel bölgelerde ve kültürlerde kullanıldığında doğru şekilde görüntülenmesini engelleyen sorunlara odaklanır. Uygulamanız yerelleştirilmiş ve/veya küreselleştirilmişse bu kural kümesini ekleyin. |
| **Microsoft Yönetilen Minimum Kurallar** | Bu kurallar, Kod Analizi'nin en doğru olduğu kodunuzdaki en kritik sorunlara odaklanır.  Bu kurallar sayıca azdır ve yalnızca sınırlı Visual Studio sürümlerinde çalışmak üzere tasarlanmıştır.  Diğer Visual Studio sürümleriyle birlikte MinimumRecommendedRules.ruleset adresini kullanın. |
| **Microsoft Yönetilen Önerilen Kurallar** | Bu kurallar, kodunuzdaki en kritik sorunlara odaklanır. Bu sorunlar, olası güvenlik açıklarını, uygulama çökmelerini ve diğer önemli mantık ve tasarım hatalarını içerir. Projeleriniz için oluşturduğunuz herhangi bir özel kural kümesine bu kural kümesini eklemenizi öneririz. |
| **Microsoft Karışık (C++ /CLR) Minimum Kuralları** | Bu kurallar, Ortak Dil Çalışma Süresini destekleyen C++ projelerinizdeki en kritik sorunlara odaklanır. Bu sorunlar, olası güvenlik açıklarını, uygulama çökmelerini ve diğer önemli mantık ve tasarım hatalarını içerir. Ortak Dil Çalışma Süresini destekleyen C++ projeleriniz için oluşturduğunuz herhangi bir özel kural kümesine bu kural kümesini eklemenizi öneririz. |
| **Microsoft Mixed (C++ /CLR) Önerilen Kurallar** | Bu kurallar, Ortak Dil Çalışma Süresini destekleyen C++ projelerinizdeki en yaygın ve kritik sorunlara odaklanır. Bu sorunlar, olası güvenlik açıklarını, uygulama çökmelerini ve diğer önemli mantık ve tasarım hatalarını içerir. Bu kural kümesi Visual Studio Professional sürümünde ve daha yüksek sürümlerinde kullanılmak üzere tasarlanmıştır. |
| **Microsoft Güvenlik Kuralları** | Bu kural kümesi tüm Microsoft güvenlik kurallarını içerir. Bildirilen olası güvenlik sorunlarının sayısını en üst düzeye çıkarmak için ayarlanan bu kuralı ekleyin. |

Her kuralı eklemek için:

| Kural Seti | Açıklama |
|--|--|
| **Microsoft Tüm Kuralları** | Bu kural kümesi tüm kuralları içerir. Bu kural kümesinin çalıştırılması çok sayıda uyarı nın raporlanmasına neden olabilir. Kodunuzdaki tüm sorunların kapsamlı bir resmini elde etmek için bu kural kümesini kullanın. Projeleriniz için çalıştırmak için daha odaklanmış kural kümelerinden hangisinin en uygun olduğuna karar vermenize yardımcı olabilir. |

## <a name="run-code-analysis"></a>Kod çözümlemesi çalıştır

Project Properties iletişim kutusunun **Kod Analizi** sayfasında, projenizi her oluşturduğunuzda çalışacak kod çözümlemesi yapılandırabilirsiniz. Kod çözümlemesi'ni el ile de çalıştırabilirsiniz.

Bir çözüm üzerinde kod çözümlemesi çalıştırmak için:

- **Yapı** menüsünde, **Çözümde Kod Çözümle'yi Çalıştır'ı**seçin.

Bir projede kod çözümlemesi çalıştırmak için:

1. Çözüm Gezgini'nde projenin adını seçin.

1. **Yapı** menüsünde, Proje **Adı'nda Kod Çözümlemesi'ni** *Project Name*seçin.

Bir dosyada kod çözümlemesi çalıştırmak için:

1. Çözüm Gezgini'nde dosyanın adını seçin.

1. **Yapı** menüsünde **Dosyada Kod Analizini Çalıştır'ı** seçin veya **Ctrl+Shift+Alt+F7 tuşuna**basın.

   Proje veya çözüm derlenir ve kod çözümlemesi çalışır. Sonuçlar Hata Listesi penceresinde görünür.

## <a name="analyze-and-resolve-code-analysis-warnings"></a>Kod analizi uyarılarını analiz edin ve çözümleme

Hata Listesi penceresi, bulunan kod çözümleme uyarılarını listeler. Sonuçlar bir tabloda görüntülenir. Belirli bir uyarı hakkında daha fazla bilgi varsa, ilk sütun genişletme denetimi içerir. Sorun hakkında ek bilgi almak için ekranı genişletmek için ekranı seçin. Mümkün olduğunda, kod çözümlemesi uyarıya yol açan satır numaralarını ve çözümleme mantığını görüntüler.

Sorunun olası çözümleri de dahil olmak üzere uyarı hakkında ayrıntılı bilgi için, ilgili çevrimiçi yardım makalesini görüntülemek için Kod sütunundaki uyarı kimliğini seçin.

İmleci Visual Studio kod düzenleyicisinde uyarıya neden olan kod satırına taşımak için bir uyarıyı çift tıklatın. Veya seçili uyarıya Enter tuşuna basın.

Sorunu anladıktan sonra, sorunu kodunuzla çözebilirsiniz. Ardından, uyarının artık Hata Listesinde görünmediğinden emin olmak için kod çözümlemesini yeniden çalıştırın.

## <a name="create-work-items-for-code-analysis-warnings"></a>Kod analizi uyarıları için iş öğeleri oluşturma

Visual Studio içinden hataları günlüğe kaydetmek için iş öğesi izleme özelliğini kullanabilirsiniz. Bu özelliği kullanmak için Azure DevOps Server 'ın bir örneğine (eski adıyla Team Foundation Server) bağlanmanız gerekir.

### <a name="to-create-a-work-item-for-one-or-more-cc-code-warnings"></a>Bir veya daha fazla C/C++ kod uyarısı için iş öğesi oluşturmak için

1. Hata Listesinde, uyarıları genişletin ve seçin

1. Uyarılar için kısayol **menüsünde, İş Öğesi Oluştur'u**ve ardından iş öğesi türünü seçin.

1. Visual Studio, seçili uyarılar için tek bir iş öğesi oluşturur ve iş öğesini IDE'nin belge penceresinde görüntüler.

1. Ek bilgi ekleyin ve ardından **İş Öğesini Kaydet'i**seçin.

## <a name="search-and-filter-code-analysis-results"></a>Arama ve filtre kodu analizi sonuçları

Uzun uyarı iletileri listelerini arayabilir ve çoklu proje çözümlerinde uyarıları filtreleyebilirsiniz.

- **Uyarılara başlık veya uyarı kimliğine göre filtrelemek için**: Arama Hata Listesi kutusuna anahtar kelimeyi girin.

- **Uyarıları önem derecesine göre filtrelemek için**: Varsayılan olarak, kod çözümleme iletilerine **Uyarı'nın**önem derecesi atanır. Özel bir kural kümesinde bir veya daha fazla iletinin önem derecesini **Hata** olarak atayabilirsiniz. **Hata Listesi'nin** **Önem Derecesi** sütununda açılır ok ve ardından filtre simgesini seçin. Yalnızca ilgili önem derecesine atanan iletileri görüntülemek için **Uyarı** veya **Hata'yı** seçin. Tüm iletileri görüntülemek için **Tümünü Seç'i** seçin.

## <a name="see-also"></a>Ayrıca bkz.

- [C/C++ için kod analizi](../code-quality/code-analysis-for-c-cpp-overview.md)
