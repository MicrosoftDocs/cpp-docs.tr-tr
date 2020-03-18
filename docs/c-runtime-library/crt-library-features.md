---
title: CRT Kitaplık Özellikleri
ms.date: 08/20/2018
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
ms.openlocfilehash: a350e2c45d9ccf83fb09a76f43b63a6b17273cff
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438541"
---
# <a name="crt-library-features"></a>CRT Kitaplık Özellikleri

Bu konuda, C çalışma zamanı kitaplıklarını ve bunlarla ilişkili derleyici seçeneklerini ve önişlemci yönergelerini oluşturan çeşitli. lib dosyaları ele alınmaktadır.

## <a name="c-run-time-libraries-crt"></a>C Çalışma Zamanı Kitaplıkları (CRT)

C çalışma zamanı kitaplığı (CRT), C++ standart kitaplığın ISO C99 standart kitaplığı 'nı içeren bölümüdür. CRT uygulayan C++ görsel kitaplıklar yerel kod geliştirmeyi ve hem karma yerel hem de yönetilen kodu destekler. CRT 'nin tüm sürümleri çoklu iş parçacıklı geliştirmeyi destekler. Kitaplıkların çoğu hem statik bağlamayı, hem de kodunuzun ortak DLL dosyalarını kullanmasına izin vermek için dinamik bağlamayı destekler.

Visual Studio 2015 ' den başlayarak, CRT yeni ikililer yeniden düzenlenmiş. Universal CRT (UCRT), standart C99 CRT kitaplığı tarafından dışarıya aktarılmış işlevleri ve genel değerleri içerir. UıCRT artık bir Windows bileşenidir ve Windows 10 ' un bir parçası olarak gelir. UıCRT için statik kitaplık, DLL içeri aktarma kitaplığı ve üst bilgi dosyaları artık Windows 10 SDK 'da bulunur. Visual Studio Kurulumu, C++Visual 'yı yüklerken UCRT kullanmak Için gereken WINDOWS 10 SDK alt kümesini yükler. UCRT 'yi, Visual Studio 2015 ve sonraki sürümleri tarafından desteklenen herhangi bir Windows sürümünde kullanabilirsiniz. Windows 10 dışındaki desteklenen Windows sürümleri için VCRedist kullanarak yeniden dağıtabilirsiniz. Daha fazla bilgi için bkz. [görsel C++ dosyaları yeniden dağıtma](../windows/redistributing-visual-cpp-files.md).

Aşağıdaki tablo UCRT uygulayan kitaplıkları listeler.

|Kitaplık|İlişkili DLL|Özellikler|Seçenek|Ön işlemci yönergeleri|
|-------------|--------------------|---------------------|------------|-----------------------------|
|libucrt. lib|Yok|UCRT 'yi kodunuza statik olarak bağlar.|**/MT**|_MT|
|libucrtd. lib|Yok|Statik bağlama için UCRT 'nin hata ayıklama sürümü. Yeniden dağıtılabilir değil.|**/MTd**|_DEBUG, _MT|
|UCRT. lib|uıcrtbase. dll|UıCRT için DLL içeri aktarma kitaplığı.|**/MD**|_MT, _DLL|
|ucrtd. lib|uıcrtbased. dll|UıCRT 'nin hata ayıklama sürümü için DLL içeri aktarma kitaplığı. Yeniden dağıtılabilir değil.|**/MDd**|_DEBUG, _MT, _DLL|

Vcruntime kitaplığı, özel durum C++ işleme ve hata ayıklama desteği, çalışma zamanı denetimleri ve tür bilgileri, uygulama ayrıntıları ve belirli genişletilmiş kitaplık Işlevleri gibi Visual CRT uygulamaya özgü kod içerir. Bu kitaplık, kullanılan derleyicinin sürümüne özgüdür.

Bu tablo vcruntime kitaplığını uygulayan kitaplıkları listeler.

|Kitaplık|İlişkili DLL|Özellikler|Seçenek|Ön işlemci yönergeleri|
|-------------|--------------------|---------------------|------------|-----------------------------|
|libvcruntime. lib|Yok|Kodunuzla statik olarak bağlanır.|**/MT**|_MT|
|libvcruntimed.lib|Yok|Statik bağlama için hata ayıklama sürümü. Yeniden dağıtılabilir değil.|**/MTd**|_MT, _DEBUG|
|vcruntime. lib|vcruntime\<sürümü >. dll|Vcruntime için DLL içeri aktarma kitaplığı.|**/MD**|_MT, _DLL|
|vcruntimed.lib|vcruntime\<sürüm > d. dll|Hata ayıklama vcruntime için DLL içeri aktarma kitaplığı. Yeniden dağıtılabilir değil.|**/MDd**|_DEBUG, _MT, _DLL|

> [!NOTE]
> UCRT C++ yeniden düzenlemesi gerçekleştiği zaman, eşzamanlılık çalışma zamanı işlevleri yeniden dağıtılabilir pakete eklenen concrt140. dll ' ye taşınmıştır. Bu DLL, `concurrency::parallel_for`gibi C++ paralel kapsayıcılar ve algoritmalar için gereklidir. Buna ek olarak, C++ Windows XP 'nin koşul değişkenleri olmadığından, standart KITAPLıK Windows XP 'de bu DLL 'nin eşitleme temel öğelerini desteklemesini gerektirir.

CRT 'yi başlatan kod, CRT kitaplığının statik veya dinamik olarak bağlı ya da yerel, yönetilen ya da karma kod olup olmadığına bağlı olarak birkaç kitaplıktan biridir. Bu kod CRT başlangıcını, iç iş parçacığı başına verileri başlatmayı ve sonlandırmayı işler. Kullanılan derleyicinin sürümüne özeldir. Bu kitaplık, dinamik olarak bağlı bir UCRT kullanılırken bile her zaman statik olarak bağlanır.

Bu tablo CRT başlatma ve sonlandırma uygulayan kitaplıkları listeler.

|Kitaplık|Özellikler|Seçenek|Ön işlemci yönergeleri|
|-------------|---------------------|------------|-----------------------------|
|Libcmt. lib|Yerel CRT başlangıcını kodunuza statik olarak bağlar.|**/MT**|_MT|
|libcmtd.lib|Yerel CRT başlatmanın hata ayıklama sürümüne statik olarak bağlanır. Yeniden dağıtılabilir değil.|**/MTd**|_DEBUG, _MT|
|msvcrt.lib|DLL UCRT ve vcruntime ile kullanılmak üzere yerel CRT başlatması için statik kitaplık.|**/MD**|_MT, _DLL|
|msvcrtd.lib|DLL UCRT ve vcruntime ile kullanılmak üzere yerel CRT başlatması hata ayıklama sürümü için statik kitaplık. Yeniden dağıtılabilir değil.|**/MDd**|_DEBUG, _MT, _DLL|
|msvcmrt.lib|DLL UCRT ve vcruntime ile kullanılmak üzere karışık yerel ve yönetilen CRT başlatması için statik kitaplık.|**clr**||
|msvcmrtd.lib|DLL UCRT ve vcruntime ile kullanılmak üzere karma yerel ve yönetilen CRT başlatmasının hata ayıklama sürümü için statik kitaplık. Yeniden dağıtılabilir değil.|**clr**||
|msvcurt.lib|**Kullanım dışı** Saf yönetilen CRT için statik kitaplık.|**/clr: Pure**||
|msvcurtd.lib|**Kullanım dışı** Saf yönetilen CRT 'nin hata ayıklama sürümü için statik kitaplık. Yeniden dağıtılabilir değil.|**/clr: Pure**||

Programınızı bir C çalışma zamanı kitaplığı belirten bir derleyici seçeneği olmadan komut satırından bağlarsanız, bağlayıcı statik olarak bağlı CRT kitaplıklarını kullanır: Libcmt. lib, libvcruntime. lib ve libucrt. lib.

Statik olarak bağlı CRT 'nin kullanılması, C çalışma zamanı kitaplığı tarafından kaydedilen tüm durum bilgilerinin CRT 'nin bu örneğine yerelden olacağı anlamına gelir. Örneğin, bir statik olarak bağlı CRT kullanırken [strtok, _strtok_l, wcstok, _wcstok_l, _mbstok _mbstok_l](../c-runtime-library/reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) kullanırsanız, `strtok` ayrıştırıcısının konumu aynı işlemde (ancak farklı bir dll veya exe içinde), statik CRT 'ın başka bir örneğine bağlı olan kodda kullanılan `strtok` durumuyla ilgisiz değildir. Buna karşılık, dinamik olarak bağlı bir işlem içindeki tüm kodlar için, CRT 'ye dinamik olarak bağlanmış bir Bu işlevlerin yeni daha güvenli sürümlerini kullanıyorsanız, bu sorun uygulanmaz; Örneğin, `strtok_s` Bu soruna sahip değildir.

Statik bir CRT 'ye bağlanan bir DLL kendi CRT durumuna sahip olduğundan, bunun sonuçları özellikle istenip anlaşılmadığı takdirde, bir DLL içindeki CRT 'ye statik olarak bağlanmamalıdır. Örneğin, kendi statik CRT 'sine bağlı DLL 'yi yükleyen bir çalıştırılabilirde [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) ÇAĞıRıRSANıZ, dll 'deki kod tarafından oluşturulan tüm donanım özel durumları, çevirmen tarafından yakalanmaz, ancak ana yürütülebilir dosyada kod tarafından oluşturulan donanım özel durumları yakalanacaktır.

**/Clr** derleyici anahtarını kullanıyorsanız, kodunuz bir statik kitaplık olan msvcmrt. lib ile bağlantılandırılır. Statik kitaplık, yönetilen kodunuz ile yerel CRT arasında bir ara sunucu sağlar. Statik olarak bağlı CRT ( **/MT** veya **/MTD** seçenekleri) **/clr**ile kullanamazsınız. Bunun yerine, dinamik olarak bağlı kitaplıkları ( **/md** veya **/MDD**) kullanın. Saf yönetilen CRT kitaplıkları Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

CRT ile CRT kullanma hakkında daha fazla bilgi **için bkz**. [karma (yerel ve yönetilen) derlemeler](../dotnet/mixed-native-and-managed-assemblies.md).

Uygulamanızın hata ayıklama sürümünü oluşturmak için [_DEBUG](../c-runtime-library/debug.md) bayrağı tanımlanmalıdır ve uygulamanın bu kitaplıklarınızdan birinin hata ayıklama sürümüyle bağlantılı olması gerekir. Kitaplık dosyalarının hata ayıklama sürümlerini kullanma hakkında daha fazla bilgi için bkz. [CRT hata ayıklama teknikleri](/visualstudio/debugger/crt-debugging-techniques).

CRT 'nin bu sürümü C99 standardına tamamen uyumlu değildir. Özellikle, \<tgmath. h > üst bilgisi ve CX_LIMITED_RANGE/FP_CONTRACT pragma makroları desteklenmez. Standart GÇ işlevlerinde parametre Belirticilerinin anlamı gibi bazı öğeler, varsayılan olarak eski yorumlamalar kullanır. /ZC derleyici uygunluk seçeneklerini kullanabilir ve kitaplık uygunluk özelliklerinin bazı yönlerini denetlemek için bağlayıcı seçeneklerini belirtebilirsiniz.

## <a name="c-standard-library"></a>C++ Standart Kitaplığı

|C++ Standart Kitaplığı|Özellikler|Seçenek|Ön işlemci yönergeleri|
|----------------------------|---------------------|------------|-----------------------------|
|libcpmt.lib|Çok iş parçacıklı, statik bağlantı|**/MT**|_MT|
|msvcprt.lib|Çok iş parçacıklı, dinamik bağlantı (MSVCP*Sürüm*. dll için içeri aktarma kitaplığı)|**/MD**|_MT, _DLL|
|libcpmtd.lib|Çok iş parçacıklı, statik bağlantı|**/MTd**|_DEBUG, _MT|
|msvcprtd.lib|Çok iş parçacıklı, dinamik bağlantı (MSVCP*Sürüm*D. dll için içeri aktarma kitaplığı)|**/MDd**|_DEBUG, _MT, _DLL|

Projenizin bir yayın sürümünü oluşturduğunuzda, temel C çalışma zamanı kitaplıklarından (Libcmt. lib, msvcmrt. lib, Msvcrt. lib) biri, seçtiğiniz derleyici seçeneğine (çok iş parçacıklı, DLL,/CLR) bağlı olarak varsayılan olarak bağlanır. Kodunuzda [ C++ standart kitaplık üst bilgi dosyalarından](../standard-library/cpp-standard-library-header-files.md) birini eklerseniz, standart bir C++ kitaplık derleme zamanında görsel C++ tarafından otomatik olarak bağlanır. Örnek:

```cpp
#include <ios>
```

İkili uyumluluk için, tek bir içeri aktarma kitaplığıyla birden fazla DLL dosyası belirtilebilir. Sürüm güncelleştirmeleri, yeni kitaplık işlevselliği sağlayan ayrı dll 'Leri, *nokta kitaplıklarını*ortaya çıkarabilir. Örneğin, Visual Studio 2017 sürüm 15,6, msvcp140. dll tarafından desteklenen ABı 'yi bozmadan ek standart kitaplık işlevlerini desteklemek için msvcp140_1. dll ' yi sunmuştur. Visual Studio 2017 sürüm 15,6 için araç seti 'ne dahil olan MSVCPRT. lib içeri aktarma kitaplığı her iki DLL 'i de destekler ve bu sürüm için VCRedist her iki DLL 'yi de yüklüyor. Sevk edildiğinde, bir nokta kitaplığı sabit bir ABı ve daha sonraki bir nokta kitaplığı üzerinde hiçbir bağımlılığı olmaz.

## <a name="what-problems-exist-if-an-application-uses-more-than-one-crt-version"></a>Bir uygulama birden fazla CRT sürümü kullanıyorsa hangi sorunları var?

Her yürütülebilir görüntünün (EXE veya DLL) kendi statik olarak bağlı CRT 'ı olabilir veya bir CRT 'ye dinamik olarak bağlanabilir. Belirli bir görüntü tarafından statik olarak dahil edilen veya dinamik olarak yüklenen CRT sürümü, yerleşik olarak oluşturulduğu araçların ve kitaplıkların sürümüne bağlıdır. Tek bir işlem, her biri kendi CRT ile birden fazla EXE ve DLL görüntüsü yükleyebilir. Bu antların her biri farklı bir ayırıcı kullanabilir, farklı iç yapı düzenlerine sahip olabilir ve farklı depolama düzenlemeleri kullanabilir. Bu, ayrılmış bellek, CRT kaynakları veya bir DLL sınırında geçirilen sınıfların bellek yönetimi, iç statik kullanım veya Düzen yorumu üzerinde sorunlara neden olabileceği anlamına gelir. Örneğin, bir sınıf bir DLL içinde ayrılmışsa, ancak başka bir tarafından silinmişse ve bu tarafından silinirse, hangi CRT deayırıcı kullanılır? Hataya neden olan hatalar, hafif ile hemen önemli arasında değişebilir ve bu nedenle bu kaynakların doğrudan aktarılmasına kesinlikle önerilmez.

Bunun yerine, kararlı ve sürümlenebilir olacak şekilde tasarlanan uygulama Ikili arabirimi (ABı) teknolojilerini kullanarak bu sorunlardan birçoğundan kaçınabilirsiniz. Bir değere göre bilgi iletmek veya yerel olarak ayırmak ve çağırana geri dönmek yerine arayan tarafından geçirilen bellek üzerinde çalışmak için DLL dışa aktarma arabirimlerinizi tasarlayın. Yapılandırılmış verileri yürütülebilir görüntüler arasında kopyalamak için sıralama tekniklerini kullanın. Kaynakları yerel olarak yalıtır ve yalnızca istemcilerde kullanıma sunabileceğiniz işleyiciler veya işlevler aracılığıyla düzenlemeye izin verin.

Bu sorunlardan bazılarının, işlemdeki tüm görüntülerin CRT 'ın aynı dinamik olarak yüklenmiş sürümünü kullanması durumunda da kaçınılmasını mümkün hale gelir. Tüm bileşenlerin CRT 'ın aynı DLL sürümünü kullandığından emin olmak için, **/md** seçeneğini kullanarak bunları derleyin ve aynı derleyici araç takımını ve özellik ayarlarını kullanın.

Programınız, CRT 'nin aynı sürümünü kullanırken bile belirli CRT kaynaklarını (Dosya tutamaçları, yerel ayarlar ve ortam değişkenleri gibi) DLL sınırları genelinde geçirirse, bazı durumlarda gereklidir. İlgili sorunlar ve bunları çözme hakkında daha fazla bilgi için, bkz. [CRT NESNELERINI DLL sınırları genelinde geçirme olası hataları](../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md).

## <a name="see-also"></a>Ayrıca bkz.

- [C Çalışma Zamanı Kitaplığı Başvurusu](../c-runtime-library/c-run-time-library-reference.md)
