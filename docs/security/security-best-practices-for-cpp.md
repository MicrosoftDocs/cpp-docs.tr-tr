---
title: C++ için en iyi yöntemler | Microsoft Docs
ms.custom: ''
ms.date: 05/08/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- securitybestpracticesVC
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, security
- security [C++]
- security [C++], best practices
ms.assetid: 86acaccf-cdb4-4517-bd58-553618e3ec42
author: mikeblome
ms.author: mikeblome
ms.workload:
- cplusplus
ms.openlocfilehash: 35114d2fff4975cfca1681a7f5861c81bd979ef5
ms.sourcegitcommit: 96cdc2da0d8c3783cc2ce03bd280a5430e1ac01d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2018
---
# <a name="security-best-practices-for-c"></a>C++ İçin En İyi Güvenlik Uygulamaları

Bu makale, güvenlik araçları ve yöntemleri hakkında bilgi içerir. Bunları kullanarak uygulamaları saldırılarından yapmaz ancak saldırıların olasılığını azaltır.  
  
## <a name="visual-c-security-features"></a>Visual C++ güvenlik özellikleri

 Bu güvenlik özellikleri, Visual C++ derleyicisi ve bağlayıcısına oluşturulur:  
  
 [/guard (Denetim Akışı Korumasını Etkinleştirme)](../build/reference/guard-enable-control-flow-guard.md)  
 İçin denetim akışı dolaylı çağrı hedefler için derleme zamanında çözümlemek derleyici neden olur ve ardından çalışma zamanında hedefleri doğrulamak için kodu ekleyin.  
  
 [/GS (Arabellek Güvenlik Denetimi)](../build/reference/gs-buffer-security-check.md)  
 Taşma algılama kodunu yararlanılmasını, risk altındadır işlevler eklemek için derleyiciye. Bir taşma algılandığında, yürütme durduruldu. Varsayılan olarak, bu seçenek açıktır.  
  
 [/SAFESEH (Görüntüde Güvenli Özel Durum İşleyicileri Var)](../build/reference/safeseh-image-has-safe-exception-handlers.md)  
 Her özel durum işleyici adresini içeren bir tablo çıktı yansımasına eklenecek bağlayıcı bildirir. Çalışma zamanında, işletim sisteminin yalnızca yasal özel durum işleyicilerinin yürütüldüğünden emin olmak için bu tabloyu kullanır. Bu, çalışma zamanında kötü amaçlı saldırı tarafından tanıtılan özel durum işleyicileri yürütülmesini önlemeye yardımcı olur. Varsayılan olarak, bu değer kapalıdır.  
  
 [/ NXCOMPAT](../build/reference/nxcompat.md), [/NXCOMPAT (Veri Yürütme Engellemesi uyumlu)](../build/reference/nxcompat-compatible-with-data-execution-prevention.md)  
 Bu derleyici ve bağlayıcı seçenekleri Veri Yürütme Engellemesi (DEP) uyumluluk etkinleştirin. DEP CPU kod olmayan sayfa yürütülmesi karşı korur.  
  
 [/analyze (Kod Çözümleme)](../build/reference/analyze-code-analysis.md)  
 Bu derleyici seçeneği arabellek taşması, başlatılmamış bellek, null işaretçi başvurusunun kaldırılmasının ve bellek sızıntıları gibi olası güvenlik sorunlarını raporları kod analizini etkinleştirir. Varsayılan olarak, bu değer kapalıdır. Daha fazla bilgi için bkz: [C/C++ genel bakış için Kod Analizi](/visualstudio/code-quality/code-analysis-for-c-cpp-overview).  
  
 [/DYNAMICBASE (Adres boşluğu düzeni rastgele seçimini kullan)](../build/reference/dynamicbase-use-address-space-layout-randomization.md)  
 Bu bağlayıcı seçeneği farklı konumlarda yürütme başlangıcında belleğe yüklenmiş bir yürütülebilir görüntü oluşturulmasını sağlar. Bu seçenek ayrıca yığın konumunu bellekte daha az tahmin edilebilir hale getirir.  
  
## <a name="security-enhanced-crt"></a>Gelişmiş Güvenlik CRT  
 C çalışma zamanı kitaplığı (CRT) güvenlik riskleri taşıyan işlevlerin güvenli sürümleri dahil etmek için Genişletilebilir — Örneğin, denetlenmeyen `strcpy` dize kopyalama işlevi. Bu işlevler eski, güvenli olmayan sürümleri kullanım dışı olduğundan, bunlar derleme zamanı uyarılarına neden. Derleme Uyarıları gizleme yerine bu CRT işlevlerinin güvenli sürümlerini kullanmanızı öneririz. Daha fazla bilgi için bkz: [CRT'deki güvenlik özellikleri](../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="safeint-library"></a>SafeInt Kitaplığı  
 [SafeInt Kitaplığı](../windows/safeint-library.md) tamsayı taşan ve uygulama matematiksel işlemler gerçekleştirdiğinde oluşabilecek hatalarla sonuçlanmasını önlenmesine yardımcı olur. `SafeInt` Kitaplığı içerir [SafeInt sınıfı](../windows/safeint-class.md), [Safeıntexception sınıfı](../windows/safeintexception-class.md)ve birkaç [SafeInt işlevleri](../windows/safeint-functions.md).  
  
 `SafeInt` Sınıfı tamsayı taşmasına karşı korur ve sıfırla bölme yararlanan. Farklı türlerde değerler arasındaki karşılaştırmaları işlemek için kullanabilirsiniz. I iki hata işleme ilkeleri sağlar. Varsayılan ilke içindir `SafeInt` sınıfının bir `SafeIntException` sınıfı özel durumu rapor neden matematiksel işlem tamamlanamıyor. İkinci ilke içindir `SafeInt` program yürütme durdurmak için sınıf. Özel bir ilke tanımlayabilir.  
  
 Her `SafeInt` işlevi bir matematiksel işlemi bir hatadan korur. Aynı türüne dönüştürmeden iki farklı türde parametrelerini kullanabilirsiniz. Birden çok matematik işlemleri korumak için kullanmak `SafeInt` sınıfı.  
  
## <a name="checked-iterators"></a>Denetlenmiş Yineleyiciler  
 Denetlenen yineleyici kapsayıcı sınırları zorlar. Varsayılan olarak, denetlenen bir yineleyici sınırların dışında olduğunda, bir özel durum oluşturur ve program yürütme sona erer. Önişlemci için atanan değerlerin bağlı diğer yanıt düzeylerini tanımlar gibi denetlenen yineleyici sağlar  **\_güvenli\_SCL\_OLUŞTURUR** ve  **\_YİNELEYİCİ\_hata ayıklama\_düzeyi**. Örneğin,  **\_YİNELEYİCİ\_hata ayıklama\_düzeyi = 2**, kapsamlı bir doğruluk denetimi hata ayıklama modunda hangi kullanarak kullanılabilir hale getirilir denetlenen yineleyici sağlar onaylar. Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md) ve [ \_YİNELEYİCİ\_hata ayıklama\_düzeyi](../standard-library/iterator-debug-level.md).  
  
## <a name="code-analysis-for-managed-code"></a>Yönetilen Kod için Kod Analizi  
 Olarak da bilinen FxCop, yönetilen kod için Kod Analizi ile uyum.NET Framework tasarım yönergeleri için derlemeleri denetler. FxCop kodu ve aşağıdaki alanlarda hatalarını denetlemek için her derlemenin meta verilerini analiz eder:  
  
-   Kitaplık tasarımı  
  
-   Yerelleştirme  
  
-   Adlandırma kuralları  
  
-   Performans  
  
-   Güvenlik  
  
## <a name="windows-application-verifier"></a>Windows Uygulama Doğrulayıcısı  
 Uygulama Doğrulayıcısı (AppVerifier) olası uygulama uyumluluğu, kararlılık ve güvenlik sorunları belirlemenize yardımcı olabilir.  
  
 Bir uygulama işletim sisteminin nasıl kullandığı AppVerifier izler. Dosya sistemi, kayıt defteri, bellek izler ve uygulaması çalıştıran ve kaynak kodu önerir API'leri için ortaya çıkardığı sorunları giderir.  
  
 AppVerifier kullanabilirsiniz:  
  
-   Genel programlama hatalarına neden olası uygulama uyumluluğu hataları için test edin.  
  
-   Bir uygulama bellek ile ilgili sorunlar için inceleyin.  

-   Bir uygulamada olası güvenlik sorunlarını tanımlayın.  
  
 Kullanılabilir uygulama uyumluluğu araç AppVerifier yer [uygulama uyumluluğu](http://go.microsoft.com/fwlink/p/?linkid=91277) TechNet web sitesinde.  
  

## <a name="windows-user-accounts"></a>Windows kullanıcı hesapları  
 Yöneticiler grup ortaya koyar geliştiricilere ve--uzantı yoluyla--ait Windows kullanıcı hesapları müşteriler güvenlik risklerine kullanma. Daha fazla bilgi için bkz: [kullanıcılar grubunun bir üyesi olarak çalıştırma](running-as-a-member-of-the-users-group.md) ve [nasıl kullanıcı hesabı denetimi (UAC) etkiler uygulamanız](how-user-account-control-uac-affects-your-application.md).

## <a name="guidance-for-speculative-execution-side-channels"></a>Kurgusal yürütme yan kanalları Kılavuzu

Tanımayı ve C++ yazılım kurgusal yürütme yan kanal donanım güvenlik açıklarına karşı azaltmak hakkında daha fazla bilgi için bkz: [C++ Geliştirici Kılavuzu Speculative yürütme yan kanalları](developer-guidance-speculative-execution.md).

  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Security>   
 [Güvenlik](/dotnet/standard/security/index)   
 [Kullanıcı Hesabı Denetimi (UAC) Uygulamanızı Nasıl Etkiler](how-user-account-control-uac-affects-your-application.md)
