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
ms.openlocfilehash: 12b2db55a393928683e65c8faca49595fbbebc51
ms.sourcegitcommit: 6e55aeb538b1c39af754f82d6f7738a18f5aa031
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87389967"
---
# <a name="security-best-practices-for-c"></a>C++ İçin En İyi Güvenlik Uygulamaları

Bu makale, güvenlik araçları ve uygulamalar hakkında bilgiler içerir. Bunların kullanılması, uygulamaların saldırıya maruz olmamasına neden olmaz, ancak olası saldırıları daha az olabilir.

## <a name="visual-c-security-features"></a>Visual C++ güvenlik özellikleri

Bu güvenlik özellikleri, Microsoft C++ derleyicisi ve bağlayıcı içinde yerleşik olarak bulunur:

[`/guard`(Denetim akışı korumasını etkinleştir)](../build/reference/guard-enable-control-flow-guard.md)<br/>
Derleyicinin derleme zamanında dolaylı çağrı hedefleri için denetim akışını çözümlemesine ve sonra çalışma zamanında hedefleri doğrulamak üzere kod eklemesini sağlar.

[`/GS`(Arabellek güvenlik denetimi)](../build/reference/gs-buffer-security-check.md)<br/>
Derleyicinin kullanım riski altında olan işlevlere taşma algılama kodu eklemesini sağlar. Bir taşma algılandığında yürütme durdurulur. Varsayılan olarak, bu seçenek açık olur.

[`/SAFESEH`(Görüntüde güvenli özel durum Işleyicileri vardır)](../build/reference/safeseh-image-has-safe-exception-handlers.md)<br/>
Bağlayıcının, her bir özel durum işleyicisinin adresini içeren bir tabloya Çıkış görüntüsüne dahil olmasını sağlar. Çalışma zamanında, işletim sistemi yalnızca meşru özel durum işleyicilerinin yürütüldüğünden emin olmak için bu tabloyu kullanır. Bu, çalışma zamanında kötü amaçlı bir saldırıya getirilen özel durum işleyicilerinin yürütülmesini önlemeye yardımcı olur. Varsayılan olarak, bu değer kapalıdır.

[`/NXCOMPAT`](../build/reference/nxcompat.md), [ `/NXCOMPAT` (Veri Yürütme Engellemesi ile uyumlu)](../build/reference/nxcompat-compatible-with-data-execution-prevention.md) Bu derleyici ve bağlayıcı seçenekleri Veri Yürütme Engellemesi (DEP) uyumluluğunu etkinleştirir. DEP, CPU 'YU kod olmayan sayfaların yürütülmesine karşı korur.

[`/analyze`(Kod analizi)](../build/reference/analyze-code-analysis.md)<br/>
Bu derleyici seçeneği, arabellek taşması, Başlatılmamış bellek, null işaretçi başvurusu ve bellek sızıntıları gibi olası güvenlik sorunlarını raporlayan Kod analizini etkinleştirir. Varsayılan olarak, bu değer kapalıdır. Daha fazla bilgi için bkz. [C/C++ Için kod analizi genel bakış](/cpp/code-quality/code-analysis-for-c-cpp-overview).

[`/DYNAMICBASE`(Adres boşluğu düzeni rastgele seçimini kullan)](../build/reference/dynamicbase-use-address-space-layout-randomization.md)<br/>
Bu bağlayıcı seçeneği, yürütmenin başlangıcında bellekte farklı konumlara yüklenebilen yürütülebilir bir görüntünün oluşturulmasına olanak tanıyor. Bu seçenek ayrıca, bellekte yığın konumunun çok daha az öngörülebilir hale gelmesini sağlar.

## <a name="security-enhanced-crt"></a>Güvenliği artırılmış CRT

C çalışma zamanı kitaplığı (CRT), güvenlik riskleri ortaya çıkaran işlevlerin güvenli sürümlerini (örneğin, denetlenmeyen dize kopyalama işlevi) içerecek şekilde geliştirilmiştir `strcpy` . Bu işlevlerin daha eski ve güvenli olmayan sürümleri kullanım dışı olduğundan, derleme zamanı uyarılarına neden olur. Derleme uyarılarını bastırmak yerine bu CRT işlevlerinin güvenli sürümlerini kullanmanızı öneririz. Daha fazla bilgi için bkz. [CRT Içindeki güvenlik özellikleri](../c-runtime-library/security-features-in-the-crt.md).

## <a name="safeint-library"></a>SafeInt Kitaplığı

[SafeInt Kitaplığı](../safeint/safeint-library.md) , uygulamanın matematik işlemlerini gerçekleştirdiğinde ortaya çıkabilecek tamsayı taşlarının ve diğer açıktan etkilenme hatalarının önlenmesine yardımcı olur. `SafeInt`Kitaplık [SafeInt sınıfını](../safeint/safeint-class.md), [safeintexception sınıfını](../safeint/safeintexception-class.md)ve birkaç [SafeInt işlevini](../safeint/safeint-functions.md)içerir.

`SafeInt`Sınıfı, tamsayı taşmasına karşı koruma ve sıfıra bölme açıklarını korur. Farklı türlerin değerleri arasındaki karşılaştırmaları işlemek için kullanabilirsiniz. İki hata işleme ilkesi sağlar. Varsayılan ilke, `SafeInt` sınıfının `SafeIntException` matematiksel bir işlemin neden tamamlanamadığına ilişkin bir sınıf özel durumu oluşturması için kullanılır. İkinci ilke, `SafeInt` Program yürütmesini durdurmak için sınıfına yöneliktir. Ayrıca, özel bir ilke tanımlayabilirsiniz.

Her `SafeInt` işlev, bir matematik işlemini, açıktan yararlanma hatasından korur. Aynı türe dönüştürmeden iki farklı parametre türü kullanabilirsiniz. Birden çok matematik işlemini korumak için sınıfını kullanın `SafeInt` .

## <a name="checked-iterators"></a>Denetlenmiş Yineleyiciler

Denetlenen bir yineleyici kapsayıcı sınırlarını zorlar. Varsayılan olarak, denetlenen bir yineleyici sınırların dışında olduğunda bir özel durum oluşturur ve program yürütmesini sonlandırır. Denetlenen bir yineleyici, ve gibi Önişlemci tanımları için atanan değerlere bağlı diğer yanıt düzeylerini sağlar `_SECURE_SCL_THROWS` `_ITERATOR_DEBUG_LEVEL` . Örneğin, `_ITERATOR_DEBUG_LEVEL=2` denetlenen bir yineleyici, hata ayıklama modunda, onaylar kullanılarak sunulan kapsamlı doğruluk denetimleri sağlar. Daha fazla bilgi için bkz. [onay yineleyiciler](../standard-library/checked-iterators.md) ve [`_ITERATOR_DEBUG_LEVEL`](../standard-library/iterator-debug-level.md) .

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

C++ yazılımıyla ilgili öngörülebilir yürütme tarafı kanal donanım güvenlik açıklarına karşı girintileme ve azaltma hakkında daha fazla bilgi için bkz. [kurgusal yürütme tarafı kanalları için C++ Geliştirici Kılavuzu](developer-guidance-speculative-execution.md).

## <a name="see-also"></a>Ayrıca bkz.

<xref:System.Security> <br/>
[Güvenlik](/dotnet/standard/security/index)<br/>
[Kullanıcı hesabı denetimi (UAC) uygulamanızı nasıl etkiler](how-user-account-control-uac-affects-your-application.md)
