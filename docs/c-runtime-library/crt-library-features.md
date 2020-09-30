---
title: CRT Kitaplık Özellikleri
description: Microsoft C çalışma zamanı kitaplıklarını ve bunlarla ilişkili derleyici seçeneklerini ve önişlemci yönergelerini içeren dosyaların listesi.
ms.date: 09/03/2020
ms.topic: conceptual
helpviewer_keywords:
- MSVCR71.dll
- libraries [C++], multithreaded
- library files, run-time
- LIBCMT.lib
- LIBCP.lib
- LIBCPMT.lib
- run-time libraries, C
- CRT, release versions
- MSVCP71.dll
- LIBC.lib
- libraries [C++]
- libraries [C++], run-time
- linking [C++], libraries
ms.assetid: a889fd39-807d-48f2-807f-81492612463f
ms.openlocfilehash: 0e0d34c1121f0bf4e2fdfabc521e0365084761eb
ms.sourcegitcommit: 9451db8480992017c46f9d2df23fb17b503bbe74
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2020
ms.locfileid: "91589789"
---
# <a name="crt-library-features"></a>CRT Kitaplık Özellikleri

Bu konuda, C çalışma zamanı kitaplıklarını ve bunlarla ilişkili derleyici seçeneklerini ve önişlemci yönergelerini oluşturan çeşitli. lib dosyaları ele alınmaktadır.

## <a name="c-run-time-libraries-crt"></a>C Çalışma Zamanı Kitaplıkları (CRT)

C çalışma zamanı kitaplığı (CRT), ISO C99 standart kitaplığı 'nı içeren C++ standart kitaplığı 'nın bir parçasıdır. CRT uygulayan Visual C++ kitaplıkları yerel kod geliştirmeyi ve hem karma yerel hem de yönetilen kodu destekler. CRT 'nin tüm sürümleri çoklu iş parçacıklı geliştirmeyi destekler. Kitaplıkların çoğu hem statik bağlamayı, hem de kodunuzun ortak DLL dosyalarını kullanmasına izin vermek için dinamik bağlamayı destekler.

Visual Studio 2015 ' den başlayarak, CRT yeni ikililer yeniden düzenlenmiş. Universal CRT (UCRT), standart C99 CRT kitaplığı tarafından dışarıya aktarılmış işlevleri ve genel değerleri içerir. UıCRT artık bir Windows bileşenidir ve Windows 10 ' un bir parçası olarak gelir. UıCRT için statik kitaplık, DLL içeri aktarma kitaplığı ve üst bilgi dosyaları artık Windows 10 SDK 'da bulunur. Visual C++ yüklediğinizde, Visual Studio Kurulumu UCRT 'yi kullanmak için gereken Windows 10 SDK alt kümesini yükler. UCRT 'yi, Visual Studio 2015 ve sonraki sürümleri tarafından desteklenen herhangi bir Windows sürümünde kullanabilirsiniz. Windows 10 dışındaki desteklenen Windows sürümleri için VCRedist kullanarak yeniden dağıtabilirsiniz. Daha fazla bilgi için bkz. [Visual C++ dosyalarını yeniden dağıtma](../windows/redistributing-visual-cpp-files.md).

Aşağıdaki tablo UCRT uygulayan kitaplıkları listeler.

| Kitaplık | İlişkili DLL | Özellikler | Seçenek | Ön işlemci yönergeleri |
|--|--|--|--|--|
| *`libucrt.lib`* | Hiçbiri | UCRT 'yi kodunuza statik olarak bağlar. | **`/MT`** | `_MT` |
| *`libucrtd.lib`* | Hiçbiri | Statik bağlama için UCRT 'nin hata ayıklama sürümü. Yeniden dağıtılabilir değil. | **`/MTd`** | `_DEBUG`, `_MT` |
| *`ucrt.lib`* | *`ucrtbase.dll`* | UıCRT için DLL içeri aktarma kitaplığı. | **`/MD`** | `_MT`, `_DLL` |
| *`ucrtd.lib`* | *`ucrtbased.dll`* | UıCRT 'nin hata ayıklama sürümü için DLL içeri aktarma kitaplığı. Yeniden dağıtılabilir değil. | **`/MDd`** | `_DEBUG`, `_MT`, `_DLL` |

Vcruntime kitaplığı, özel durum işleme ve hata ayıklama desteği, çalışma zamanı denetimleri ve tür bilgileri, uygulama ayrıntıları ve belirli genişletilmiş kitaplık işlevleri gibi Visual C++ CRT uygulamaya özgü kod içerir. Bu kitaplık, kullanılan derleyicinin sürümüne özgüdür.

Bu tablo vcruntime kitaplığını uygulayan kitaplıkları listeler.

| Kitaplık | İlişkili DLL | Özellikler | Seçenek | Ön işlemci yönergeleri |
|--|--|--|--|--|
| *`libvcruntime.lib`* | Hiçbiri | Kodunuzla statik olarak bağlanır. | **`/MT`** | `_MT` |
| *`libvcruntimed.lib`* | Hiçbiri | Statik bağlama için hata ayıklama sürümü. Yeniden dağıtılabilir değil. | **`/MTd`** | `_MT`, `_DEBUG` |
| *`vcruntime.lib`* | *`vcruntime<version>.dll`* | Vcruntime için DLL içeri aktarma kitaplığı. | **`/MD`** | `_MT`, `_DLL` |
| *`vcruntimed.lib`* | *`vcruntime<version>d.dll`* | Hata ayıklama vcruntime için DLL içeri aktarma kitaplığı. Yeniden dağıtılabilir değil. | **`/MDd`** | `_DEBUG`, `_MT`, `_DLL` |

> [!NOTE]
> UCRT yeniden düzenlemesi gerçekleştiği zaman, Eşzamanlılık Çalışma Zamanı işlevleri *`concrt140.dll`* C++ yeniden dağıtılabilir paketine eklenmiş olan içine taşınır. Bu DLL, C++ paralel kapsayıcıları ve gibi algoritmalar için gereklidir `concurrency::parallel_for` . Buna ek olarak, Windows XP 'nin koşul değişkenleri olmadığından, C++ standart kitaplığı Windows XP 'de bu DLL 'nin eşitleme temel öğelerini desteklemesini gerektirir.

CRT 'yi başlatan kod, CRT kitaplığının statik veya dinamik olarak bağlı ya da yerel, yönetilen ya da karma kod olup olmadığına bağlı olarak birkaç kitaplıktan biridir. Bu kod CRT başlangıcını, iç iş parçacığı başına verileri başlatmayı ve sonlandırmayı işler. Kullanılan derleyicinin sürümüne özeldir. Bu kitaplık, dinamik olarak bağlı bir UCRT kullanılırken bile her zaman statik olarak bağlanır.

Bu tablo CRT başlatma ve sonlandırma uygulayan kitaplıkları listeler.

| Kitaplık | Özellikler | Seçenek | Ön işlemci yönergeleri |
|--|--|--|--|
| *`libcmt.lib`* | Yerel CRT başlangıcını kodunuza statik olarak bağlar. | **`/MT`** | `_MT` |
| *`libcmtd.lib`* | Yerel CRT başlatmanın hata ayıklama sürümüne statik olarak bağlanır. Yeniden dağıtılabilir değil. | **`/MTd`** | `_DEBUG`, `_MT` |
| *`msvcrt.lib`* | DLL UCRT ve vcruntime ile kullanılmak üzere yerel CRT başlatması için statik kitaplık. | **`/MD`** | `_MT`, `_DLL` |
| *`msvcrtd.lib`* | DLL UCRT ve vcruntime ile kullanılmak üzere yerel CRT başlatması hata ayıklama sürümü için statik kitaplık. Yeniden dağıtılabilir değil. | **`/MDd`** | `_DEBUG`, `_MT`, `_DLL` |
| *`msvcmrt.lib`* | DLL UCRT ve vcruntime ile kullanılmak üzere karışık yerel ve yönetilen CRT başlatması için statik kitaplık. | **`/clr`** |  |
| *`msvcmrtd.lib`* | DLL UCRT ve vcruntime ile kullanılmak üzere karma yerel ve yönetilen CRT başlatmasının hata ayıklama sürümü için statik kitaplık. Yeniden dağıtılabilir değil. | **`/clr`** |  |
| *`msvcurt.lib`* | **Kullanım dışı** Saf yönetilen CRT için statik kitaplık. | **`/clr:pure`** |  |
| *`msvcurtd.lib`* | **Kullanım dışı** Saf yönetilen CRT 'nin hata ayıklama sürümü için statik kitaplık. Yeniden dağıtılabilir değil. | **`/clr:pure`** |  |

Programınızı bir C çalışma zamanı kitaplığı belirten derleyici seçeneği olmadan komut satırından bağlarsanız, bağlayıcı statik olarak bağlı CRT kitaplıklarını kullanır: *`libcmt.lib`* , *`libvcruntime.lib`* ve *`libucrt.lib`* .

Statik olarak bağlı CRT 'nin kullanılması, C çalışma zamanı kitaplığı tarafından kaydedilen tüm durum bilgilerinin CRT 'nin bu örneğine yerelden olacağı anlamına gelir. Örneğin, [`strtok`](../c-runtime-library/reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) statik olarak bağlı BIR CRT kullanırken kullanıyorsanız, `strtok` ayrıştırıcısının konumu `strtok` aynı işlemdeki kodda kullanılan durumla (ancak farklı BIR DLL veya exe 'de), statik CRT 'ın başka bir örneğine bağlı değildir. Buna karşılık, dinamik olarak bağlı bir işlem içindeki tüm kodlar için, CRT 'ye dinamik olarak bağlanmış bir Bu işlevlerin yeni daha güvenli sürümlerini kullanıyorsanız, bu sorun uygulanmaz; Örneğin, `strtok_s` Bu sorun yoktur.

Statik bir CRT 'ye bağlanan bir DLL kendi CRT durumuna sahip olduğundan, bunun sonuçları özellikle istenip anlaşılmadığı takdirde, bir DLL içindeki CRT 'ye statik olarak bağlanmamalıdır. Örneğin, [`_set_se_translator`](../c-runtime-library/reference/set-se-translator.md) kendi STATIK CRT 'sine bağlı dll 'yi yükleyen bir yürütülebilir dosyayı çağırırsanız, dll 'deki kod tarafından oluşturulan tüm donanım özel durumları, çevirmen tarafından yakalanmaz, ancak ana yürütülebilir dosyada kod tarafından oluşturulan donanım özel durumları yakalanacaktır.

**`/clr`** Derleyici anahtarını kullanıyorsanız, kodunuz bir statik kitaplık olan msvcmrt. lib ile bağlantılandırılır. Statik kitaplık, yönetilen kodunuz ile yerel CRT arasında bir ara sunucu sağlar. Statik olarak bağlı CRT ( **`/MT`** veya **`/MTd`** seçenekleri) ile kullanamazsınız **`/clr`** . Bunun yerine, dinamik olarak bağlı kitaplıkları ( **`/MD`** veya **`/MDd`** ) kullanın. Saf yönetilen CRT kitaplıkları Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

CRT ile birlikte kullanma hakkında daha fazla bilgi için **`/clr`** bkz. [karma (yerel ve yönetilen) derlemeler](../dotnet/mixed-native-and-managed-assemblies.md).

Uygulamanızın hata ayıklama sürümünü oluşturmak için, [`_DEBUG`](../c-runtime-library/debug.md) bayrağın tanımlanması ve uygulamanın bu kitaplıkların birinin hata ayıklama sürümüyle bağlantılı olması gerekir. Kitaplık dosyalarının hata ayıklama sürümlerini kullanma hakkında daha fazla bilgi için bkz. [CRT hata ayıklama teknikleri](/visualstudio/debugger/crt-debugging-techniques).

CRT 'nin bu sürümü C99 standardına tamamen uyumlu değildir. Visual Studio 2019 sürüm 16,8 ' den önceki sürümlerde \<tgmath.h> üst bilgi desteklenmez. Tüm sürümlerde, `CX_LIMITED_RANGE` ve `FP_CONTRACT` pragma makroları desteklenmez. Standart GÇ işlevlerinde parametre Belirticilerinin anlamı gibi bazı öğeler, varsayılan olarak eski yorumlamalar kullanır. **`/Zc`** Derleyici uygunluk seçeneklerini kullanabilir ve kitaplık uygunluk özelliklerinin bazı yönlerini denetlemek için bağlayıcı seçeneklerini belirtebilirsiniz.

## <a name="c-standard-library"></a>C++ Standart Kitaplığı

| C++ Standart Kitaplığı | Özellikler | Seçenek | Ön işlemci yönergeleri |
|--|--|--|--|
| *`libcpmt.lib`* | Çok iş parçacıklı, statik bağlantı | **`/MT`** | `_MT` |
| *`msvcprt.lib`* | Çok iş parçacıklı, dinamik bağlantı (için kitaplık içeri aktarma *`msvcp<version>.dll`* ) | **`/MD`** | `_MT`, `_DLL` |
| *`libcpmtd.lib`* | Çok iş parçacıklı, statik bağlantı | **`/MTd`** | `_DEBUG`, `_MT` |
| *`msvcprtd.lib`* | Çok iş parçacıklı, dinamik bağlantı (için kitaplık içeri aktarma *`msvcp<version>d.dll`* ) | **`/MDd`** | `_DEBUG`, `_MT`, `_DLL` |

Projenizin bir yayın sürümünü derlediğinizde, *`libcmt.lib`* *`msvcmrt.lib`* *`msvcrt.lib`* seçtiğiniz derleyici seçeneğine (çok iş parçacıklı, dll,) bağlı olarak temel C çalışma zamanı kitaplıklarından (,,) biri varsayılan olarak bağlanır **`/clr`** . Kodunuzda [C++ standart kitaplık üst bilgi dosyalarından](../standard-library/cpp-standard-library-header-files.md) birini eklerseniz, bir C++ standart kitaplığı, derleme zamanında Visual C++ tarafından otomatik olarak bağlanır. Örneğin:

```cpp
#include <ios>
```

İkili uyumluluk için, tek bir içeri aktarma kitaplığıyla birden fazla DLL dosyası belirtilebilir. Sürüm güncelleştirmeleri, yeni kitaplık işlevselliği sağlayan ayrı dll 'Leri, *nokta kitaplıklarını*ortaya çıkarabilir. Örneğin, Visual Studio 2017 sürüm 15,6, *`msvcp140_1.dll`* tarafından desteklenen ABI 'yi bozmadan ek standart kitaplık işlevlerini desteklemeye sunuldu *`msvcp140.dll`* . *`msvcprt.lib`* Visual Studio 2017 sürüm 15,6 için araç takımı 'nda bulunan içeri aktarma kitaplığı her Iki dll 'yi de destekler ve bu sürümün VCRedist 'leri her Iki dll 'yi de yüklüyor. Sevk edildiğinde, bir nokta kitaplığı sabit bir ABı ve daha sonraki bir nokta kitaplığı üzerinde hiçbir bağımlılığı olmaz.

## <a name="what-problems-exist-if-an-application-uses-more-than-one-crt-version"></a>Bir uygulama birden fazla CRT sürümü kullanıyorsa hangi sorunları var?

Her yürütülebilir görüntünün (EXE veya DLL) kendi statik olarak bağlı CRT 'ı olabilir veya bir CRT 'ye dinamik olarak bağlanabilir. Belirli bir görüntü tarafından statik olarak dahil edilen veya dinamik olarak yüklenen CRT sürümü, yerleşik olarak oluşturulduğu araçların ve kitaplıkların sürümüne bağlıdır. Tek bir işlem, her biri kendi CRT ile birden fazla EXE ve DLL görüntüsü yükleyebilir. Bu antların her biri farklı bir ayırıcı kullanabilir, farklı iç yapı düzenlerine sahip olabilir ve farklı depolama düzenlemeleri kullanabilir. Bu, ayrılmış bellek, CRT kaynakları veya bir DLL sınırında geçirilen sınıfların bellek yönetimi, iç statik kullanım veya Düzen yorumu üzerinde sorunlara neden olabileceği anlamına gelir. Örneğin, bir sınıf bir DLL içinde ayrılmışsa, ancak başka bir tarafından silinmişse ve bu tarafından silinirse, hangi CRT deayırıcı kullanılır? Hataya neden olan hatalar, hafif ile hemen önemli arasında değişebilir ve bu nedenle bu kaynakların doğrudan aktarılmasına kesinlikle önerilmez.

Bunun yerine, kararlı ve sürümlenebilir olacak şekilde tasarlanan uygulama Ikili arabirimi (ABı) teknolojilerini kullanarak bu sorunlardan birçoğundan kaçınabilirsiniz. Bir değere göre bilgi iletmek veya yerel olarak ayırmak ve çağırana geri dönmek yerine arayan tarafından geçirilen bellek üzerinde çalışmak için DLL dışa aktarma arabirimlerinizi tasarlayın. Yapılandırılmış verileri yürütülebilir görüntüler arasında kopyalamak için sıralama tekniklerini kullanın. Kaynakları yerel olarak yalıtır ve yalnızca istemcilerde kullanıma sunabileceğiniz işleyiciler veya işlevler aracılığıyla düzenlemeye izin verin.

Bu sorunlardan bazılarının, işlemdeki tüm görüntülerin CRT 'ın aynı dinamik olarak yüklenmiş sürümünü kullanması durumunda da kaçınılmasını mümkün hale gelir. Tüm bileşenlerin CRT 'ın aynı DLL sürümünü kullandığından emin olmak için, seçeneğini kullanarak bunları derleyin **`/MD`** ve aynı derleyici araç takımını ve özellik ayarlarını kullanın.

Programınız belirli CRT kaynaklarını DLL sınırları genelinde geçirirse dikkatli olun. Dosya tanıtıcıları, yerel ayarlar ve ortam değişkenleri gibi kaynaklar, aynı CRT sürümü kullanılırken bile sorunlara neden olabilir. İlgili sorunlar ve bunları çözme hakkında daha fazla bilgi için, bkz. [CRT NESNELERINI DLL sınırları genelinde geçirme olası hataları](../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md).

## <a name="see-also"></a>Ayrıca bkz.

- [C Çalışma Zamanı Kitaplığı Başvurusu](../c-runtime-library/c-run-time-library-reference.md)
