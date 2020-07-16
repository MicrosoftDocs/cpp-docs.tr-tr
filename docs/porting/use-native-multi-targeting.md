---
title: Visual Studio’da eski projeleri oluşturmak için yerel çoklu sürüm paketi kullanma
ms.date: 10/25/2019
helpviewer_keywords:
- C++ native multi-targeting
- upgrading Visual C++ applications, retargeting
ms.assetid: b115aabe-a9dc-4525-90d3-367d97ea20c9
ms.openlocfilehash: 14100a70fa3bb883d257017eaf9174c5340317b4
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2020
ms.locfileid: "86404814"
---
# <a name="use-native-multi-targeting-in-visual-studio-to-build-old-projects"></a>Visual Studio’da eski projeleri oluşturmak için yerel çoklu sürüm paketi kullanma

Normalde, Visual Studio 'nun en son sürümünü yüklediğinizde projelerinizi güncelleştirmenizi öneririz. Projelerinizi ve kodunuzu güncelleştirme maliyeti genellikle yeni IDE, derleyici, kitaplıklar ve araçların avantajlarından daha fazla uzaklığa sahiptir. Ancak, bazı projeleri güncelleştiremeyebilirsiniz. Yükselteceğiniz bakım nedenlerinden daha eski kitaplıklara veya platformlara bağlı ikili dosyalarınız olabilir. Kodunuz, daha yeni bir derleyiciye taşıdığınız takdirde kesilecek standart olmayan dil yapılarını kullanabilir. Kodunuz, belirli bir Visual C++ sürümü için derlenen 3. taraf kitaplıklarını kullanabilir. Ya da diğer bir Visual C++ daha eski bir sürümünü hedeflemek zorunda olması gereken diğer kitaplıkları da oluşturabilirsiniz.

Neyse ki, daha eski derleyici araç kümelerini ve kitaplıklarını hedefleyen projeler oluşturmak için Visual Studio 2017 ve Visual Studio 2015 ' yi kullanabilirsiniz. IDE 'deki yeni özelliklerden yararlanmak için Visual Studio 2010, Visual Studio 2012, Visual Studio 2013 veya Visual Studio 2015 projesini yükseltmeniz gerekmez:

- Yeni C++ yeniden düzenleme özellikleri ve düzenleyici deneysel özellikleri
- Yeni tanılama araçları hata ayıklayıcısı penceresi ve Hata Listesi penceresi
- Yeniden kullanıma alınan kesme noktaları, özel durumlar penceresi ve yeni PerfTips
- Yeni kod gezintisi ve arama araçları
- Yeni C++ hızlı düzeltmeleri ve üretkenlik güç araçları uzantıları.

Visual Studio 2008 projelerini de hedefleyebilirsiniz, ancak bunlar değişmeden kullanılamaz. Ayrıntılar için bkz. **Visual Studio Için yönergeler 2008** bölümü.

Visual Studio 'nun en son sürümleri, projelerin yerel Çoklu hedefleme ve gidiş dönüşü destekler. Yerel çoklu hedefleme, en son IDE 'nin Visual Studio 'nun önceki sürümleri tarafından yüklenen araç kümelerini kullanarak oluşturma yeteneğidir. Gidiş dönüşü, en son IDE 'nin proje üzerinde herhangi bir değişiklik yapmadan önceki bir IDE sürümü tarafından oluşturulan projeleri yükleme olanağıdır. Visual Studio 'nun en son sürümünü mevcut sürümünüzle yan yana yüklerseniz, projelerinizi derlemek için mevcut sürümden derleyici ve araçlarla IDE 'nin yeni sürümünü kullanabilirsiniz. Takımınızın diğer üyeleri, Visual Studio 'nun eski sürümünde projeleri kullanmaya devam edebilir.

Daha eski bir araç takımını kullandığınızda, en son IDE özelliklerinden faydalanabilirsiniz, ancak C++ derleyicisinde, kitaplıklarda ve derleme araçlarında en son gelişmelerden yararlanabilirsiniz. Örneğin, yeni dil uyumluluğu geliştirmelerini, yeni hata ayıklama ve kod analizi özelliklerini kullanamaz ya da en son araç takımını daha hızlı derleme aktarım hızını edinebilirsiniz. Ayrıca, eski araç kümeleriyle uyumsuz bazı IDE özellikleri de vardır. Örneğin, bellek profil oluşturucuda tür bilgileri eksik olabilir ve yeniden düzenleme işlemi **Ham dize değişmez değerlerine dönüştürüyorsa** , Visual Studio 2012 veya daha eski araç kümelerini kullandığınızda derlenmeyen C + +11 uyumlu kod oluşturulur.

## <a name="how-to-use-native-multi-targeting-in-visual-studio"></a>Visual Studio 'da yerel Çoklu hedefleme kullanma

Visual Studio 'Yu eski sürümle yan yana yükledikten sonra, mevcut projenizi Visual Studio 'nun yeni sürümünde açın. Proje yüklendiğinde, Visual Studio en son C++ derleyicisini ve kitaplıklarını kullanmak için onu yükseltmek isteyip istemediğinizi sorar. Projenin eski derleyicisini ve kitaplıkları tutmasını istiyorsanız **iptal** düğmesini seçin.

Visual Studio, projenizi yükseltme hakkında kalıcıdır. Projeyi her yüklediğinizde yükseltme iletişim kutusunun görünmemesi için, projelerinizde aşağıdaki özelliği veya içeri aktardıkları. props veya. targets dosyalarını tanımlayabilirsiniz:

`<VCProjectUpgraderObjectName>NoUpgrade</VCProjectUpgraderObjectName>`

Projelerinizi yükseltmek istediğinizde bu özelliği kaldırmanız gerekir.

Yükseltmesiz ' ı seçerseniz, Visual Studio çözümünüzde veya proje dosyalarınızda değişiklik yapmaz. Projeyi derlediğinizde, oluşturulan ikililer, Visual Studio 'nun eski sürümüyle derleydiklerle tamamen uyumludur. Bunun nedeni, Visual Studio 'Nun aynı C++ derleyicisini kullanması ve eski IDE 'nizin sevk ettiği aynı kitaplıkları bağlalarıdır. Aynı zamanda, **iptal**' i seçerseniz yükseltme iletişim kutusunun, eski Visual Studio sürümünü yüklü tutmanız için sizi uyarır.

## <a name="instructions-for-visual-studio-2008"></a>Visual Studio 2008 için yönergeler

Visual Studio 2008, **VCBuild**adlı C++ için kendi adanmış derleme sistemine sahipti. Visual Studio 2010 ' den başlayarak, Visual Studio C++ projeleri **MSBuild**'i kullanacak şekilde değiştirilmiştir. Bu, kalıcı veya çoklu hedeflemenin yükseltilmesinden bağımsız olarak Visual Studio 2008 projelerinizi Visual Studio 'nun en son sürümünde derlemek için bir güncelleştirme adımından gitmeniz gerekir. Güncelleştirilmiş projeniz, Visual Studio 2008 IDE kullanılarak oluşturulan ikililer ile tamamen uyumlu ikili dosyalar oluşturuyor.

İlk olarak, Visual Studio 'nun geçerli sürümüne ek olarak Visual Studio 2010 ' i Visual Studio 2008 ile aynı bilgisayara yüklemeniz gerekir. Visual Studio 2008 projelerini hedeflemek için gereken **MSBuild** betikleri yalnızca visual Studio 2010 tarafından yüklenir.

Ardından, Visual Studio 2008 çözümünüzü ve projelerinizi Visual Studio 'nun geçerli sürümüne güncelleştirmeniz gerekir. Yükseltmeden önce projelerinizin ve çözüm dosyalarınızın bir yedeğini oluşturmanızı öneririz. Yükseltme işlemini başlatmak için, çözümü Visual Studio 'nun geçerli sürümünde açın. Yükseltme istemi 'ni aldığınızda, sunulan bilgileri gözden geçirin ve ardından yükseltmeyi başlatmak için **Tamam** ' ı seçin. Çözümde birden çok projeniz varsa, sihirbazın mevcut. vcproj dosyalarıyla yan yana yeni. vcxproj proje dosyaları oluşturacağını güncelleştirmeniz gerekir. Özgün. sln dosyasının bir kopyasına de sahip olduğunuz sürece, yükseltmenin mevcut Visual Studio 2008 projeleriniz üzerinde başka bir etkisi yoktur.

> [!NOTE]
> Aşağıdaki adımlar yalnızca çoklu hedefleme senaryoları için geçerlidir. Projeyi daha sonraki bir araç takımına kalıcı olarak yükseltmeyi düşünüyorsanız, bir sonraki adımınız projeyi kaydetmek, Visual Studio 2019 ' de açmak ve burada görünen derleme sorunlarını gidermek olacaktır.

Yükseltme tamamlandığında, günlük raporunda projelerinizden herhangi birinin hataları veya uyarıları varsa, bunları dikkatle gözden geçirin. **VCBuild** 'ten **MSBuild** 'e dönüştürme soruna neden olabilir. Raporda listelenen tüm eylem öğelerini anladığınızdan ve uyguladığınızdan emin olun. İşlem günlüğü raporu ve **VCBuild** **MSBuild**'e dönüştürülürken oluşabilecek sorunlar hakkında daha fazla bilgi için, bkz. bu [C++ yerel çoklu hedef](https://devblogs.microsoft.com/cppblog/c-native-multi-targeting/) blog gönderisi.

Proje yükseltmesi tamamlandığında ve günlük dosyasında herhangi bir sorunu düzelttiğiniz zaman, çözümünüz gerçekten en son araç takımını hedefler. Son adım olarak, çözümdeki her projenin özelliklerini Visual Studio 2008 araç takımını kullanacak şekilde değiştirin. Visual Studio 'nun geçerli sürümünde yüklenen çözüm ile, çözümdeki her bir proje için, proje **Özellik sayfaları** iletişim kutusunu açın: **Çözüm Gezgini** ' de projeye sağ tıklayın ve ardından **Özellikler**' i seçin. **Özellik sayfaları** iletişim kutusunda, **yapılandırma** açılan değerini **tüm yapılandırmalar**' a değiştirin. **Yapılandırma özellikleri**' nde **genel**' i seçin ve ardından **Platform araç takımını** **Visual Studio 2008 (V90)** olarak değiştirin.

Bu değişiklikten sonra Visual Studio 2008 derleyicisi ve kitaplıkları, Visual Studio 'nun geçerli sürümünde çözüm oluşturduğunuzda proje ikili dosyaları oluşturmak için kullanılır.

## <a name="install-an-older-visual-studio-toolset"></a>Eski bir Visual Studio araç takımını yükler

Projeniz ile eşleşen platform araç takımı sürümünü değil, yükseltmek istemediğiniz veya yükseltmek istemediğiniz eski bir Visual Studio C++ projenize sahip olabilirsiniz. Bu durumda, araç takımını almak için, ihtiyacınız olan sürümün ücretsiz Visual Studio Community veya Express sürümünü yükleyebilirsiniz. Visual Studio 2008 ' den Visual Studio 'nun her sürümü, bu sürümü geçerli Visual Studio 'dan hedeflemek için gereken derleyici, Araçlar ve kitaplıkları yükleyebilir. Visual Studio 'nun belirli bir sürümünü bulmak ve indirmek için Microsoft Indirme Merkezi ' nde arama yapın. Kurulum sırasında C++ yükleme seçeneklerini seçtiğinizden emin olun. Kurulum tamamlandıktan sonra, herhangi bir güncelleştirmeyi yüklemek için Visual Studio 'nun bu sürümünü çalıştırın. Ayrıca, gerekli olabilecek Windows Update değişikliklerini denetleyin. Tüm güncelleştirmeleri almak için bu güncelleştirme denetimi işleminin birden çok kez tekrarlanması gerekebilir.

Mevcut olan İndirilenler için bkz. [eski Visual Studio yazılımlarını indirme](https://visualstudio.microsoft.com/vs/older-downloads/).

Bu ürünler yüklendiğinde, **Özellik sayfaları** Iletişim kutusundaki **platform araç takımı** özelliği açılan menüsü, kullanılabilir araç kümelerini gösterecek şekilde otomatik olarak güncelleştirilir. Artık Visual Studio 'nun en son sürümünü kullanarak araç takımının daha eski sürümleri için projeler oluşturabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ önceki sürümlerinden projeleri yükseltme](upgrading-projects-from-earlier-versions-of-visual-cpp.md)<br/>
[Visual Studio 2017’deki C++ uyumluluk geliştirmeleri](../overview/cpp-conformance-improvements.md)
