---
title: / Qspectre | Microsoft Docs
ms.custom: ''
ms.date: 1/23/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
f1_keywords:
- /Qspectre
helpviewer_keywords:
- /Qspectre
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d3b238b9a5bc01fa3ee053acdb3c7c84b95df71
ms.sourcegitcommit: 27b5712badd09a09c499d887e2e4cf2208a28603
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2018
ms.locfileid: "44385014"
---
# <a name="qspectre"></a>/ Qspectre

Derleyici belirli Spectre değişkeni 1 güvenlik açıklarını gidermek için yönergeler oluşturulmasını belirtir.

## <a name="syntax"></a>Sözdizimi

> **/Qspectre**

## <a name="remarks"></a>Açıklamalar

**/Qspectre** seçeneği bulunan Visual Studio 2017 sürüm 15.7 ve üzeri. Belirli azaltmak için yönergeler derleyiciye neden [Spectre güvenlik açıklarını](https://spectreattack.com/spectre.pdf). Olarak adlandırılan bu güvenlik açıklarına *kurgusal yürütme yan kanal saldırıları*, çok sayıda işletim sistemleri ve Intel, AMD, işlemcilerini dahil olmak üzere modern işlemciler etkiler ve ARM.

**/Qspectre** seçeneği varsayılan olarak kapalıdır.

İlk sürümde, **/qspectre** seçeneği yalnızca en iyi duruma getirilmiş kod üzerinde çalışır. Kodunuzu iyileştirme seçeneklerden herhangi biri ile derlemek emin olmanız gerekir (örneğin, [/O2 veya/O1](o1-o2-minimize-size-maximize-speed.md) ama [/Od](od-disable-debug.md)) azaltma uygulandığından emin olmak için. Benzer şekilde, kullanan herhangi bir kod İnceleme [#pragma en iyi duruma getirme ("stg", kapalı)](../../preprocessor/optimize.md).

### <a name="applicability"></a>Uygulanabilirlik

Kodunuzu bir güven sınırı aştığında veri çalışır sonra kullanmanızı öneririz **/qspectre** yeniden oluşturun ve olabildiğince çabuk bu sorunu gidermek için kodunuzu yeniden dağıtın. Yürütme etkileyebilecek güvenilir olmayan girişlere yükler kod bir güven sınırı aştığında veriler üzerinde çalışıyor kod örnekleri, örneğin, uzak yordam hale getiren kodu çağırır, güvenilmeyen girişler veya dosyalarını ayrıştırmak veya diğer yerel arası işlemi kullanır iletişim (IPC) arabirimler. Standart bir korumalı alana alma tekniklerini yeterli olmayabilir. Kodunuzu güven sınırının çapraz değil karar vermeden önce sanal dikkatli bir şekilde araştırmanız gerekir.

### <a name="availability"></a>Kullanılabilirlik

**/Qspectre** seçeneği, Visual Studio 2017 sürüm 15.5.5 ve şirket veya 23 Ocak 2018'den sonra yapılan tüm güncelleştirmeler için Microsoft Visual C++ Derleyicileri (MSVC) kullanılabilir. Visual Studio yükleyicisi, derleyici güncelleştirilecek ve tek tek bileşenleri olarak Spectre azaltılabilir kitaplıklarını yüklemek için kullanın. **/Qspectre** seçenek, ayrıca bir düzeltme eki Visual Studio 2015 güncelleştirme 3'te kullanılabilir. Daha fazla bilgi için [KB 4338871](https://support.microsoft.com/help/4338871).

Visual Studio 2017 sürüm 15.5 ve tüm önizlemeleri Visual Studio'nun sürüm 15.6 zaten belgelenmemiş bir seçenek dahil tüm sürümlerini **/d2guardspecload**, yani ilk davranışını eşdeğer   **/qspectre**. Kullanabileceğiniz **/d2guardspecload** derleyicisinin bu sürümü kodunuzda aynı risk azaltma işlemleri uygulamak için. Yapınızı kullanmak için lütfen güncelleştirme **/qspectre** seçeneği; destekleyen kapsayıcılar içinde **/qspectre** seçeneği derleyicinin sonraki sürümlerde yeni risk azaltma işlemleri de destekleyebilir.

### <a name="effect"></a>Efekt

**/Qspectre** seçeneği çıkarır Specter değişken 1, kontrol sınırları atlama azaltmak için kod [CVE-2017-5753](https://nvd.nist.gov/vuln/detail/CVE-2017-5753). Kurgusal bir kod yürütme engeli davranan yönergeleri ekleme çalışır. İşlemci Spekülasyon azaltmak için kullanılan özel yönergeler, işlemci ve kendi mikro-mimarisi bağlıdır ve gelecekteki derleyici sürümleri değişebilir.

Zaman **/qspectre** seçeneği etkin olduğunda, burada kurgusal yürütmeyi sınırları denetimleri atlayabilir ve barrier yönergelerini ekler örnekleri tanımlamak derleyici çalışır. Bir derleyici değişkeni 1 örnekleri tanımlamak için gerçekleştirebileceği çözümleme sınırları olduğunu dikkate almak önemlidir. Bu nedenle, tüm olası değişkeni 1 örnekleri altında işaretlenmiş bir garanti yoktur **/qspectre**.

### <a name="performance-impact"></a>Performans etkisi

Performans etkisini **/qspectre** birkaç çok büyük kod tabanlarında göz ardı edilebilir olmasını görülen kodunuzun altında performans garantisi yoktur, ancak **/qspectre** etkilenmez. Kodunuzu seçeneği performans üzerindeki etkisini belirlemek için Kıyaslama. Azaltma performans açısından kritik blok veya döngü içinde gerekmediğini biliyorsanız, risk azaltma seçmeli olarak kullanarak devre dışı bırakılabilir bir [__declspec(spectre(nomitigation))](../../cpp/spectre.md) yönergesi. Bu yönerge yalnızca destek derleyicilerde kullanılabilir olmayan **/d2guardspecload** seçeneği.

### <a name="required-libraries"></a>Gerekli kitaplıkları

**/Qspectre** derleyici seçeneği Spectre risk azaltma işlemleri sağlamak için oluşturulan çalışma zamanı kitaplıklarının sürümlerini örtük olarak bağlanan kod oluşturur. Bu kitaplıklar, Visual Studio Yükleyicisi'ni kullanarak yüklü olması gereken isteğe bağlı bileşenleri şunlardır:

- VC ++ 2017 sürüm *version_number* (x86 ve x64) Spectre için kitaplıklar
- Spectre azaltmaları ile Visual C++ ATL (x86/x64)
- Spectre azaltmaları ile x86/x64 için Visual C++ MFC

Kullanarak, kodunuzu derlemek, **/qspectre** ve bu kitaplıklar değildir yüklü, yapı sistemi raporları **uyarı MSB8038: Spectre riskini azaltma etkinleştirildi, ancak Spectre azaltılabilir kitaplıklar bulunamadı**. MFC veya ATL kodunuzu derlemek başarısız olur ve bağlayıcı gibi bir hata bildiriyor **LNK1104 önemli hatası: 'oldnames.lib' dosyası açılamıyor**, bu eksik kitaplıklar neden olabilir.

### <a name="additional-information"></a>Ek bilgiler

Daha fazla ayrıntı için lütfen resmi bakın [kurgusal yürütme yan kanal güvenlik açıklarına azaltmak için Microsoft Güvenlik Danışma ADV180002, rehberlik](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002). Kılavuzu Intel'in, kullanılabilir ayrıca [kurgusal yürütme yan kanal azaltmaları](https://software.intel.com/sites/default/files/managed/c5/63/336996-Speculative-Execution-Side-Channel-Mitigations.pdf)ve ARM, [önbellek Spekülasyon yan kanalları](https://developer.arm.com/-/media/Files/pdf/Cache_Speculation_Side-channels.pdf). Spectre ve Meltdown azaltmaları Windows özgü bakış için bkz: [Spectre ve Meltdown azaltmaları Windows sistemlerinde performans etkisini anlama](https://cloudblogs.microsoft.com/microsoftsecure/2018/01/09/understanding-the-performance-impact-of-spectre-and-meltdown-mitigations-on-windows-systems/) Microsoft Secure blogunda. Spectre güvenlik açığı MSVC risk azaltma işlemleri tarafından ele alınan genel bakış için bkz. [Spectre azaltmaları MSVC içinde](https://blogs.msdn.microsoft.com/vcblog/2018/01/15/spectre-mitigations-in-msvc./) Visual C++ Team blogunda.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Girin **/qspectre** derleyici seçeneğini **ek seçenekler** kutusu. Seçin **Tamam** değişikliği uygulamak için.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Q Seçenekler (Düşük Düzey İşlemler)](../../build/reference/q-options-low-level-operations.md)  
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)  
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)  
