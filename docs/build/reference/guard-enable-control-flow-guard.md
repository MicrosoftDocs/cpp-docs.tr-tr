---
title: -guard (denetim akışı korumasını etkinleştirme) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /guard
- VC.Project.VCCLCompilerTool.ControlFlowGuard
dev_langs:
- C++
ms.assetid: be495323-f59f-4cf3-a6b6-8ee69e6a19dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f480dde44073b6674985f4c814fdc0c476da0144
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45701473"
---
# <a name="guard-enable-control-flow-guard"></a>/guard (Denetim Akışı Korumasını Etkinleştirme)

Denetim akışı koruyucusu güvenlik denetimleri derleyici oluşturulmasını sağlar.

## <a name="syntax"></a>Sözdizimi

```
/guard:cf[-]
```

## <a name="remarks"></a>Açıklamalar

**/Guard: cf** seçenek neden olur, denetim akışı dolaylı çağrı hedefler için derleme zamanında çözümlemek derleyici ve çalışma zamanında hedefleri doğrulamak için kod eklenemedi. Varsayılan olarak, **/Guard: cf** kapalıdır ve açıkça etkinleştirilmesi gerekir. Açıkça bu seçeneği devre dışı bırakma, **/guard:cf-**.

**Visual Studio 2017 ve üzeri**: Bu seçenek için cf ekler **geçiş** atlama tablo oluşturma deyimleri.

Zaman **/Guard: cf** denetim akışı koruyucu (CFG) seçeneği belirtildiğinde, derleyici ve bağlayıcı kodunuzu tehlikeye girişimlerinin algılanmasına için ek çalışma zamanı güvenlik denetimleri Ekle. Derleme ve bağlama sırasında kod tüm dolaylı aramalar, doğru çalıştığı zaman, kod ulaşabileceği her konumu bulmak için analiz edilir. Bu bilgiler, ikili dosyalarınızı başlıklarına ek yapılardaki depolanır. Derleyici, ayrıca her dolaylı çağrı hedefi doğrulanmış konumlardan birine sağlar, kodunuzda önce bir denetimi ekler. Çalışma zamanında CFG kullanan bir işletim sistemi denetimi başarısız olursa, programın işletim sistemini kapatır.

Ortak bir yazılım saldırı, aşırı ya da beklenmeyen girişler işlemedeki hata avantajlarından yararlanır. Uygulama için özenle hazırlanmış Giriş işaretçisi yürütülebilir kod içeren bir konum üzerine yazabilir. Bu kod saldırgan tarafından denetlenen denetim akışı yeniden yönlendirmek için kullanılabilir. CFG çalışma zamanı denetimleri, yürütülebilir dosya içinde veri bozulması hataları düzeltin değil. Bunlar bunun yerine daha zor bir saldırganın rastgele kod yürütmek için bunları kullanmayı kolaylaştırır. CFG aramalar işlev giriş noktaları kodunuzda dışındaki konumlara engelleyen bir risk azaltma aracıdır. Nasıl yapılır benzer Veri Yürütme Engellemesi (DEP) [/GS](../../build/reference/gs-buffer-security-check.md) yığın denetimlerini ve [dynamıcbase](../../build/reference/dynamicbase-use-address-space-layout-randomization.md) ve [/highentropyva](../../build/reference/highentropyva-support-64-bit-aslr.md) adres alanı düzenini (aslr) düşük şansı kodunuzu yararlanma vektör haline gelir.

**/Guard: cf** derleyici için seçeneği geçirilen ve CFG kullanan kodu oluşturmak için bağlayıcı yararlanma riskini azaltma tekniği. İkili dosyanız tek bir kullanılarak oluşturulmuşsa `cl` komutu, derleyici seçeneğini bağlayıcıya geçirir. Derleme ve ayrı ayrı bağlantı seçeneği derleyici ve bağlayıcı komutları ayarlamanız gerekir. Dynamıcbase bağlayıcı seçeneği de gereklidir. İkili dosyanıza, CFG veri olduğunu doğrulamak için `dumpbin /headers /loadconfig` komutu. CFG özellikli ikili dosyalarınız `Guard` EXE veya DLL özelliklerine ve koruma bayrakları listeye dahil `CF Instrumented` ve `FID table present`.

**/Guard: cf** seçeneği ile uyumlu [/zi](../../build/reference/z7-zi-zi-debug-information-format.md) (Düzenle ve devam et hata ayıklama bilgileri) veya [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) (ortak dil çalışma zamanı derlemesi).

Kullanarak derlenmiş kod **/Guard: cf** kitaplıklarına bağlı ve nesne seçeneğini kullanarak derlenmemiş dosyaları. Kullanarak ayrıca bağlı olduğunda yalnızca bu kod, **/Guard: cf** seçeneği ve CFG kullanan bir işletim sisteminde çalıştırmak, CFG koruma bulunur. Seçeneği olmadan derlenmiş kod, bir saldırı durdurmaz olduğundan, derleme kod seçeneğini kullanmanızı öneririz. CFG denetimleri için maliyet küçük bir çalışma zamanı, ancak derleyici analiz güvenli olarak kanıtlanmış dolaylı atlar denetimler koyma iyileştirmek çalışır.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri**, **C/C++**, **kod oluşturma**.

1. Seçin **denetim akışı koruyucusu** özelliği.

1. Dropdown denetimi seçin **Evet** denetim akışı koruyucusu, etkinleştirme veya **Hayır** devre dışı.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)