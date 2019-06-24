---
title: /Qspectre
ms.date: 10/12/2018
f1_keywords:
- /Qspectre
helpviewer_keywords:
- /Qspectre
ms.openlocfilehash: e0d3af50015b77af297cbee22f439cd17d803de9
ms.sourcegitcommit: 6cf0c67acce633b07ff31b56cebd5de3218fd733
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2019
ms.locfileid: "67344157"
---
# <a name="qspectre"></a>/Qspectre

Derleyici belirli Spectre değişkeni 1 güvenlik açıklarını gidermek için yönergeler oluşturulmasını belirtir.

## <a name="syntax"></a>Sözdizimi

> **/Qspectre**

## <a name="remarks"></a>Açıklamalar

**/Qspectre** seçeneği, Visual Studio 2017 sürüm 15.5.5 kullanılabilir ve daha sonra ve Visual Studio 2015 güncelleştirme 3'ten [KB 4338871](https://support.microsoft.com/help/4338871/visual-studio-2015-update-3-spectre-variant-1-toolset-qspectre). Belirli azaltmak için yönergeler derleyiciye neden [Spectre güvenlik açıklarını](https://spectreattack.com/spectre.pdf). Bu güvenlik açıklarına adlı *kurgusal yürütme yan kanal saldırıları*. Birçok işletim sistemleri ve Intel, AMD ve ARM işlemcileri gibi modern işlemciler etkilerler.

**/Qspectre** seçeneği varsayılan olarak kapalıdır.

İlk sürümde, **/qspectre** seçeneği yalnızca üzerinde çalıştığınız en iyi duruma getirilmiş kod. Visual Studio 2017 sürüm 15.7 ve üzeri, **/qspectre** seçeneği, tüm iyileştirme düzeylerinde desteklenir.

Microsoft Visual C++ kitaplıkları da Spectre riskini azaltma sürümlerle kullanılabilir. Spectre azaltılabilir kitaplıkları ve daha sonra Visual Studio 2017 için Visual Studio Yükleyicisi'nde indirilebilir. Bulunan **tek tek bileşenler** sekmesinde altında **derleyiciler, derleme araçları ve çalışma zamanları**, ve "Spectre için kitaplıklar" adı. DLL hem statik çalışma zamanı kitaplıkları ile etkinleştirilen risk azaltma Visual C++ çalışma zamanı bir alt kümesi için kullanılabilir: VC ++ başlatma kodu, vcruntime140, msvcp140, concrt140 ve vcamp140. DLL'leri yalnızca yerel uygulama dağıtımı için desteklenir. Görselin içeriklerini C++ 2017 ve sonraki çalışma zamanı kitaplıklarının yeniden dağıtılabilir henüz değiştirilmiş.

MFC ve ATL için Spectre azaltılabilir kitaplıkları da yükleyebilirsiniz Bulunan **tek tek bileşenler** sekmesinde altında **SDK'lar, kitaplıklar ve çerçeveler**.

### <a name="applicability"></a>Uygulanabilirlik

Kodunuz, bir güven sınırı aştığında veriler üzerinde çalışır ve ardından kullanmanızı öneririz, **/qspectre** yeniden oluşturun ve olabildiğince çabuk bu sorunu gidermek için kodunuzu yeniden dağıtın. Bu tür kod yürütme etkileyebilecek güvenilir olmayan girişlere yükler kod örneğidir. Örneğin, uzak yordam yapar kodu çağırır, güvenilmeyen girişler veya dosyalarını ayrıştırmak veya diğer yerel işlemler arası iletişim (IPC) arabirimini kullanır. Standart bir korumalı alana alma tekniklerini yeterli olmayabilir. Kodunuzu güven sınırının çapraz değil karar vermeden önce sanal dikkatle inceleyin.

### <a name="availability"></a>Kullanılabilirlik

**/Qspectre** seçenek, kullanılabilir tüm güncelleştirmelerin Microsoft ve Visual Studio 2017 sürüm 15.5.5 C++ derleyiciler ve 23 Ocak 2018'den sonra (MSVC). Visual Studio yükleyicisi, derleyici güncelleştirilecek ve tek tek bileşenleri olarak Spectre azaltılabilir kitaplıklarını yüklemek için kullanın. **/Qspectre** seçenek, ayrıca bir düzeltme eki Visual Studio 2015 güncelleştirme 3'te kullanılabilir. Daha fazla bilgi için [KB 4338871](https://support.microsoft.com/help/4338871).

Visual Studio 2017 sürüm 15.5 ve tüm önizlemeleri, Visual Studio 2017 sürüm 15.6 tüm sürümleri. belgelenmemiş bir seçenek içerecek **/d2guardspecload**. Başlangıç davranışını eşdeğerdir **/qspectre**. Kullanabileceğiniz **/d2guardspecload** derleyicisinin bu sürümü kodunuzda aynı risk azaltma işlemleri uygulamak için. Yapınızı kullanmak için güncelleştirme öneririz **/qspectre** seçeneğini destekleyen derleyiciler içinde. **/Qspectre** seçeneği derleyicinin sonraki sürümlerde yeni risk azaltma işlemleri de destekleyebilir.

### <a name="effect"></a>Efekt

**/Qspectre** seçeneği çıkarır Specter değişken 1, kontrol sınırları atlama azaltmak için kod [CVE-2017-5753](https://nvd.nist.gov/vuln/detail/CVE-2017-5753). Kurgusal bir kod yürütme engeli davranan yönergeleri ekleme çalışır. İşlemci Spekülasyon azaltmak için kullanılan özel yönergeler, işlemci ve kendi mikro-mimarisi bağlıdır ve gelecekteki derleyici sürümleri değişebilir.

Etkinleştirdiğinizde **/qspectre** derleyici seçeneği, çalışır örnekleri burada kurgusal yürütmeyi atlama sınırları denetimleri tanımlamak. Burada bunu barrier yönergelerini ekler olmasıdır. Bir derleyici değişkeni 1 örnekleri tanımlamak için yapabileceğiniz çözümleme sınırları bilmeniz önemlidir. Bu nedenle, tüm olası değişkeni 1 örnekleri altında işaretlenmiş bir garanti yoktur **/qspectre**.

### <a name="performance-impact"></a>Performans etkisi

Performans etkisini **/qspectre** birkaç hacimle kod tabanlarında göz ardı edilebilir olduğu görüldü. Ancak, tutarlılık garantisi yoktur, kodunuzun altında performans **/qspectre** etkilenmez. Kodunuzu seçeneği performans üzerindeki etkisini belirlemek için Kıyaslama. Azaltma performans açısından kritik blok veya döngü içinde gerekli olmadığından biliyorsanız, seçmeli olarak risk azaltma kullanarak devre dışı bırakabilirsiniz bir [__declspec(spectre(nomitigation))](../../cpp/spectre.md) yönergesi. Bu yönerge yalnızca destekleyen derleyicilerde kullanılamaz **/d2guardspecload** seçeneği.

### <a name="required-libraries"></a>Gerekli kitaplıkları

**/Qspectre** derleyici seçeneği Spectre risk azaltma işlemleri sağlamak üzere tasarlanmış çalışma zamanı kitaplıklarının sürümlerini örtük olarak bağlanan kod oluşturur. Bu kitaplıklar, Visual Studio Yükleyicisi'ni kullanarak yüklü olması gereken isteğe bağlı bileşenleri şunlardır:

- MSVC sürüm *version_numbers* Spectre için kitaplıklar \[(x86 ve x64) | (ARM) | (ARM64)]
- Görsel C++ için ATL \[(x86/x64) | ARM | ARM64] Spectre azaltmaları ile
- Görsel C++ için MFC \[x86/x64 | ARM | ARM64] Spectre azaltmaları ile

Kodunuzu kullanarak derleme yaparsanız **/qspectre** ve bu kitaplıklar yüklüyse, yapı sistemi raporları **MSB8038 Uyarı: Spectre riskini azaltma etkinleştirildi, ancak Spectre azaltılabilir kitaplıklar bulunamadı**. MFC veya ATL kodunuzu derlemek başarısız olur ve bağlayıcı gibi bir hata bildiriyor **LNK1104 önemli hatası: 'oldnames.lib' dosyası açılamıyor**, bu eksik kitaplıklar neden olabilir.

### <a name="additional-information"></a>Ek bilgiler

Daha fazla bilgi için bkz: resmi [kurgusal yürütme yan kanal güvenlik açıklarına azaltmak için Microsoft Güvenlik Danışma ADV180002, rehberlik](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002). Kılavuzu Intel'in, kullanılabilir ayrıca [kurgusal yürütme yan kanal azaltmaları](https://software.intel.com/sites/default/files/managed/c5/63/336996-Speculative-Execution-Side-Channel-Mitigations.pdf)ve ARM, [önbellek Spekülasyon yan kanalları](https://developer.arm.com/-/media/Files/pdf/Cache_Speculation_Side-channels.pdf). Spectre ve Meltdown azaltmaları Windows özgü bakış için bkz: [Spectre ve Meltdown azaltmaları Windows sistemlerinde performans etkisini anlama](https://www.microsoft.com/security/blog/2018/01/09/understanding-the-performance-impact-of-spectre-and-meltdown-mitigations-on-windows-systems/). Spectre güvenlik açıklarını MSVC risk azaltma işlemleri tarafından ele alınan genel bakış için bkz. [Spectre azaltmaları MSVC içinde](https://devblogs.microsoft.com/cppblog/spectre-mitigations-in-msvc./) üzerinde C++ ekibi blogu.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++**  > **komut satırı** özellik sayfası.

1. Girin **/qspectre** derleyici seçeneğini **ek seçenekler** kutusu. Seçin **Tamam** değişikliği uygulamak için.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Q Seçenekler (Düşük Düzey İşlemler)](q-options-low-level-operations.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
