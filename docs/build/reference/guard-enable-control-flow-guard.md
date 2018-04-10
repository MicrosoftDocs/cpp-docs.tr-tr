---
title: -guard (etkinleştir denetim akışı koruma) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- /guard
- VC.Project.VCCLCompilerTool.ControlFlowGuard
dev_langs:
- C++
ms.assetid: be495323-f59f-4cf3-a6b6-8ee69e6a19dd
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e7f87c101122b8f74e3bffefd42b1d9a9ddc55c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="guard-enable-control-flow-guard"></a>/guard (Denetim Akışı Korumasını Etkinleştirme)
Denetim akışı koruyucu güvenlik denetimlerini derleyici nesil etkinleştirin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/guard:cf[-]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **/Guard:cf** seçeneği dolaylı çağrı hedefleri için denetim akışı derleme zamanında çözümlemek derleyicinin neden olur ve ardından çalışma zamanında hedefleri doğrulamak için kodu ekleyin. Varsayılan olarak, **/guard:cf** kapalıdır ve açıkça etkinleştirilmesi gerekir. Açıkça bu seçenek devre dışı bırakma **/guard:cf-**.  
  
 Zaman **/guard:cf** denetim akışı koruma (CFG) seçeneği belirtildiğinde, derleyici ve bağlayıcı kodunuzu bozma girişimlerini algılamak için ek çalışma zamanı güvenlik denetimlerini ekleyin. Derleme ve bağlama sırasında kodunuzdaki tüm dolaylı çağrıları, doğru çalıştığı zaman koda ulaşıp ulaşamadığını her konum bulmak için incelenir. Bu bilgiler, ikili dosyaları başlıklarına fazladan yapıları depolanır. Derleyici de hedef doğrulanmış konumlardan birini sağlar, kodunuzda dolaylı her çağrıdan önce onay yerleştirir. Çalışma zamanında CFG uyumlu bir işletim sisteminde denetimi başarısız olursa, işletim sistemi programı kapatır.  
  
 Ortak bir yazılım saldırı aşırı veya beklenmeyen girişleri işlemedeki hatalar yararlanır. Uygulama dikkatle hazırlanmış giriş yürütülebilir kod gösteren bir işaretçi içeren bir konum üzerine yazabilir. Bu kod saldırgan tarafından denetlenen denetim akışı yönlendirmek için kullanılabilir. CFG çalışma zamanı denetimleri, yürütülebilir dosya içinde veri bozulması hataları düzeltin değil. Bunlar bunun yerine daha rastgele kod yürütmek için onları kullanmak bir saldırganın zorlaştırır. CFG kodunuzdaki işlev giriş noktaları dışındaki konumlara çağrıları engelleyen bir azaltma aracıdır. Nasıl yapılır benzer Veri Yürütme Engellemesi (DEP) [/GS](../../build/reference/gs-buffer-security-check.md) yığın denetimleri ve [/DYNAMICBASE](../../build/reference/dynamicbase-use-address-space-layout-randomization.md) ve [/highentropyva](../../build/reference/highentropyva-support-64-bit-aslr.md) adres boşluğu düzeni rastgele seçimini (ASLR) düşük kodunuzu yararlanma vektör hale chances.  
  
 **/Guard:cf** derleyici için seçeneği geçirilen ve CFG kullanan kodu oluşturmak için bağlayıcı azaltma teknik yararlanma. Tek bir kullanarak ikili dosyanız oluşturulduysa `cl` komutunu derleyici seçeneği bağlayıcıya geçirir. Derleme ve ayrı bağlantı seçeneği derleyici ve bağlayıcı komutları ayarlamanız gerekir. /DYNAMICBASE bağlayıcı seçeneği de gereklidir. İkili dosyanız CFG verilerin olduğunu doğrulamak için kullanılan `dumpbin /headers /loadconfig` komutu. CFG etkin ikilileri sahibi `Guard` EXE veya DLL özelliklerine ve koruma bayrakları listeye dahil `CF Instrumented` ve `FID table present`.  
  
 **/Guard:cf** seçeneği ile uyumlu [/zı](../../build/reference/z7-zi-zi-debug-information-format.md) (Düzenle ve devam et hata ayıklama bilgileri) veya [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) (ortak dil çalışma zamanı derlemesi).  
  
 Kullanarak derlenmiş kod **/guard:cf** kitaplıklara bağlanabilir ve nesne seçeneğini kullanarak derlenmemiş dosyaları. Ayrıca kullanarak bağlandığında yalnızca bu kodu **/guard:cf** seçeneği ve CFG uyumlu bir işletim sisteminde çalıştırmak, CFG korumaya sahip. Seçeneği olmadan derlenmiş kod saldırının durdurmaz olduğundan, derleme kodu seçeneğini kullanmanızı öneririz. CFG denetimleri için maliyet küçük bir çalışma zamanı yoktur, ancak güvenli olması için kanıtlanmış dolaylı atlar denetimler koyma iyileştirmek derleyici analiz çalışır.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **yapılandırma özellikleri**, **C/C++**, **kod oluşturma**.  
  
3.  Seçin **denetim akışı koruma** özelliği.  
  
4.  Açılır liste denetiminde seçin **Evet** akış denetimi koruma etkinleştirmek için veya **Hayır** devre dışı bırakmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)