---
title: Yerel çoklu sürüm desteğinin Visual Studio'da eski projeleri oluşturmak için kullanın
ms.date: 11/04/2016
helpviewer_keywords:
- C++ native multi-targeting
- upgrading Visual C++ applications, retargeting
ms.assetid: b115aabe-a9dc-4525-90d3-367d97ea20c9
ms.openlocfilehash: 57e9556ccb7313c137c173e0f2143dc6e563d4c3
ms.sourcegitcommit: b72a10a7b12e722fd91a17406b91b270026f763a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/03/2019
ms.locfileid: "58898823"
---
# <a name="use-native-multi-targeting-in-visual-studio-to-build-old-projects"></a>Yerel çoklu sürüm desteğinin Visual Studio'da eski projeleri oluşturmak için kullanın

Normalde, Visual Studio'nun en son sürümünü yüklediğinizde projelerinizi güncelleştirmenizi öneririz. Proje ve kod güncelleştirme maliyeti genellikle daha fazla yeni IDE, derleyici, kitaplıklar ve Araçlar avantajlarını tarafından uzaklığı. Ancak, bazı projeler güncelleştirmek mümkün olmayabilir olduğunu biliyoruz. Eski kitaplıkları veya bakım nedeniyle, yükseltemezsiniz platformları bağlı ikili dosyalarınız. Kodunuz için daha yeni bir derleyici taşıdıysanız, kesmek standart olmayan dil yapıları kullanabilirsiniz. Kodunuzu Visual C++, belirli bir sürümü için derlenmiş 3 şahıs kitaplıklardaki dayanır. Veya Visual C++ belirli bir eski sürümünü hedeflemelidir başkaları için kitaplıkları üretebilir.

Neyse ki, bu hedef eski derleyici araç kümeleri ve kitaplıklar projeleri derlemek için Visual Studio 2017 ve Visual Studio 2015 kullanabilirsiniz. Visual Studio 2010, Visual Studio 2012, Visual Studio 2013 veya Visual Studio 2015 proje IDE'de yeni özelliklerden yararlanmak için yükseltme gerekmez:

  - Yeni C++ yeniden düzenleme özellikleri ve Deneysel özellikler Düzenleyicisi
  - Yeni tanılama araçları penceresi ve Hata Listesi penceresi hata ayıklayıcı
  - Yenilenmiş kesme noktaları, özel durumlar penceresi ve yeni PerfTips
  - Yeni kod gezinti ve arama araçları
  - Yeni C++ hızlı düzeltmeler ve verimlilik güç araçları uzantıları.

Visual Studio 2008 projeleri de hedefleyebilir, ancak bunlar kullanılamaz değişmez. Ayrıntılar için bkz **yönergeler için Visual Studio 2008** bölümü.

Proje gidiş dönüşü yerel çoklu sürüm desteği ve Visual Studio'nun en son sürümlerini destekler. Yerel çoklu sürüm desteğinin araç takımları ile Visual Studio'nun önceki sürümleri yüklü kullanarak oluşturmak için en yeni IDE özelliğidir. Gidiş dönüşü projeye herhangi bir değişiklik yapmadan önceki bir IDE sürümü tarafından oluşturulmuş bir projeyi yüklemeye son IDE'nin yeteneğidir. Mevcut sürümünüz ile Visual Studio yan yana en son sürümünü yüklerseniz, IDE yeni sürümünü derleyici ve araçlarla mevcut sürümünden projelerinizi oluşturmak için kullanabilirsiniz. Diğer ekip üyelerinin projeleri Visual Studio'nun eski sürümde kullanmaya devam edebilirsiniz.

Eski bir araç takımı kullandığınızda, C++ derleyicisi, kitaplıklar ve derleme araçları birçok yeni IDE özelliği, ancak değil en son geliştirmeleri avantajlarından yararlanabilirsiniz. Örneğin, yeni hata ayıklama yeni dil uyumluluk geliştirmeleri kullanın ve kod çözümleme özellikleri veya en son araç daha hızlı derleme aktarım hızı alma mümkün olmayacaktır. Eski araç takımları ile uyumlu olmayan bazı IDE özellikleri de vardır. Örneğin, tür bilgilerini bellek Profiler ve yeniden düzenleme işlemi eksik olabilir **ham dize değişmez değerlerine dönüştürme** kullandığınızda Visual Studio 2012 veya daha eski araç takımları, derlenemeyecektir C ++ 11 ile uyumlu kod üretir.

## <a name="how-to-use-native-multi-targeting-in-visual-studio"></a>Visual Studio'da yerel çoklu sürüm desteğinin kullanma

Visual Studio yan yana eski sürümünüzle yükledikten sonra yeni Visual Studio sürümünde mevcut projenizi açın. Proje yüklendiğinde, Visual Studio en son C++ Derleyici ve kitaplıkları kullanacak şekilde yükseltmek isteyip istemediğinizi sorar. Proje eski derleyici ve kitaplıkları tutmak istediğinden seçin **iptal** düğmesi.

Visual Studio, projenizi yükseltme hakkında kalıcıdır. Projeyi her yüklediğimizde yükseltme iletişim kutusundan görmekten kaçınmak için aşağıdaki özelliği projelerinizi tanımlayabilirsiniz veya .props veya .targets dosyalarında bunlar içeri aktarın:

`<VCProjectUpgraderObjectName>NoUpgrade</VCProjectUpgraderObjectName>`

Projelerinizi yükseltmek istediğinizde bu özellik kaldırmanız gerekir.

Yükseltme seçerseniz Visual Studio çözüm veya proje dosyalarınıza değişiklik yapmaz. Projeyi oluşturduğunuzda oluşturulan ikili dosyaları Visual Studio'nun önceki sürümüyle oluşturulan fiyatlarla tam olarak uyumlu değildir. Visual Studio C++ derleyicinin aynısını kullanır ve eski IDE'nizi ile birlikte gelen aynı kitaplıkları bağlantılar olmasıdır. Ayrıca neden yükseltme iletişim kutusundan seçerseniz yüklü olan Visual Studio sürümün tutmak için sizi uyarır olan **iptal**.

## <a name="instructions-for-visual-studio-2008"></a>Visual Studio 2008 için yönergeler

Visual Studio 2008 adlı C++ için kendi özel yapı sistemine sahip **VCBuild**. Visual Studio 2010'da başlıyor, Visual C++ projeleri kullanmak üzere değiştirilmiştir **MSBuild**. Başka bir deyişle, Visual Studio 2008 projelerinizi Visual Studio'nun en son sürümünü derlemek için bir güncelleştirme adım aracılığıyla gitmeniz gerekir. Güncelleştirilmiş projeniz Visual Studio 2008 IDE kullanılarak oluşturulan ikili dosyalarla tam olarak uyumlu ikili dosyaları yine de oluşturur.

İlk olarak, Visual Studio geçerli sürümüne ek olarak, Visual Studio 2008 ile aynı bilgisayarda Visual Studio 2010 yüklemelisiniz. Visual Studio 2010 yükler **MSBuild** hedef Visual Studio 2008 projeleri için gereken betikler.

Ardından, Visual Studio 2008 çözümünüzü ve projelerinizi Visual Studio'nun geçerli sürüme güncelleştirmelisiniz. Proje ve çözüm dosyaları yükseltmeden önce bir yedeklemesini oluşturun öneririz. Yükseltme işlemini başlatmak için Visual Studio'nun geçerli sürümünde çözümü açın. Yükseltme istemi aldığınızda, bilgileri gözden geçirin ve ardından **Tamam** yükseltmeyi başlatmak için. Çözümde birden fazla projeniz varsa, güncelleştirmelisiniz sihirbaz yeni .vcxproj proje dosyaları yan yana mevcut .vcproj dosyaları oluşturur. Özgün .sln dosyasını bir kopyasını da sahip olduğu sürece, yükseltme, mevcut Visual Studio 2008 projeler üzerinde diğer herhangi bir etkisi yoktur.

Yükseltme tamamlandığında günlük rapor tüm projeleriniz için hataları veya uyarıları içeriyorsa dikkatle gözden geçirin. Dönüştürme **VCBuild** için **MSBuild** sorunlara neden olabilir. Anlama ve raporu listelenen herhangi bir eylem öğeleri uygulamak emin olun. Yükseltme günlüğünü rapor ve dönüştürme sırasında meydana gelebilecek sorunları hakkında daha fazla bilgi için **VCBuild** için **MSBuild**, bkz. Bu [yerel C++ çoklu sürüm desteğinin](https://blogs.msdn.microsoft.com/vcblog/2009/12/08/c-native-multi-targeting/) blog gönderisi.

Proje yükseltme tamamlandıktan ve günlük dosyasında sorunları düzelttikten sonra çözümünüzün en son araç takımı gerçekten hedefler. Son adım olarak, Visual Studio 2008 araç kümesi kullanmak için çözümde her proje özelliklerini değiştirin. Visual Studio'nun geçerli sürümünde çözümde her proje için yüklenen çözümüyle projeyi açın **özellik sayfaları** iletişim kutusunda: Projeye sağ tıklayarak **Çözüm Gezgini** seçip **özellikleri**. İçinde **özellik sayfaları** iletişim kutusunda, değişiklik **yapılandırma** için aşağı açılan değer **yapılandırmalarında**. İçinde **yapılandırma özellikleri**seçin **genel**ve ardından değiştirmek **Platform araç takımını** için **Visual Studio 2008 (v90)**.

Bu değişiklikten sonra Visual Studio 2008 derleyici ve kitaplıkları, Visual Studio'nun geçerli sürümünde bir çözüm oluşturduğunuzda, proje ikililerini oluşturmak için kullanılır.

## <a name="install-an-older-visual-studio-toolset"></a>Eski bir Visual Studio araç takımı'nı yükleme

Olamaz ya da yükseltmek istemediğiniz eski bir Visual C++ projesi, ancak projenizi eşleşen olmayan platform araç kümesi sürümünü olabilir. Bu durumda, araç takımı almak için ücretsiz Visual Studio Community'yi veya ihtiyacınız olan sürümü Express sürümü yükleyebilirsiniz. Visual Studio 2008'den Visual Studio'nun her sürümü, derleyici, araçları ve kitaplıklarını geçerli Visual Studio, sürümünü hedefleyecek şekilde ihtiyacınız yükleyebilmek için. Bul ve Visual Studio'nun belirli bir sürümü indirmek için Microsoft Download Center arayın. Kurulum sırasında C++ yükleme seçenekleri seçtiğinizden emin olun. Kurulum tamamlandıktan sonra tüm güncelleştirmeleri yüklemek için Visual Studio'nun bu sürümü çalıştırın. Ayrıca Windows Update değişiklikleri için gerekli olabilecek denetleyin. Bu güncelleştirme onay işlemi her güncelleştirmeyi almak için birden fazla kez yinelenen gerekebilir.

Şu anda kullanılabilir yüklemeler için bkz: [eski Visual Studio yazılımını indirme](https://visualstudio.microsoft.com/vs/older-downloads/).

Bu ürünler yüklü olduğunda **Platform araç takımını** özellik açılan menü **özellik sayfaları** iletişim kutusu kullanılabilir takımları gösterecek şekilde otomatik olarak güncelleştirilir. Şimdi, dönüştürme veya yükseltilirken araç bu eski sürümler için projeleri derlemek için Visual Studio'nun en son sürümünü kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Önceki Visual C++ Sürümü Projelerini Yükseltme](upgrading-projects-from-earlier-versions-of-visual-cpp.md)<br/>
[Visual Studio'da C++ uyumluluk geliştirmeleri](../overview/cpp-conformance-improvements.md)
