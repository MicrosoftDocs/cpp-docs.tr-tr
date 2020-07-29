---
title: /guard (Denetim Akışı Korumasını Etkinleştirme)
ms.date: 11/04/2016
f1_keywords:
- /guard
- VC.Project.VCCLCompilerTool.ControlFlowGuard
ms.assetid: be495323-f59f-4cf3-a6b6-8ee69e6a19dd
ms.openlocfilehash: 8661f94e0ee35f8d5e2c8caba1fc01bbf4072876
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87190695"
---
# <a name="guard-enable-control-flow-guard"></a>/guard (Denetim Akışı Korumasını Etkinleştirme)

Denetim akışı koruyucusu güvenlik denetimlerinin derleyicisini oluşturmayı etkinleştirin.

## <a name="syntax"></a>Sözdizimi

```
/guard:cf[-]
```

## <a name="remarks"></a>Açıklamalar

**/Guard: CF** seçeneği derleyicinin derleme zamanında dolaylı çağrı hedefleri için denetim akışını çözümlemesine ve sonra çalışma zamanında hedefleri doğrulamak üzere kod eklemesini sağlar. Varsayılan olarak, **/Guard: CF** kapalıdır ve açıkça etkin olmalıdır. Bu seçeneği açıkça devre dışı bırakmak için **/Guard: CF-** kullanın.

**Visual Studio 2017 ve üzeri**: Bu seçenek **`switch`** , sıçrama tabloları oluşturan deyimler için koruyucuları ekler.

**/Guard: CF** denetim akışı koruyucusu (cfg) seçeneği belirtildiğinde, derleyici ve bağlayıcı, kodunuzun güvenliğinin aşılmasına yönelik denemeleri algılamak için ek çalışma zamanı güvenlik denetimleri ekler. Derleme ve bağlama sırasında, kodunuzdaki tüm dolaylı çağrılar, doğru çalıştırıldığında kodun ulaşabileceği her konumu bulacak şekilde çözümlenir. Bu bilgiler, ikili dosyalarınızdaki üst bilgilerdeki ek yapılar halinde depolanır. Derleyici Ayrıca kodunuzdaki her dolaylı çağrıdan önce bir denetim çıkarır ve hedefin doğrulanmış konumlardan biri olmasını sağlar. Denetim, CFG kullanan bir işletim sisteminde çalışma zamanında başarısız olursa, işletim sistemi programı kapatır.

Yazılım üzerinde yaygın bir saldırı, Extreme veya beklenmedik girdileri işlerken hataların avantajlarından yararlanır. Uygulamaya dikkatle hazırlanmış giriş, yürütülebilir kod işaretçisi içeren bir konumun üzerine yazabilir. Bu, denetim akışını saldırgan tarafından denetlenen koda yönlendirmek için kullanılabilir. CFG çalışma zamanı denetimleri çalıştırılabilirinizdeki veri bozulması hatalarını düzeltmez. Bunun yerine, bir saldırganın rastgele kod yürütmek için bunları kullanmasını daha zor hale getirir. CFG, kodunuzun işlev giriş noktaları dışındaki konumlara çağrıları engelleyen bir azaltma aracıdır. Veri Yürütme Engellemesi (DEP), [/GS](gs-buffer-security-check.md) Stack denetimleri ve [/DynamicBase](dynamicbase-use-address-space-layout-randomization.md) ve [/highentropyva](highentropyva-support-64-bit-aslr.md) adres alanı düzeni rastgele seçme (ASLR) kodunuzun bir yararlanma vektörü haline gelmesi ihtimaline benzer.

CFG Exploit azaltma tekniğinin kullanıldığı kodu derlemek için, **/Guard: CF** seçeneğinin her ikisine de derleyiciye ve bağlayıcıya geçirilmesi gerekir. İkili 'niz tek bir komut kullanılarak derlenirse `cl` , derleyici seçeneği bağlayıcıya geçirir. Ayrı olarak derleyip bağlarsanız, bu seçenek hem derleyici hem de bağlayıcı komutlarında ayarlanmalıdır. /DYNAMICBASE bağlayıcı seçeneği de gereklidir. İkilinin CFG verilerini içerdiğini doğrulamak için `dumpbin /headers /loadconfig` komutunu kullanın. CFG özellikli ikililer `Guard` , exe veya dll özellikleri listesinde bulunur ve koruma bayrakları `CF Instrumented` ve içerir `FID table present` .

**/Guard: CF** seçeneği [/Zi](z7-zi-zi-debug-information-format.md) (hata ayıklama bilgilerini düzenle ve devam et) veya [/clr](clr-common-language-runtime-compilation.md) (ortak dil çalışma zamanı derlemesi) ile uyumsuzdur.

**/Guard: CF** kullanılarak derlenen kod, seçeneği kullanılarak derlenmediği kitaplıklara ve nesne dosyalarıyla bağlantılı olabilir. Bu kod, ayrıca **/Guard: CF** seçeneği KULLANıLARAK ve cfg ile uyumlu bir işletim sisteminde ÇALıŞTıRıLDıĞıNDA, cfg koruması vardır. Seçeneği olmadan derlenen kod bir saldırıyı durdurmayacak olduğundan, derleme yaptığınız tüm koddaki seçeneğini kullanmanızı öneririz. CFG denetimleri için küçük bir çalışma zamanı maliyeti vardır ancak derleyici analizi, güvenli olması için kendini kanıtlamış olan dolaylı atlamalar üzerinde denetimleri iyileştirmenize çalışır.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**, **C/C++**, **kod oluşturma**' yı seçin.

1. **Denetim akışı koruyucusu** özelliğini seçin.

1. Açılan denetimde Denetim akışı korumasını etkinleştirmek için **Evet** ' i veya devre dışı bırakmak için **Hayır** ' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
