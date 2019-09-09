---
title: /Qspectre
ms.date: 09/06/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.SpectreMitigation
helpviewer_keywords:
- /Qspectre
ms.openlocfilehash: e8d03075a980a9b9c345ce351413e39a3c3444cb
ms.sourcegitcommit: 7babce70714242cf498ca811eec3695fad3abd03
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2019
ms.locfileid: "70808831"
---
# <a name="qspectre"></a>/Qspectre

Belirli Spectre varyant 1 güvenlik açıklarına karşı hafifletmek için derleyici oluşturma yönergelerinin belirtir.

## <a name="syntax"></a>Sözdizimi

> **/Qspectre**

## <a name="remarks"></a>Açıklamalar

**/Qspectre** seçeneği, visual Studio 2017 sürüm 15.5.5 ve sonrasında ve visual Studio 2015 güncelleştirme 3 Ile [4338871 KB](https://support.microsoft.com/help/4338871/visual-studio-2015-update-3-spectre-variant-1-toolset-qspectre)arasında bulunur. Derleyicinin bazı [Spectre güvenlik açıklarını](https://spectreattack.com/spectre.pdf)hafifletmek için yönergeler eklemesine neden olur. Bu güvenlik açıklarına, *kurgusal yürütme yan kanal saldırıları*adı verilir. Intel, AMD ve ARM İşlemcileri dahil olmak üzere birçok işletim sistemini ve modern işlemcileri etkiler.

**/Qspectre** seçeneği varsayılan olarak kapalıdır.

İlk sürümünde, **/Qspectre** seçeneği yalnızca iyileştirilmiş kodla kullanılabilir. Visual Studio 2017 sürüm 15,7 ve sonraki sürümlerde, **/Qspectre** seçeneği tüm iyileştirme düzeylerinde desteklenir.

Microsoft Visual C++ kitaplıkları, Spectre azaltma ile sürümlerde de mevcuttur. Visual Studio 2017 ve üzeri için Spectre-hafiftılan kitaplıklar Visual Studio Yükleyicisi indirilebilir. Bunlar, **derleyiciler, derleme araçları ve çalışma zamanları**altındaki **tek bileşenler** sekmesinde bulunur ve adında "Spectre için libs" bulunur. Hem DLL hem de hafifletme özellikli olan statik çalışma zamanı kitaplıkları görsel C++ çalışma zamanlarının bir alt kümesi için kullanılabilir: VC + + başlangıç kodu, vcruntime140, msvcp140, concrt140 ve vcamp140. Dll 'Ler yalnızca uygulama yerel dağıtımı için desteklenir. Visual C++ 2017 ve üzeri çalışma zamanı kitaplıklarının yeniden dağıtılabilir içeriği değiştirilmedi.

MFC ve ATL için Spectre-hafifme kitaplıklarını da yükleyebilirsiniz. Bunlar **, SDK 'lar, kitaplıklar ve çerçeveler**altındaki **ayrı bileşenler** sekmesinde bulunur.

> [!NOTE]
> Evrensel Windows (UWP) uygulamaları veya bileşenleri için Spectre ile hafiflemesiz kitaplıkların bir sürümü yoktur. Bu tür kitaplıkların uygulama yerel dağıtımı mümkün değildir.

### <a name="applicability"></a>Uygulanabilirlik

Kodunuz bir güven sınırını kesen veriler üzerinde çalışıyorsa, bu sorunu mümkün olan en kısa sürede azaltmak için kodunuzu yeniden oluşturmak ve yeniden dağıtmak üzere **/Qspectre** seçeneğini kullanmanızı öneririz. Bu kod örneği, yürütmeyi etkileyebilecek güvenilmeyen girişi yükleyen koddur. Örneğin, uzak yordamı çağıran kod, güvenilmeyen giriş veya dosyaları ayrıştırır veya diğer yerel işlem arası iletişim (IPC) arabirimlerini kullanır. Standart korumalı alana alma teknikleri yeterli olmayabilir. Kodunuzun güven sınırının çapraz olmadığı kararı vermeden önce sanal ortamınızı dikkatle araştırın.

### <a name="availability"></a>Kullanılabilirlik

**/Qspectre** seçeneği, Visual Studio 2017 sürüm 15.5.5 ' de ve 23 Ocak 2018 tarihinde veya sonrasında yapılan C++ tüm MICROSOFT derleyicileri (MSVC) güncelleştirmelerinde bulunur. Derleyiciyi güncelleştirmek ve Spectre-hafiftılan kitaplıkları tek tek bileşenler olarak yüklemek için Visual Studio Yükleyicisi kullanın. **/Qspectre** seçeneği, Visual Studio 2015 güncelleştirme 3 ' te bir yama aracılığıyla da kullanılabilir. Daha fazla bilgi için bkz. [KB 4338871](https://support.microsoft.com/help/4338871).

Visual Studio 2017 sürüm 15,5 ' nin tüm sürümleri ve Visual Studio 2017 sürüm 15,6 ' in tüm önizlemeleri. belgelenmemiş bir seçeneği ekleyin, **/d2guardspecload**. Bu, **/Qspectre**'in ilk davranışına eşdeğerdir. Bu derleyicinin bu sürümlerindeki kodunuzda aynı azaltmaları uygulamak için **/d2guardspecload** ' i kullanabilirsiniz. Derlemenizi, bu seçeneği destekleyen derleyicilerde **/Qspectre** kullanmak üzere güncelleştirmenizi öneririz. **/Qspectre** seçeneği, derleyicinin sonraki sürümlerinde yeni azaltıcı etkenleri de destekleyebilir.

### <a name="effect"></a>Efekt

**/Qspectre** seçeneği, Specter varyant 1, sınır denetimi atlaması, [CVE-2017-5753](https://nvd.nist.gov/vuln/detail/CVE-2017-5753)' i azaltmak için kodu verir. Bu, kurgusal bir kod yürütme engeli olarak davranan yönergelerin eklenmesine göre çalışır. İşlemci uyumluluğunu azaltmak için kullanılan belirli yönergeler, işlemciye ve mikro mimarisine bağlıdır ve derleyicinin gelecek sürümlerinde değişebilir.

**/Qspectre** seçeneğini etkinleştirdiğinizde, derleyici, yansımalı yürütmenin sınır denetimlerini atlayabileceği örnekleri belirlemeyi dener. Bu, engel talimatlarını eklediği yerdir. Bir derleyicinin varyant 1 örneklerini tanımlamak için yapabildiği analize yönelik limitlerin farkında olmak önemlidir. Bu nedenle, değişken 1 ' in tüm olası örneklerinin **/Qspectre**altında işaretlenmiş olduğunun garantisi yoktur.

### <a name="performance-impact"></a>Performans etkisi

**/Qspectre** performans etkisi, birkaç boyutlandırılabilir kod tabanı içinde yok edilebilir. Ancak, **/Qspectre** altındaki kodunuzun performansının etkilenmemesini garanti eder. Bu seçeneğin performans üzerindeki etkisini öğrenmek için kodunuzu kıyaslanmalısınız. Performans açısından kritik bir blok veya döngüde hafifletme gerekmediğini biliyorsanız, bir [__declspec (Spectre (nohafifletme))](../../cpp/spectre.md) yönergesini kullanarak hafifletme 'yi seçmeli olarak devre dışı bırakabilirsiniz. Bu yönerge yalnızca **/d2guardspecload** seçeneğini destekleyen derleyicilerde kullanılamaz.

### <a name="required-libraries"></a>Gerekli kitaplıklar

**/Qspectre** derleyici seçeneği, Spectre azaltmaları sağlamak üzere oluşturulan çalışma zamanı kitaplıklarının sürümlerini örtülü olarak bağlayan kodu oluşturur. Bu kitaplıklar, Visual Studio Yükleyicisi kullanılarak yüklenmesi gereken isteğe bağlı bileşenlerdir:

- Spectre\[için MSVC Version *version_numbers* LIBS (x86 ve x64) | (ARM) | (ARM64)]
- C++ İçin\[Visual ATL (x86/x64) | ARM | ARM64] Spectre azaltmaları ile
- X86 C++ /x64 \[için Visual MFC | ARM | ARM64] Spectre azaltmaları ile

Kodunuzu **/Qspectre** kullanarak oluşturursanız ve bu kitaplıklar yüklü değilse, derleme sistemi uyarı MSB8038 ' yi raporlar **: Spectre azaltma etkin ancak Spectre hafifletme kitaplıkları bulunamadı**. MFC veya ATL kodunuz derlenmezse ve bağlayıcı önemli hata LNK1104 gibi bir hata bildirirse **: ' oldnames. lib ' dosyası**açılamıyor, bu eksik kitaplıklar neden olabilir.

### <a name="additional-information"></a>Ek bilgiler

Daha fazla bilgi için bkz. resmi [Microsoft Güvenlik Danışmanlığı ADV180002, yansımalı yürütme tarafı kanal güvenlik açıklarını azaltmaya yönelik rehberlik](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002). Ayrıca, Intel, [kurgusal yürütme tarafı kanal azaltmaları](https://software.intel.com/sites/default/files/managed/c5/63/336996-Speculative-Execution-Side-Channel-Mitigations.pdf)ve ARM, [önbellek yansımalı yan kanallar](https://developer.arm.com/-/media/Files/pdf/Cache_Speculation_Side-channels.pdf)aracılığıyla da kullanılabilir. Spectre ve Meltazaltma hafifletlerine yönelik Windows 'a özel bir genel bakış için bkz. [Windows sistemlerinde Spectre ve meltazaltma azaltıcı etkenleri 'nin performans etkisini anlama](https://www.microsoft.com/security/blog/2018/01/09/understanding-the-performance-impact-of-spectre-and-meltdown-mitigations-on-windows-systems/). MSVC azaltmaları tarafından ele alınan Spectre güvenlik açıklarına genel bakış için, bkz. C++ takım BLOGDAKI [MSVC içindeki Spectre azaltmaları](https://devblogs.microsoft.com/cppblog/spectre-mitigations-in-msvc./) .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

::: moniker range="vs-2019"

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **CC++ /** kod> **oluşturma** özellik sayfasını seçin.

1. **Spectre hafifletme** özelliği için yeni bir değer seçin. Değişikliği uygulamak için **Tamam ' ı** seçin.

::: moniker-end

::: moniker range="<=vs-2017"

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **CC++ /** komut> **satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** kutusuna **/Qspectre** derleyici seçeneğini girin. Değişikliği uygulamak için **Tamam ' ı** seçin.

::: moniker-end

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Q Seçenekler (Düşük Düzey İşlemler)](q-options-low-level-operations.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
