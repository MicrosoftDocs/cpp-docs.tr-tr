---
title: Projeleri C++ Visual Studio 'nun önceki sürümlerinden yükseltme
description: Microsoft C++ projelerini Visual Studio 'nun eski sürümlerinden yükseltme.
ms.date: 10/29/2019
helpviewer_keywords:
- 32-bit code porting
- upgrading Visual C++ applications, 32-bit code
ms.assetid: 18cdacaa-4742-43db-9e4c-2d9e73d8cc84
ms.openlocfilehash: b317271a9cd0873e60a6dd9acd1b73a766aaea19
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627161"
---
# <a name="upgrade-c-projects-from-earlier-versions-of-visual-studio"></a>Projeleri C++ Visual Studio 'nun önceki sürümlerinden yükseltme

Visual Studio 2008 veya önceki sürümlerde oluşturulan bir projeyi yükseltmek için öncelikle Visual Studio 2010 kullanarak projeyi VCBuild biçiminden (. vcproj) MSBuild biçimine (. vcxproj) dönüştürmeniz gerekir. Daha fazla bilgi için bkz. [Visual Studio 2008 Için yönergeler](use-native-multi-targeting.md#instructions-for-visual-studio-2008).

Visual Studio 2010 veya sonraki sürümlerde oluşturulan bir projeyi yükseltmek için, Visual Studio 'nun en son sürümünde projeyi açmanız yeterlidir. Visual Studio, projeyi geçerli şemaya yükseltmek için teklifler sunar. **Hayır**' ı seçerseniz ve bilgisayarınızda Visual Studio 'nun eski sürümüne sahipseniz, projede Visual Studio 'nun daha yeni bir sürümünde çalışabilir ve eski araç takımını hedefle devam edebilirsiniz. Örneğin, projenizin Windows XP 'de çalışmaya devam etmesi gerekiyorsa, Visual Studio 2019 ' a yükseltebilirsiniz, ancak araç takımını v141 veya daha önceki bir sürümü olarak belirtmeniz gerekir. Daha fazla bilgi için bkz. [Eski projeler oluşturmak Için Visual Studio 'da yerel çoklu sürüm kullanımını kullanma](use-native-multi-targeting.md). **Evet**' i seçerseniz, proje dönüştürülür ve önceki sürüme geri dönüştürülemez. Bu nedenle, yükseltme senaryolarında, var olan proje ve çözüm dosyalarının bir kopyasını oluşturmak iyi bir uygulamadır.

## <a name="upgrade-reports"></a>Yükseltme raporları

Bir projeyi yükselttiğinizde, aynı zamanda proje klasörünüze UpgradeLog. htm olarak kaydedilen bir yükseltme raporu alırsınız. Yükseltme raporu, karşılaşılan sorunların özetini ve yapılan değişiklikler hakkında bazı bilgileri gösterir, örneğin:

1. Proje Özellikleri

2. İçerme dosyaları

3. Derleyici uygunluk geliştirmeleri veya standart değişiklikler nedeniyle artık düzgün derlenmeyecek kod

4. Visual Studio 'nun veya varsayılan bir Visual Studio yüklemesinde bulunmayan ya da üründen kaldırılmış olan üst bilgi dosyalarının kullanıldığı Visual Studio veya Windows özelliklerini kullanan kod

5. Yeniden adlandırılan API 'Ler, değiştirilen işlev imzaları veya kullanım dışı işlevler gibi API 'lerde yapılan değişiklikler nedeniyle artık derlenmediğini belirten kod

6. Bir hata haline gelme gibi Tanılamadaki değişiklikler nedeniyle artık derlenmediğini belirten kod

7. Özellikle/NODEFAULTLIB kullanıldığında değiştirilen kitaplıklar nedeniyle bağlayıcı hataları.

8. Davranış değişiklikleri nedeniyle çalışma zamanı hataları veya beklenmedik sonuçlar

9. Araçlarda sunulan hatalar. Bir sorunla karşılaşırsanız, normal destek kanallarınız aracılığıyla veya C++ [Visual Studio C++ geliştirici topluluğu](https://developercommunity.visualstudio.com/spaces/62/index.html) sayfasını kullanarak bu sorunu görsel ekibe bildirin.

Bazı Yükseltilen projeler ve çözümler değişiklik yapılmadan başarıyla oluşturulabilir. Ancak, çoğu projenin büyük olasılıkla proje ayarlarında ve kaynak kodda değişiklik yapılması gerekir. Bunları düzeltmek için tek bir doğru yol yoktur, ancak bazı aşamalı yaklaşım önerilir. Başlamadan önce, yaygın olarak karşılaşılan birçok hata hakkında daha fazla bilgi için [olası yükseltme sorunlarına genel bakış](../porting/overview-of-potential-upgrade-issues-visual-cpp.md) konusunu inceleyin.

 1. Platform araç takımını, C++ dil standardını ve Windows SDK sürümünü (varsa) istenen sürümlere ayarlayın. (**Proje** > **özellikleri** > **yapılandırma özellikleri** > **genel**)
 1. Çok sayıda hata varsa, [izin veren](../build/reference/permissive-standards-conformance.md) seçeneğini devre dışı bırakın (**Proje** > **özellikleri** > **yapılandırma özellikleri** > **C/C++**  > **Language**) ve [Kod Analizi ](/visualstudio/code-quality/code-analysis-for-c-cpp-overview)(**Proje** > **özellikler** > **yapılandırma özellikleri** > **Kod Analizi**) seçeneği geçici olarak hata sayısını azaltmak için.
 1. Tüm bağımlılıkların mevcut olduğundan ve içerme yollarının veya kitaplık konumlarının doğru olduğundan emin olun. (**Proje** > **özellikleri** > **yapılandırma özellikleri** > **VC + + dizinleri**)
 1. Artık mevcut olmayan API başvuruları nedeniyle hataları belirleyip düzeltir.
 1. Derlemeyi engelleyen kalan hataları giderin. Yaygın hatalara yönelik düzeltmeler için [olası yükseltme sorunlarından genel bakış](../porting/overview-of-potential-upgrade-issues-visual-cpp.md) bölümüne bakın.
 1. **İzin** vermek için yeniden etkinleştirme yapın ve daha önce MSVC içinde derlenen uyumsuz olmayan kod nedeniyle görüntülenen yeni hataları düzeltin.
 1. Artık kabul edilebilir olarak kabul edilen olası sorunları veya geçmiş kodlama düzenlerini belirlemek için kod analizini etkinleştirin. Kod Analizi birçok hatayı işaretleyemdeyse, bazı uyarıları kapatarak öncelikle en önemli öneme sahip olursunuz. IDE, bazı sorun türleri için hızlı düzeltmelerde yardımcı olabilir.
 1. Özel veri yapılarını ve algoritmaları C++ standart kitaplıktan veya Boost açık kaynak kitaplığından değiştirerek, örneğin, kodu modernize yönelik diğer fırsatları düşünün. Standart özellikleri kullanarak başkalarının kodu korumasını kolaylaştırır ve ayrıca kodun iyi bir şekilde sınanmış ve standart Komite ve daha geniş C++ topluluk üzerinde birçok uzman tarafından incelendiğinden emin olabilirsiniz.

Onarma sırasında hatalar için Stack Overflow veya [ C++ geliştirici topluluğu](https://developercommunity.visualstudio.com/spaces/62/index.html)üzerinde bir soruyu aramayı veya göndermeyi deneyin.

## <a name="in-this-section"></a>Bu bölümde

[Olası yükseltme sorunlarına genel bakış](overview-of-potential-upgrade-issues-visual-cpp.md)<br/>
[Kodunuzu Evrensel CRT’ye Yükseltme](upgrade-your-code-to-the-universal-crt.md)<br/>
[WINVER ve _WıN32_WıNNT güncelleştirme](modifying-winver-and-win32-winnt.md)<br/>
[Kitaplık İçeriklerindeki Bağımlılıklarınızı Düzeltme](fix-your-dependencies-on-library-internals.md)<br/>
[Kayan Nokta Geçiş Sorunları](floating-point-migration-issues.md)<br/>
[C++Visual Studio 2019 ' de kullanım dışı Özellikler](features-deprecated-in-visual-studio.md)<br/>
[VCBuild ile MSBuild](build-system-changes.md)<br/>
[Bağlantı noktası 3. taraf kitaplıkları](porting-third-party-libraries.md)<br/>

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'daki görsele C++ yenilikler](../overview/what-s-new-for-visual-cpp-in-visual-studio.md)<br/>
[Visual C++ değişiklik geçmişi 2003 - 2015](../porting/visual-cpp-change-history-2003-2015.md)<br/>
[Standart Olmayan Davranış](../cpp/nonstandard-behavior.md)<br/>
[Bağlantı noktası veri uygulamaları](../data/data-access-programming-mfc-atl.md)<br/>
