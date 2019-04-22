---
title: C++ İçin En İyi Güvenlik Uygulamaları
ms.date: 05/08/2018
f1_keywords:
- securitybestpracticesVC
helpviewer_keywords:
- Visual C++, security
- security [C++]
- security [C++], best practices
ms.assetid: 86acaccf-cdb4-4517-bd58-553618e3ec42
ms.openlocfilehash: bc449d0bbf222391868dc7586e0245fd6e8cd2ac
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58769868"
---
# <a name="security-best-practices-for-c"></a>C++ İçin En İyi Güvenlik Uygulamaları

Bu makale, güvenlik araçları ve uygulamaları hakkında bilgi içerir. Bunları kullanarak uygulamaları saldırılarından yapmaz, ancak bu saldırıların düşürür.

## <a name="visual-c-security-features"></a>Visual C++ güvenlik özellikleri

Bu güvenlik özellikleri, Visual C++ Derleyici ve bağlayıcı yerleşik:

[/guard (Denetim Akışı Korumasını Etkinleştirme)](../build/reference/guard-enable-control-flow-guard.md)<br/>
Denetim akışı dolaylı çağrı hedefler için derleme zamanında çözümlemek derleyicinin ve çalışma zamanında hedefleri doğrulamak için kod eklenemedi.

[/GS (Arabellek Güvenlik Denetimi)](../build/reference/gs-buffer-security-check.md)<br/>
Derleyicinin yararlanılmasını bir risk altında olan işlevler halinde taşması algılama kod eklemesini söyler. Bir taşma algılandığında, yürütme durduruldu. Varsayılan olarak, bu seçenek açıktır.

[/SAFESEH (Görüntüde Güvenli Özel Durum İşleyicileri Var)](../build/reference/safeseh-image-has-safe-exception-handlers.md)<br/>
Her özel durum işleyicisi adresini içeren bir tablo çıktı görüntüsüne dahil etme konusunda bilgilendirir. Çalışma zamanında, işletim sisteminin yalnızca yasal bir özel durum işleyicileri yürütüldüğünden emin olmak için bu tabloyu kullanır. Bu, çalışma zamanında bir kötü amaçlı saldırı tarafından sunulan özel durum işleyicileri yürütülmesini önlemeye yardımcı olur. Varsayılan olarak, bu değer kapalıdır.

[/ NXCOMPAT](../build/reference/nxcompat.md), [/NXCOMPAT (veri yürütme önlemesi ile uyumlu)](../build/reference/nxcompat-compatible-with-data-execution-prevention.md) Veri Yürütme Engellemesi (DEP) uyumluluk Bu derleyici ve bağlayıcı seçenekleri etkinleştirin. DEP CPU olmayan kod sayfaları yürütülmesini karşı korur.

[/analyze (Kod Çözümleme)](../build/reference/analyze-code-analysis.md)<br/>
Bu derleyici seçeneğini arabellek taşması, başlatılmamış bellek, null işaretçisinin başvurusunun kaldırılması ve bellek sızıntıları gibi olası güvenlik sorunlarını raporları kod analizini etkinleştirir. Varsayılan olarak, bu değer kapalıdır. Daha fazla bilgi için [C/C++ genel bakış için Kod Analizi](/visualstudio/code-quality/code-analysis-for-c-cpp-overview).

[/DYNAMICBASE (Adres boşluğu düzeni rastgele seçimini kullan)](../build/reference/dynamicbase-use-address-space-layout-randomization.md)<br/>
Bu bağlayıcı seçeneğini farklı konumlarda yürütme başına belleğe yüklenebilen bir yürütülebilir görüntü oluşturmayı etkinleştirir. Bu seçenek de yığın konumunu bellekte çok daha az tahmin edilebilir olmasını sağlar.

## <a name="security-enhanced-crt"></a>Gelişmiş Güvenlik CRT

C çalışma zamanı kitaplığı (CRT) güvenlik riskleri konusunda sizi uyarmayı işlevlerin güvenli sürümleri içerecek şekilde genişletilmiş — Örneğin, denetlenmemiş `strcpy` dize kopyalama işlevi. Bu işlevlerin daha eski, güvenli olmayan sürümler kullanım dışı olduğundan, derleme zamanı uyarılarına neden olur. Derleme uyarılarını bastırmak yerine bu CRT işlevlerin güvenli sürümleri kullanmanızı öneririz. Daha fazla bilgi için [CRT'deki güvenlik özellikleri](../c-runtime-library/security-features-in-the-crt.md).

## <a name="safeint-library"></a>SafeInt Kitaplığı

[SafeInt Kitaplığı](../safeint/safeint-library.md) tamsayı taşıyor ve uygulama matematiksel işlemler gerçekleştirdiğinde oluşabilecek açıklardan diğer hataları önlemeye yardımcı olur. `SafeInt` Kitaplığı içerir [SafeInt sınıfı](../safeint/safeint-class.md), [Safeıntexception sınıfı](../safeint/safeintexception-class.md)ve birkaç [SafeInt işlevleri](../safeint/safeint-functions.md).

`SafeInt` Sıfırla bölme yararlanan ve sınıfı tamsayı taşması karşı korur. Farklı türlerde değerler arasında karşılaştırma işlemek için bunu kullanabilirsiniz. Bu iki hata işleme ilkeleri sağlar. İçin varsayılan ilkedir `SafeInt` sınıfının bir `SafeIntException` sınıfı özel durumu raporuna neden bir matematiksel işlem tamamlanamıyor. İkinci ilkeyi içindir `SafeInt` sınıfı programın yürütülmesini durdurur. Ayrıca, özel bir ilke de tanımlayabilirsiniz.

Her `SafeInt` işlevi, bir hatadan bir matematiksel işlem korur. İki farklı tür parametreleri aynı türe dönüştürme olmadan kullanabilirsiniz. Birden çok matematik işlemi korumak için `SafeInt` sınıfı.

## <a name="checked-iterators"></a>Denetlenmiş Yineleyiciler

Denetlenen bir yineleyiciye kapsayıcı sınırlarının zorlar. Varsayılan olarak, denetlenen bir yineleyiciye sınırların dışında olduğunda, bir özel durum oluşturur ve program yürütme sona erer. Denetlenen bir yineleyiciye önişlemci için atanan değerleri bağımlı diğer yanıt düzeyleri tanımlar gibi sağlar  **\_güvenli\_SCL\_OLUŞTURUR** ve  **\_YİNELEYİCİ\_hata ayıklama\_düzeyi**. Örneğin,  **\_YİNELEYİCİ\_hata ayıklama\_düzeyi = 2**, denetlenen bir yineleyiciye kapsamlı bir doğruluk hangi kullanarak eserleridir hata ayıklama modunda denetimi sağlar onaylar. Daha fazla bilgi için [Checked Iterators](../standard-library/checked-iterators.md) ve [ \_YİNELEYİCİ\_hata ayıklama\_düzeyi](../standard-library/iterator-debug-level.md).

## <a name="code-analysis-for-managed-code"></a>Yönetilen Kod için Kod Analizi

FxCop olarak da bilinir, yönetilen kod için Kod Analizi derlemeler.NET Framework tasarım yönergeleri uyumluluk için denetler. FxCop kod ve aşağıdaki alanlarda hataları denetlemek için her bir derleme içindeki meta verileri analiz eder:

- Kitaplık tasarımı

- Yerelleştirme

- Adlandırma kuralları

- Performans

- Güvenlik

## <a name="windows-application-verifier"></a>Windows Uygulama Doğrulayıcısı

[Uygulama Doğrulayıcısı (AppVerifier)](/windows-hardware/drivers/debugger/application-verifier
) olası uygulama uyumluluğu, kararlılık ve güvenlik sorunlarını belirlemenize yardımcı olabilir.

AppVerifier, uygulama işletim sisteminin nasıl kullandığı izler. Dosya sistemi, kayıt defteri, bellek izler ve uygulama çalıştıran ve kaynak kodu önerir API'leri ortaya çıkardığı için sorunları giderir.

AppVerifier için kullanabilirsiniz:

- Ortak programlama hatalarına neden olası uygulama uyumluluğu hataları için test edin.

- Bir uygulama için bellekle ilgili sorunları inceleyin.

- Bir uygulamada olası güvenlik sorunlarını belirleyin.

## <a name="windows-user-accounts"></a>Windows kullanıcı hesapları

Yöneticiler grubu kullanıma sunan geliştiricilere ve--uzantısı--ait Windows kullanıcı hesapları müşterilerin güvenlik risklerine kullanma. Daha fazla bilgi için [kullanıcılar grubunun bir üyesi olarak çalıştırma](running-as-a-member-of-the-users-group.md) ve [nasıl kullanıcı hesabı denetimi (UAC) etkiler uygulamanız](how-user-account-control-uac-affects-your-application.md).

## <a name="guidance-for-speculative-execution-side-channels"></a>Kurgusal yürütme yan kanal için yönergeler

Tanımayı ve C++ yazılım kurgusal yürütme yan kanal donanım güvenlik açıklarına karşı azaltmak hakkında daha fazla bilgi için bkz. [C++ Geliştirici Kılavuzu için kurgusal yürütme yan kanal](developer-guidance-speculative-execution.md).

## <a name="see-also"></a>Ayrıca bkz.

<xref:System.Security> <br/>
[Güvenlik](/dotnet/standard/security/index)<br/>
[Kullanıcı Hesabı Denetimi (UAC) Uygulamanızı Nasıl Etkiler](how-user-account-control-uac-affects-your-application.md)
