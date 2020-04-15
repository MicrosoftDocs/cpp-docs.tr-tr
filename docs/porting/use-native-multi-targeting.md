---
title: Visual Studio’da eski projeleri oluşturmak için yerel çoklu sürüm paketi kullanma
ms.date: 10/25/2019
helpviewer_keywords:
- C++ native multi-targeting
- upgrading Visual C++ applications, retargeting
ms.assetid: b115aabe-a9dc-4525-90d3-367d97ea20c9
ms.openlocfilehash: 70acf3b5b78e0bc58555ef3f1f8e72e8aed74dd5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81353258"
---
# <a name="use-native-multi-targeting-in-visual-studio-to-build-old-projects"></a>Visual Studio’da eski projeleri oluşturmak için yerel çoklu sürüm paketi kullanma

Normalde Visual Studio'nun en son sürümünü yüklediğinizde projelerinizi güncelleştirmenizi öneririz. Projelerinizi ve kodunuzu güncelleştirmenin maliyeti genellikle yeni IDE, derleyici, kitaplıklar ve araçların avantajlarıyla dengelenir. Ancak, bazı projeleri güncelleştiremeyebileceğini biliyoruz. Bakım nedenlerinden dolayı yükseltilemediğiniz eski kitaplıklara veya platformlara bağlı ikili kutularınız olabilir. Kodunuz, daha yeni bir derleyiciye taşınırsanız kırılabilen standart olmayan dil yapıları kullanabilir. Kodunuz Visual C++'ın belirli bir sürümü için derlenen üçüncü taraf kitaplıklarını güvenebilir. Veya Visual C++'ın belirli bir eski sürümünü hedeflemesi gereken başkaları için kitaplıklar oluşturabilirsiniz.

Neyse ki, visual studio 2017 ve Visual Studio 2015'i kullanarak eski derleyici araç kümelerini ve kitaplıklarını hedefleyen projeler oluşturabilirsiniz. IDE'deki yeni özelliklerden yararlanmak için Visual Studio 2010, Visual Studio 2012, Visual Studio 2013 veya Visual Studio 2015 projesini yükseltmeniz gerekmez:

- Yeni C++ refactoring yetenekleri ve editör deneysel özellikleri
- Yeni Tanılama araçları hata ayıklama penceresi ve Hata Listesi penceresi
- Yenilenen kesme noktaları, özel durumlar penceresi ve yeni PerfTips
- Yeni kod gezinme ve arama araçları
- Yeni C++ Hızlı düzeltmeler ve Verimlilik Güç Araçları uzantıları.

Visual Studio 2008 projelerini de hedefleyebilirsiniz, ancak bunlar değiştirilmeden kullanılamaz. Ayrıntılar için **Visual Studio 2008 Talimatları** bölümüne bakın.

Visual Studio'nun en son sürümleri, yerel çok hedeflemeli ve yuvarlak tripping projeleri destekler. Yerel çoklu hedefleme, en son IDE'nin Visual Studio'nun önceki sürümleri tarafından yüklenen araç kümelerini kullanarak oluşturma yeteneğidir. Yuvarlama, en son IDE'nin projede herhangi bir değişiklik yapmadan önceki Bir IDE sürümü tarafından oluşturulan projeleri yükleme yeteneğidir. Visual Studio'nun en son sürümünü mevcut sürümünüzle yan yana yüklerseniz, projelerinizi oluşturmak için Mevcut sürümdeki derleyici ve araçlarla IDE'nin yeni sürümünü kullanabilirsiniz. Ekibinizin diğer üyeleri Visual Studio'nun eski sürümündeki projeleri kullanmaya devam edebilir.

Eski bir araç kümesi kullandığınızda, en son IDE özelliklerinin çoğundan yararlanabilir, ancak C++ derleyicisindeki, kitaplıklardaki ve yapı araçlarındaki en son gelişmelerden yararlanamazsınız. Örneğin, yeni dil uyumluluğu geliştirmelerini, yeni hata ayıklama ve kod çözümleme özelliklerini kullanamaz sınız veya en son araç kümesinin daha hızlı yapı işletini elde edemezsiniz. Eski araç kümeleriyle uyumsuz bazı IDE özellikleri de vardır. Örneğin, bellek profilcisinde tür bilgileri eksik olabilir ve yeniden düzenleme işlemi **Raw string literals'e dönüştür,** Visual Studio 2012 veya daha eski araç kümelerini kullandığınızda derlenmeyen C++11 uyumlu kod oluşturur.

## <a name="how-to-use-native-multi-targeting-in-visual-studio"></a>Visual Studio'da yerel çoklu hedefleme nasıl kullanılır?

Visual Studio'yu eski sürümünizle yan yana yükledikten sonra, mevcut projenizi Visual Studio'nun yeni sürümünde açın. Proje yüklendiğinde Visual Studio, en son C++ derleyicisini ve kitaplıklarını kullanmak için yükseltme yapmak isteyip istemediğinizi sorar. Projenin eski derleyiciyi ve kitaplıkları tutmasını istediğinizden, **İptal** düğmesini seçin.

Visual Studio projenizi yükseltme konusunda ısrarcıdır. Projeyi her yüklediğinizde yükseltme iletişim kutusunu görmekten kaçınmak için, projelerinizde veya .props veya .targets dosyalarında aşağıdaki özelliği tanımlayabilirsiniz:

`<VCProjectUpgraderObjectName>NoUpgrade</VCProjectUpgraderObjectName>`

Projelerinizi yükseltmek istediğinizde bu özelliği kaldırmanız gerekir.

Yükseltme yapmamayı seçerseniz, Visual Studio çözüm veya proje dosyalarınızda hiçbir değişiklik yapmaz. Projeyi oluşturduğunuzda, oluşturulan ikililer Visual Studio'nun eski sürümüyle oluşturduğunuz ikililerle tamamen uyumludur. Bunun nedeni Visual Studio'nun aynı C++ derleyicisini kullanması ve eski IDE'nizin gönderildiği kitaplıkları birbirine bağlatmamasıdır. Bu nedenle yükseltme iletişim kutusu, **İptal**seçeneğini seçerseniz eski Visual Studio sürümünü yüklü tutmanız için sizi uyarır.

## <a name="instructions-for-visual-studio-2008"></a>Görsel Stüdyo 2008 Için Talimatlar

Visual Studio 2008 **VcBuild**denilen C++ için kendi özel yapı sistemi vardı. Visual Studio 2010'dan itibaren Visual Studio C++ projeleri **MSBuild'i**kullanacak şekilde değiştirildi. Bu, ister kalıcı olarak yükseltme ister çok hedeflemeli olun, Visual Studio 2008 projelerinizi Visual Studio'nun en son sürümünde oluşturmak için bir güncelleştirme adımından geçmeniz gerektiği anlamına gelir. Güncelleştirilmiş projeniz, Visual Studio 2008 IDE kullanılarak oluşturulan ikili lerle tam uyumlu ikili ler oluşturmaya devam etmektedir.

İlk olarak, Visual Studio geçerli sürümüne ek olarak, Visual Studio 2008 ile aynı bilgisayara Visual Studio 2010 yüklemeniz gerekir. Yalnızca Visual Studio 2010, Visual Studio 2008 projelerini hedeflemek için gereken **MSBuild** komut dosyalarını yükler.

Ardından, Visual Studio 2008 çözümünüzü ve projelerinizi Visual Studio'nun geçerli sürümüne güncellemeniz gerekir. Yükseltmeden önce projelerinizin ve çözüm dosyalarınızın bir yedeklemesini oluşturmanızı öneririz. Yükseltme işlemini başlatmak için, Visual Studio'nun geçerli sürümünde çözümü açın. Yükseltme istemini aldığınızda, sunulan bilgileri gözden geçirin ve yükseltmeyi başlatmak için **Tamam'ı** seçin. Çözümde birden fazla proje varsa, sihirbazı güncelleştirmelisiniz yeni .vcxproj proje dosyaları varolan .vcproj dosyaları ile yan yana oluşturur. Orijinal .sln dosyasının bir kopyasına da sahip olduğunuz sürece, yükseltmenin mevcut Visual Studio 2008 projeleriniz üzerinde başka bir etkisi yoktur.

> [!NOTE]
> Aşağıdaki adımlar yalnızca çok hedeflemesenaryoları için geçerlidir. Projeyi kalıcı olarak daha sonraki bir araç kümesine yükseltmeyi planlıyorsanız, bir sonraki adımınız projeyi kaydetmek, Visual Studio 2019'da açmak ve orada görünen yapı sorunlarını gidermektir.

Yükseltme tamamlandığında, günlük raporunda projelerinizden herhangi biri için hatalar veya uyarılar varsa, bunları dikkatle inceleyin. **VCBuild'ten** **MSBuild'e** dönüşüm sorunlara neden olabilir. Raporda listelenen eylem öğelerini anladığınızdan ve uyguladığınıza emin olun. Yükseltme günlüğü raporu ve **VCBuild'i** **MSBuild'e**dönüştürürken oluşabilecek sorunlar hakkında daha fazla bilgi için bu [C++ Native Multi-Targeting](https://blogs.msdn.microsoft.com/vcblog/2009/12/08/c-native-multi-targeting/) blog gönderisine bakın.

Proje yükseltmesi tamamlandığında ve günlük dosyasındaki tüm sorunları düzelttiğinizde, çözümünüz aslında en son araç kümesini hedefler. Son adım olarak, Visual Studio 2008 araç kümesini kullanmak için çözümdeki her projenin özelliklerini değiştirin. Visual Studio'nun geçerli sürümüne yüklenen çözümle, çözümdeki her proje için Project **Property Pages** iletişim kutusunu açın: **Solution Explorer'da** projeye sağ tıklayın ve ardından **Özellikler'i**seçin. Özellik **Sayfaları** iletişim kutusunda, **Yapılandırma** açılır değerini Tüm Yapılandırmalar olarak **değiştirin.** **Yapılandırma Özellikleri'nde** **Genel'i**seçin ve platform **araç setini** **Visual Studio 2008 (v90)** olarak değiştirin.

Bu değişiklikten sonra, Visual Studio 2008 derleyicisi ve kitaplıkları Visual Studio'nun geçerli sürümünde çözüm oluşturduğunuzda proje ikilileri oluşturmak için kullanılır.

## <a name="install-an-older-visual-studio-toolset"></a>Eski bir Visual Studio araç seti yükleme

Yükseltme yapmak istemediğiniz veya yükseltmek istemediğiniz eski bir Visual Studio C++ projeniz olabilir, ancak projenize uyan platform araç seti sürümünüz olmayabilir. Bu durumda, araç setini almak için ihtiyacınız olan sürümün ücretsiz Visual Studio Community veya Express sürümünü yükleyebilirsiniz. Visual Studio 2008'deki Visual Studio'nun her sürümü, mevcut Visual Studio'dan bu sürümü hedeflemek için gereken derleyiciyi, araçları ve kütüphaneleri yükleyebilir. Visual Studio'nun belirli bir sürümünü bulmak ve indirmek için Microsoft İndirme Merkezi'nde arama yapın. Kurulum sırasında C++ yükleme seçeneklerini seçtiğinizden emin olun. Kurulum tamamlandıktan sonra, herhangi bir güncelleştirmeyüklemek için Visual Studio'nun bu sürümünü çalıştırın. Ayrıca, gerekli olabilecek Windows Update değişikliklerini de denetleyin. Bu güncelleştirme denetimi işleminin her güncelleştirmeyi almak için birden çok kez yinelenmesi gerekebilir.

Şu anda kullanılabilen indirmeler için [bkz.](https://visualstudio.microsoft.com/vs/older-downloads/)

Bu ürünler yüklendiğinde, **Özellik Sayfaları** iletişim kutusundaki **Platform Toolset** özelliği açılır açılır, kullanılabilir araç kümelerini göstermek için otomatik olarak güncelleştirilir. Artık Visual Studio'nun en son sürümünü kullanarak araç setinin eski sürümleri için projeleri dönüştürmeden veya yükseltmeden oluşturabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++'nin önceki sürümlerinden projeleri yükseltme](upgrading-projects-from-earlier-versions-of-visual-cpp.md)<br/>
[Visual Studio’deki C++ uyumluluk geliştirmeleri](../overview/cpp-conformance-improvements.md)
