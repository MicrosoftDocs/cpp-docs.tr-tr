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
ms.openlocfilehash: 3d87850ae5413ccf876eb4d4b44b34e34527ef9a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379425"
---
# <a name="qspectre"></a>/ Qspectre

Belirli Spectre değişken 1 güvenlik açıklarını azaltmak için yönergeler derleyici nesil belirtir.

## <a name="syntax"></a>Sözdizimi

> **/Qspectre**

## <a name="remarks"></a>Açıklamalar

**/Qspectre** seçeneği neden belirli azaltmak için yönergeler eklemek derleyici [Spectre güvenlik açıkları](https://spectreattack.com/spectre.pdf). Adlı açıklarından *kurgusal yürütme yan kanal saldırıları*, çok sayıda işletim sistemleri ve Intel, AMD, işlemcilerini dahil modern işlemciler etkiler ve ARM.

**/Qspectre** seçeneği varsayılan olarak kapalıdır.

İlk sürümde, **/Qspectre** seçenek yalnızca en iyi duruma getirilmiş kodu üzerinde çalışır. En iyi duruma getirme seçenekleri biriyle kodunuzu derleyin emin olmanız gerekir (örneğin, [O2 veya /O1](o1-o2-minimize-size-maximize-speed.md) ama [/Od](od-disable-debug.md)) azaltma uygulandığından emin olmak için. Benzer şekilde, kullanan herhangi bir kod İnceleme [#pragma en iyi duruma getirme ("stg", kapalı)](../../preprocessor/optimize.md).

### <a name="applicability"></a>Uygulanabilirlik

Kodunuzu bir güven sınırı yayılan veriler üzerinde çalışıyor sonra kullanmanız önerilir **/Qspectre** yeniden oluşturun ve bu sorunu hemen azaltmak için kodunuzu yeniden dağıtmak için seçeneği. Yürütme etkileyebilir güvenilmeyen giriş yükler kod güven sınırının yayılan veriler üzerinde çalışıyor kod örnekleri içerir, örneğin, uzak yordam yapan kod çağırır, güvenilmeyen giriş veya dosyaları ayrıştırır veya diğer yerel arası işlem kullanır iletişim (IPC) arabirimleri. Standart korumalı alan teknikleri yeterli olmayabilir. Kodunuzu bir güven sınırının çapraz değil karar vermeden önce sanal dikkatle araştırmanız gerekir.

### <a name="availability"></a>Kullanılabilirlik

**/Qspectre** seçenek, Visual Studio 2017 sürüm 15.5.5 ve ve 23 Ocak 2018 sonrasında yapılan tüm güncelleştirmeler için Microsoft Visual C++ Derleyicileri (MSVC) kullanılabilir.

Visual Studio 2017 sürüm 15,5 ve tüm önizlemeler, Visual Studio sürümü 15,6 zaten belgelenmemiş bir seçenek dahil tüm sürümleri **/d2guardspecload**, yani ilk davranışını eşdeğer **/Qspectre**. Kullanabileceğiniz **/d2guardspecload** derleyici'nın bu sürümlerini kodunuzda aynı Azaltıcı uygulamak için. Lütfen kullanmak için yapılandırma güncelleştirmesi **/Qspectre** seçeneği; destek derleyicileri içinde **/Qspectre** seçeneği yeni Azaltıcı Etkenler de derleyici sonraki sürümlerini destekleyebilir.

### <a name="effect"></a>Efekt

**/Qspectre** seçeneği çıkarır Specter değişken 1, sınırların atlama denetleyin, azaltmak için kod [CVE 2017 5753](https://nvd.nist.gov/vuln/detail/CVE-2017-5753). Bir kurgusal kodu yürütme engelle hareket yönerge ekleme çalışır. İşlemci Spekülasyon azaltmak için kullanılan özel yönergeler işlemci ve onun mikro mimarisi bağlıdır ve gelecekte derleyici sürümlerinde değişebilir.

Zaman **/Qspectre** seçeneği etkin olduğunda, derleyici burada kurgusal yürütme sınırları denetimleri atlayabilir ve engel yönergeleri ekler örnekleri tanımlamaya çalışır. Derleyici değişken 1 örneklerini tanımlamak üzere gerçekleştirebileceğiniz çözümleme sınırları olduğunu dikkate almak önemlidir. Bu nedenle, değişken 1 olası tüm kopyalarını altında izleme garantisi yoktur **/Qspectre**.

### <a name="performance-impact"></a>Performans etkisi

Performans etkisini **/Qspectre** birkaç çok büyük kod temelleri içinde düşünülerek olmasını görülen ancak garanti kodunuzun altında performans **/Qspectre** etkilenmemesini kalır. Kodunuzu seçeneği performans üzerindeki etkisini belirlemek için Kıyaslama. Azaltma bir performans açısından kritik blok veya döngü gerekli olmadığını biliyorsanız, azaltma seçmeli olarak kullanarak devre dışı bırakılabilir bir [__declspec(spectre(nomitigation))](../../cpp/spectre.md) yönergesi. Bu yönerge yalnızca destek derleyicileri içinde kullanılabilir değil **/d2guardspecload** seçeneği.

### <a name="additional-information"></a>Ek bilgiler

Daha fazla ayrıntı için lütfen resmi bkz [Microsoft güvenlik önerisi ADV180002, kılavuzu kurgusal yürütme yan kanal güvenlik açıkları azaltmak için](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002). Kılavuzu kullanılabilir Ayrıca, Intel'in [kurgusal yürütme yan kanal Azaltıcı](https://software.intel.com/sites/default/files/managed/c5/63/336996-Speculative-Execution-Side-Channel-Mitigations.pdf)ve ARM, [önbellek Spekülasyon yan-kanalları](https://developer.arm.com/-/media/Files/pdf/Cache_Speculation_Side-channels.pdf). Spectre ve Meltdown Azaltıcı Etkenler Windows'a özgü bakış için bkz: [Spectre ve Meltdown Azaltıcı Etkenler Windows sistemlerinde performans etkisini anlama](https://cloudblogs.microsoft.com/microsoftsecure/2018/01/09/understanding-the-performance-impact-of-spectre-and-meltdown-mitigations-on-windows-systems/) Microsoft Secure blogunda. MSVC Azaltıcı Etkenler tarafından ele Spectre güvenlik açığı genel bakış için bkz: [Spectre Azaltıcı MSVC içinde](https://blogs.msdn.microsoft.com/vcblog/2018/01/15/spectre-mitigations-in-msvc./) Visual C++ ekip blogunda.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Girin **/Qspectre** derleyici seçeneği **ek seçenekler** kutusu. Seçin **Tamam** değişikliği uygulamak için.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Q Seçenekler (Düşük Düzey İşlemler)](../../build/reference/q-options-low-level-operations.md)  
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)  
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)  
