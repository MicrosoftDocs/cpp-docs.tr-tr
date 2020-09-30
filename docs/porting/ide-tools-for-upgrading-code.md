---
title: C++ kodunu yükseltmek için Visual Studio IDE araçları
description: Visual Studio 'daki C++ kod Düzenleyicisi ve kod çözümleme araçları, C++ kod tabanınızı modernleştirin etmenize yardımcı olur.
ms.date: 11/13/2019
ms.topic: conceptual
ms.openlocfilehash: d6368445d16232ff968b7116b0f0313e97aa144c
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91503761"
---
# <a name="visual-studio-ide-tools-for-upgrading-c-code"></a>C++ kodunu yükseltmek için Visual Studio IDE araçları

Visual Studio, eski C++ kodunu derleyici seçenekleri, kod analizi uyarıları ve hızlı düzeltmeler, hızlı bilgi ve gelişmiş kaydırma çubuğu gibi düzenleyici özellikleriyle yükseltmenize yardımcı olur. "Eski kod" terimi şu kategorilerden herhangi birine başvurur:

- Daha önce Microsoft C++ derleyicisi (MSVC) tarafından izin verilen ancak C++ standardına hiçbir şekilde bağlaneklenen kod.

   Eski uyumlu olmayan MSVC kodlarını yükseltmek için [/Permissive-](../build/reference/permissive-standards-conformance.md) derleyici seçeneğini açın. Uyumlu olmayan kullanımların tüm örnekleri, kod Düzenleyicisi 'nde kırmızı dalgalı çizgiler ile altı çizili olarak çizilir. **Hata listesi** penceresindeki hata iletileri hatanın nasıl düzeltileceğini gösteren bir öneri içerir. Belgelerdeki yardım sayfasına gitmek için hata kodu ' na tıklayın. Tüm hataların aynı anda düzeltilmesi pratik bir seçenektir, **izin veren** seçeneğini açıp, bazı hataları düzelterek ve sonra yeniden devre dışı bırakarak, aşamalı olmayan kodu yükseltebilirsiniz. Kod yeni geliştirmelerle derlenir ve geri dönüp kalan sorunları daha sonra giderebilirsiniz. Uyumlu olmayan MSVC kodu örnekleri için [/Permissive-](../build/reference/permissive-standards-conformance.md) sayfasına bakın.

- C++ standardının önceki bir sürümünde izin verilen ancak daha sonra kullanım dışı bırakılmış veya daha sonraki bir sürümde kaldırılan kod.

   Daha yeni bir dil standardına yükseltmek için, [C++ dil standardı](../build/reference/std-specify-language-standard-version.md) seçeneğini istenen standart olarak ayarlayın ve oluşturulan derleme hatalarını düzeltin. Genel olarak, dil standardını [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)olarak ayarlamayı öneririz. Daha yeni bir standarda yükseltme yaparken ortaya çıkan hatalar, **izin** verilen seçeneği kullanılırken oluşturulan hatalarla ilgili değildir.

- Tüm standart sürümlerine uyan, ancak modern C++ ' da artık en iyi uygulama olarak kabul edilen kod.

   Değişikliklerin önerildiği kodu belirlemek için [Kod analizini](../code-quality/code-analysis-for-c-cpp-overview.md)çalıştırın.

## <a name="open-and-convert-a-legacy-project"></a>Eski bir projeyi açma ve dönüştürme

Eski projeniz Visual Studio 'nun eski bir sürümünü temel alıyorsa, Visual Studio 2017 veya Visual Studio 2019 ' de açabilirsiniz. Visual Studio, en son derleyici ve IDE özellikleri desteğiyle otomatik olarak geçerli proje şemasına dönüştürür.

![Projeyi yükseltme](media/upgrade-dialog-v142.png "Projeyi yükseltme")

Daha fazla bilgi için bkz. [Visual Studio 'nun önceki sürümlerinden C++ projelerini yükseltme](upgrading-projects-from-earlier-versions-of-visual-cpp.md).

## <a name="search-the-code-base"></a>Kod tabanında arama

Bir kod tabanının yükseltilmesi genellikle birden çok dosya üzerinde arama içerir. Kod tabanınıza herhangi bir şey aramak için **CTRL + T** tuşlarına basarak **tüm aramaya git** kutusunu açın.

![Tümüne git](media/go-to-all.png "Tümüne git")

Arama kapsamını daraltmak için, 1 harfli filtrelerden birini, ardından bir boşluk ve aradığınız şeyi yazın.

## <a name="error-list"></a>Hata Listesi

İstenen C++ dili standardını ve diğer derleyici seçeneklerini ayarladıktan sonra (**Proje**  >  **özellikleri**  >  **genel**), projenizi derlemek için **CTRL + SHIFT + B** tuşlarına basın. Kodun çeşitli yerlerinde kırmızı dalgalı çizgiler biçiminde bazı hataları ve uyarıları görmeyi bekleyebilir. Hatalar **hata listesi**de görüntülenir. Belirli bir hata hakkında daha fazla bilgi için, belgelerindeki yardım sayfasına gitmek üzere hata koduna tıklayın. "C" ile başlayan hata kodları derleyici hatalarıdır. "MSB" ile başlayan kodlar, proje yapılandırmasıyla ilgili bir sorun olduğunu belirten MSBuild hatalarıdır.

![Hata Listesi 'de derleyici ve MSBuild hataları](media/compiler-error-list.png "Hata Listesi 'de derleyici ve MSBuild hataları")

## <a name="document-health-indicator"></a>Belge Durumu Göstergesi

Düzenleyicinin alt kısmındaki belge sistem durumu göstergesi, geçerli belgedeki hataların ve uyarıların sayısını gösterir ve bir uyarıdan/hatadan doğrudan bir sonrakine gitmenizi sağlar.

![Belge durumu göstergesi](media/document-health-indicator.png "Belge durumu göstergesi")

Birçok durumda, Visual Studio değişiklik geçmişi ve uyumluluk iyileştirmeleri hakkındaki belgelerde belirli bir hata hakkında daha fazla bilgi edinebilirsiniz.

- [C++ uygunluk iyileştirmeleri](../overview/cpp-conformance-improvements.md)
- [Visual C++ değişiklik geçmişi 2003-2015](visual-cpp-change-history-2003-2015.md)
- [Olası yükseltme sorunlarına genel bakış](overview-of-potential-upgrade-issues-visual-cpp.md)

## <a name="use-code-analysis-to-modernize-your-code"></a>Kodunuzu modernleştirin için kod analizini kullanın

' Yi yükseltirken, kod analizi yapmak için projenizde kod analizini çalıştırmanızı öneririz, bu sayede kodun en az Microsoft yerel önerilen kurallara uygun olması gerekir. Bu kurallar, Microsoft tarafından tanımlanan kuralların ve [C++ temel yönergeleri](https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines)bir alt kümesinin bir birleşimidir. Bunlara uyarak, yaygın olarak karşılaşılan hata kaynaklarını büyük ölçüde azaltabilir veya ortadan kaldıracaksınız ve aynı zamanda kodunuzun daha okunabilir ve bu nedenle bakımını daha kolay hale getirir. Microsoft yerel önerilen kurallarını kullanan kod analizi varsayılan olarak etkinleştirilmiştir. **Proje**  >  **özellikleri**  >  **Kod Analizi**altında ek kurallara izin verebilirsiniz. Kurallardan birini ihlal eden kod, uyarı olarak işaretlenir ve kod düzenleyicisinde yeşil dalgalı çizgi ile altı çizili olur. Sorunu açıklayan bir **QuickInfo** araç ipucunu görmek için dalgalı çizgi üzerine gelin.

![Kod Analizi araç ipucu](media/code-analysis-tooltip.png "Kod Analizi uyarısı")

Hangi uyarıların görüntülendiğini seçmek için **kod** sütunundaki filtre simgesine tıklayın.

![Hata Listesi 'de kod analizi filtreleri](media/code-analysis-filter.png "Hata Listesi 'de kod analizi filtreleri")

Kod Analizi hataları ve uyarıları, tıpkı derleyici hataları gibi **hata listesi** de görüntülenir.

![Hata Listesi 'de kod analizi uyarıları](media/code-analysis-error-list.png "Hata Listesi 'de kod analizi uyarıları")

Hangi kuralların etkin olduğunu değiştirebilir ve özel RuleSets 'ler oluşturabilirsiniz. Kod analizini kullanma hakkında daha fazla bilgi için bkz. [C/C++ Için kod analizi genel bakış](../code-quality/code-analysis-for-c-cpp-overview.md).

## <a name="use-quick-actions-to-modernize-code"></a>Kodu modernleştirin için hızlı eylemler kullanın

Kod Düzenleyicisi bazı yaygın öneriler için hızlı eylemler sağlar. Ampul simgesi görüntülendiğinde, kullanılabilir hızlı eylemleri görmek için üzerine tıklayabilirsiniz.

### <a name="convert-macros-to-constexpr-functions"></a>Makroları constexpr işlevlerine Dönüştür

Aşağıdaki görüntüde `AVERAGE` , varsayılan anlam renklendirme olan adlı makronun kullanımı gösterilmektedir. Görüntüde ayrıca fare imleci üzerine geldiğinde görüntülenen QuickInfo araç ipucu gösterilmektedir:

![QuickInfo makro genişletmesi](media/macro-expansion-quick-info.png "QuickInfo araç ipucu makro genişletmesi")

Modern C++ ' da makroların kullanılması önerilmez, Visual Studio, makroları işlevlere dönüştürmeyi kolaylaştırır **`constexpr`** :

1. Öğesine sağ tıklayın `AVERAGE` ve **Tanıma Git**' i seçin.
2. Screwdriver simgesine tıklayın ve **makroyu constexpr olarak Dönüştür** ' ü seçin.

   ![Constexpr için hızlı eylem makrosu](media/quick-action-macro-to-constexpr.png "Constexpr için hızlı eylem makrosu")

Makro aşağıda gösterildiği gibi dönüştürülür:

![constexpr işlevi](media/constexpr-function.png "constexpr işlevi")

Ve çağrısı `AVERAGE` artık işlev çağrısı olarak renklendirilir ve hızlı bilgi ipucu işlevin çıkarılan türünü gösterir:

![constexpr işlev çağrısı](media/constexpr-function-call.png "constexpr işlev çağrısı")

### <a name="initialize-variables"></a>Değişkenleri Başlat

Başlatılmamış değişkenler, önemli hatalara yol açabilecek rastgele değerler tutabilir. Kod analizi bu örnekleri işaretler ve düzenleyici bir hızlı eylem sağlar:

![Değişkeni Başlat](media/init-variable.png "Değişken hızlı eylemini Başlat")

### <a name="convert-to-raw-string-literal"></a>Ham dize sabit değerine dönüştürme

Ham dize değişmez değerleri, gömülü kaçış karakterlerine sahip dizelerden daha az hataya açıktır ve daha uygundur. Bir dizeye sağ tıklayın ve bir ham dize değişmez değerine dönüştürmek için **hızlı eylemler** ' i seçin.

![Ham dize sabit değeri](media/raw-string-literal.png "Ham dize sabit değeri")

Dize: olarak dönüştürülür `R"(C:\Users\bjarnes\demo\output.txt)"` .
