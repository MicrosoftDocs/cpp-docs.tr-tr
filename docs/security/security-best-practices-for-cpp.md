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
ms.openlocfilehash: 914498a79d3d3ddae08ae672aac35c6e913ef238
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988079"
---
# <a name="security-best-practices-for-c"></a>C++ İçin En İyi Güvenlik Uygulamaları

Bu makale, güvenlik araçları ve uygulamalar hakkında bilgiler içerir. Bunların kullanılması, uygulamaların saldırıya maruz olmamasına neden olmaz, ancak olası saldırıları daha az olabilir.

## <a name="visual-c-security-features"></a>Görsel C++ güvenlik özellikleri

Bu güvenlik özellikleri, Microsoft C++ derleyicisi ve bağlayıcı içinde yerleşik olarak bulunur:

[/guard (Denetim Akışı Korumasını Etkinleştirme)](../build/reference/guard-enable-control-flow-guard.md)<br/>
Derleyicinin derleme zamanında dolaylı çağrı hedefleri için denetim akışını çözümlemesine ve sonra çalışma zamanında hedefleri doğrulamak üzere kod eklemesini sağlar.

[/GS (Arabellek Güvenlik Denetimi)](../build/reference/gs-buffer-security-check.md)<br/>
Derleyicinin kullanım riski altında olan işlevlere taşma algılama kodu eklemesini sağlar. Bir taşma algılandığında yürütme durdurulur. Varsayılan olarak, bu seçenek açık olur.

[/SAFESEH (Görüntüde Güvenli Özel Durum İşleyicileri Var)](../build/reference/safeseh-image-has-safe-exception-handlers.md)<br/>
Bağlayıcının, her bir özel durum işleyicisinin adresini içeren bir tabloya Çıkış görüntüsüne dahil olmasını sağlar. Çalışma zamanında, işletim sistemi yalnızca meşru özel durum işleyicilerinin yürütüldüğünden emin olmak için bu tabloyu kullanır. Bu, çalışma zamanında kötü amaçlı bir saldırıya getirilen özel durum işleyicilerinin yürütülmesini önlemeye yardımcı olur. Varsayılan olarak, bu değer kapalıdır.

[/NXCOMPAT](../build/reference/nxcompat.md), [/NXCOMPAT (Veri Yürütme Engellemesi ile uyumlu)](../build/reference/nxcompat-compatible-with-data-execution-prevention.md) Bu derleyici ve bağlayıcı seçenekleri VERI Yürütme Engellemesi (DEP) uyumluluğunu etkinleştirir. DEP, CPU 'YU kod olmayan sayfaların yürütülmesine karşı korur.

[/analyze (Kod Çözümleme)](../build/reference/analyze-code-analysis.md)<br/>
Bu derleyici seçeneği, arabellek taşması, Başlatılmamış bellek, null işaretçi başvurusu ve bellek sızıntıları gibi olası güvenlik sorunlarını raporlayan Kod analizini etkinleştirir. Varsayılan olarak, bu değer kapalıdır. Daha fazla bilgi için bkz. [C/C++ Overview için kod analizi](/visualstudio/code-quality/code-analysis-for-c-cpp-overview).

[/DYNAMICBASE (Adres boşluğu düzeni rastgele seçimini kullan)](../build/reference/dynamicbase-use-address-space-layout-randomization.md)<br/>
Bu bağlayıcı seçeneği, yürütmenin başlangıcında bellekte farklı konumlara yüklenebilen yürütülebilir bir görüntünün oluşturulmasına olanak tanıyor. Bu seçenek ayrıca, bellekte yığın konumunun çok daha az öngörülebilir hale gelmesini sağlar.

## <a name="security-enhanced-crt"></a>Güvenliği artırılmış CRT

C çalışma zamanı kitaplığı (CRT), güvenlik riskleri ortaya çıkaran işlevlerin güvenli sürümlerini (örneğin, denetlenmeyen `strcpy` dize kopyalama işlevi) içerecek şekilde geliştirilmiştir. Bu işlevlerin daha eski ve güvenli olmayan sürümleri kullanım dışı olduğundan, derleme zamanı uyarılarına neden olur. Derleme uyarılarını bastırmak yerine bu CRT işlevlerinin güvenli sürümlerini kullanmanızı öneririz. Daha fazla bilgi için bkz. [CRT Içindeki güvenlik özellikleri](../c-runtime-library/security-features-in-the-crt.md).

## <a name="safeint-library"></a>SafeInt Kitaplığı

[SafeInt Kitaplığı](../safeint/safeint-library.md) , uygulamanın matematik işlemlerini gerçekleştirdiğinde ortaya çıkabilecek tamsayı taşlarının ve diğer açıktan etkilenme hatalarının önlenmesine yardımcı olur. `SafeInt` Kitaplığı [SafeInt sınıfını](../safeint/safeint-class.md), [Safeintexception sınıfını](../safeint/safeintexception-class.md)ve birkaç [SafeInt işlevini](../safeint/safeint-functions.md)içerir.

`SafeInt` sınıfı, tamsayı taşmasına karşı koruma ve sıfıra bölme açıklarını korur. Farklı türlerin değerleri arasındaki karşılaştırmaları işlemek için kullanabilirsiniz. İki hata işleme ilkesi sağlar. Varsayılan ilke, bir matematik işleminin neden tamamlanamadığına ilişkin bir `SafeIntException` sınıfı özel durumu oluşturması için `SafeInt` sınıfına yöneliktir. İkinci ilke, program yürütmeyi durdurmak için `SafeInt` sınıfına yöneliktir. Ayrıca, özel bir ilke tanımlayabilirsiniz.

Her `SafeInt` işlevi, bir matematik işlemini, açıktan etkilenme hatasından korur. Aynı türe dönüştürmeden iki farklı parametre türü kullanabilirsiniz. Birden çok matematik işlemini korumak için `SafeInt` sınıfını kullanın.

## <a name="checked-iterators"></a>Denetlenmiş Yineleyiciler

Denetlenen bir yineleyici kapsayıcı sınırlarını zorlar. Varsayılan olarak, denetlenen bir yineleyici sınırların dışında olduğunda bir özel durum oluşturur ve program yürütmesini sonlandırır. Denetlenen bir yineleyici, **\_güvenli\_SCL\_oluşturur** ve **\_Yineleyici\_hata ayıklama\_düzeyi**gibi, Önişlemci 'ye atanan değerlere bağlı diğer yanıt düzeylerini sağlar. Örneğin, **\_yineleyici\_hata ayıklama\_düzeyi = 2**ise, denetlenen bir yineleyici hata ayıklama modunda, onay kullanılarak kullanıma sunulan kapsamlı doğruluk denetimleri sağlar. Daha fazla bilgi için bkz. [onay yineleyiciler](../standard-library/checked-iterators.md) ve [\_Yineleyici\_hata ayıklama\_düzeyi](../standard-library/iterator-debug-level.md).

## <a name="code-analysis-for-managed-code"></a>Yönetilen Kod için Kod Analizi

FxCop olarak da bilinen yönetilen kod için kod analizi, the.NET Framework Tasarım yönergelerine uygunluk için derlemeleri denetler. FxCop, her derlemedeki kodu ve meta verileri çözümleyerek aşağıdaki alanlarda kusurları denetler:

- Kitaplık tasarımı

- Yerelleştirme

- Adlandırma kuralları

- Performans

- Güvenlik

## <a name="windows-application-verifier"></a>Windows Uygulama Doğrulayıcısı

[Uygulama doğrulayıcısı (AppVerifier)](/windows-hardware/drivers/debugger/enable-application-verifier) , olası uygulama uyumluluk, kararlılık ve güvenlik sorunlarını belirlemenize yardımcı olabilir.

AppVerifier, bir uygulamanın işletim sistemini nasıl kullandığını izler. Uygulama çalışırken dosya sistemi, kayıt defteri, bellek ve API 'Leri izler ve kapsamamakta olan sorunlara yönelik kaynak kodu düzeltmeleri önerir.

AppVerifier ' i kullanarak şunları yapabilirsiniz:

- Yaygın programlama hatalarından kaynaklanan olası uygulama uyumluluğu hatalarını test edin.

- Bellekle ilgili sorunlar için bir uygulamayı inceleyin.

- Bir uygulamadaki olası güvenlik sorunlarını belirler.

## <a name="windows-user-accounts"></a>Windows Kullanıcı hesapları

Yöneticiler grubuna ait olan Windows Kullanıcı hesaplarının kullanılması geliştiricileri ve------arasındaki müşterileri güvenlik risklerine sunar. Daha fazla bilgi için, bkz. [Kullanıcılar grubunun üyesi olarak çalışan](running-as-a-member-of-the-users-group.md) ve [Kullanıcı HESABı denetimi (UAC) uygulamanızı nasıl etkiler](how-user-account-control-uac-affects-your-application.md).

## <a name="guidance-for-speculative-execution-side-channels"></a>Spectıcı yürütme tarafı kanalları Kılavuzu

C++ Yazılımdaki öngörülebilir yürütme tarafı kanalı güvenlik açıklarına karşı nasıl karşılaştırılma ve hafiflebileceğine ilişkin bilgiler için, bkz [ C++ . kurgusal yürütme tarafı kanalları için Geliştirici Kılavuzu](developer-guidance-speculative-execution.md).

## <a name="see-also"></a>Ayrıca bkz.

<xref:System.Security> <br/>
[Security](/dotnet/standard/security/index)<br/>
[Kullanıcı Hesabı Denetimi (UAC) Uygulamanızı Nasıl Etkiler](how-user-account-control-uac-affects-your-application.md)
