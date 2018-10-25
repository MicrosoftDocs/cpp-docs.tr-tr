---
title: CRT kitaplık özellikleri | Microsoft Docs
ms.custom: ''
ms.date: 08/20/2018
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.runtime
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7562f6e5a8915f33b3f2c8bd23ce310e641984c6
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50057055"
---
# <a name="crt-library-features"></a>CRT Kitaplık Özellikleri

Bu konuda, C çalışma zamanı kitaplıklarının yanı sıra ilgili derleme seçeneklerini ve ön işlemci yönergeleri oluşturan çeşitli .lib dosyaları anlatılmaktadır.

## <a name="c-run-time-libraries-crt"></a>C Çalışma Zamanı Kitaplıkları (CRT)

C çalışma zamanı kitaplığı (CRT) ISO C99 standart Kitaplığı'na dahil C++ Standart Kitaplığı'nun bir parçasıdır. Yerel kod geliştirme CRT uygulamak için Visual C++ kitaplıklarını destekler ve hem de yerel ve yönetilen kod karma. Çok iş parçacıklı geliştirme CRT tüm sürümlerini destekler. Hem statik, doğrudan kodunuza, kitaplık bağlamak için bağlama veya, kod kullanmak yaygın DLL dosyaları izin vermek için dinamik bağlantı kitaplıkları çoğunu destekler.

Visual Studio 2015'ten başlayarak, CRT yeni ikili dosyalarınıza düzenlendi. İşlevler ve genel öğeleri standart C99 CRT kitaplığı tarafından dışarı aktarılan Evrensel CRT (UCRT) içerir. UCRT artık Windows bir bileşendir ve Windows 10 'un bir parçası olarak sunulur. Statik kitaplık, DLL içeri aktarma kitaplığını ve UCRT için üst bilgi dosyaları artık Windows 10 SDK'sı bulunamadı. Visual C++'ı yüklediğinizde, Visual Studio kurulumunu UCRT kullanmak için gerekli Windows 10 SDK'sının alt yükler. Visual Studio 2015 ve sonraki sürümleri tarafından desteklenen Windows sürümlerini UCRT kullanabilirsiniz. Windows 10 dışında Windows'ın desteklenen sürümleri için vcredist kullanarak dağıtabilirsiniz. Daha fazla bilgi için [Visual C++ dosyalarını yeniden dağıtma](../ide/redistributing-visual-cpp-files.md).

Aşağıdaki tabloda UCRT uygulayan kitaplıkları listeler.

|Kitaplığı|İlişkili DLL|Özellikler|Seçenek|Ön işlemci yönergeleri|
|-------------|--------------------|---------------------|------------|-----------------------------|
|libucrt.lib|Yok.|Statik olarak UCRT kodunuza bağlar.|**/MT**|_MT|
|libucrtd.lib|Yok.|Statik bağlama UCRT sürümünü hata ayıklayın. Değil yeniden dağıtılabilir.|**/MTd**|_DEBUG, _MT|
|ucrt.lib|ucrtbase.dll|DLL içeri aktarma kitaplığını UCRT için.|**/MD**|_MT, _DLL|
|ucrtd.lib|ucrtbased.dll dosyasını|DLL Kitaplığı UCRT hata ayıklama sürümünü içeri aktarın. Değil yeniden dağıtılabilir.|**/MDd**|_DEBUG, _MT, _DLL|

Visual C++ CRT uygulamaya özgü kod özel durum işleme ve hata ayıklama desteği, çalışma zamanı denetimleri ve tür bilgileri, uygulama ayrıntıları ve bazı genişletilmiş kitaplık işlevleri gibi vcruntime kitaplığı içerir. Bu kitaplık, kullanılan derleyici sürümüne özeldir.

Bu tabloda vcruntime kitaplığı uygulayan kitaplıkları listeler.

|Kitaplığı|İlişkili DLL|Özellikler|Seçenek|Ön işlemci yönergeleri|
|-------------|--------------------|---------------------|------------|-----------------------------|
|libvcruntime.lib|Yok.|Kodunuza statik olarak bağlı.|**/MT**|_MT|
|libvcruntimed.lib|Yok.|Statik bağlama sürüm hata ayıklayın. Değil yeniden dağıtılabilir.|**/MTd**|_MT, _DEBUG|
|vcruntime.lib|vcruntime\<sürüm > .dll|DLL içeri aktarma kitaplığını vcruntime için.|**/MD**|_MT, _DLL|
|vcruntimed.lib|vcruntime\<sürüm > d.dll|DLL içeri aktarma kitaplığı hata ayıklama vcruntime için. Değil yeniden dağıtılabilir.|**/MDd**|_DEBUG, _MT, _DLL|

> [!NOTE]
> Yeniden düzenleme UCRT oluştuğunda eşzamanlılık çalışma zamanı işlevleri C++ yeniden dağıtılabilir paketi eklenen concrt140.dll içine taşındı. C++ paralel kapsayıcılar ve algoritmalar gibi bu DLL gerekiyor `concurrency::parallel_for`. Ayrıca, Windows XP koşul değişkenleri olmadığından bu DLL eşitleme temellerine desteklemek için Windows XP C++ Standart kitaplığı gerektirir.

CRT başlatan bir CRT kitaplığının statik veya dinamik olarak bağlı, veya yerel, yönetilen veya karma kodu olduğuna göre birden çok kitaplık kodudur. Bu kod, CRT başlatma, iç iş parçacığı başına veri başlatma ve sonlandırma işler. Kullanılan derleyici sürümüne özeldir. Dinamik olarak bağlı UCRT kullanırken bile bu kitaplığı her zaman statik olarak bağlanır.

Bu tablo, CRT başlatma ve sonlandırma uygulayan kitaplıkları listeler.

|Kitaplığı|Özellikler|Seçenek|Ön işlemci yönergeleri|
|-------------|---------------------|------------|-----------------------------|
|LIBCMT.lib|Statik olarak yerel CRT başlatma kodunuza bağlar.|**/MT**|_MT|
|libcmtd.lib|Hata ayıklama sürümü yerel CRT başlatma, statik olarak bağlar. Değil yeniden dağıtılabilir.|**/MTd**|_DEBUG, _MT|
|msvcrt.lib|Yerel CRT başlatma DLL UCRT ve vcruntime ile kullanılmak için statik kitaplığı.|**/MD**|_MT, _DLL|
|msvcrtd.lib|Hata ayıklama sürümü, yerel CRT başlatma DLL UCRT ve vcruntime ile kullanılmak için statik kitaplığı. Değil yeniden dağıtılabilir.|**/MDd**|_DEBUG, _MT, _DLL|
|msvcmrt.lib|Karma yerel ve yönetilen CRT başlatma DLL UCRT ve vcruntime ile kullanılmak için statik kitaplığı.|**/ CLR**||
|msvcmrtd.lib|Hata ayıklama sürümü, karma yerel ve yönetilen CRT başlatma DLL UCRT ve vcruntime ile kullanılmak için statik kitaplığı. Değil yeniden dağıtılabilir.|**/ CLR**||
|msvcurt.lib|**Kullanım dışı** yönetilen CRT saf için statik kitaplığı.|**/clr:pure**||
|msvcurtd.lib|**Kullanım dışı** yönetilen CRT hata ayıklama sürümü saf için statik kitaplığı. Değil yeniden dağıtılabilir.|**/clr:pure**||

Programınızın C çalışma zamanı kitaplığı belirten bir derleyici seçeneği olmadan komut satırından, statik olarak bağlı CRT kitaplığı bağlayıcı kullanacak: LIBCMT.lib libvcruntime.lib ve libucrt.lib.

Statik olarak bağlı CRT kullanarak C çalışma zamanı kitaplığı tarafından kaydedilen herhangi bir durum bilgisini CRT örneğini için yerel olacağı anlamına gelir. Örneğin kullanırsanız, [strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l](../c-runtime-library/reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) konumu statik olarak bağlı bir CRT kullanırken `strtok` ayrıştırıcı ilgisi olmayan `strtok` kod aynı işlemde kullanılan durumu (ancak farklı bir DLL veya EXE) statik CRT başka bir örneğine bağlı. Buna karşılık, dinamik olarak bağlı CRT CRT'ye dinamik olarak bağlı bir işlem içinde tüm kodlar için durum paylaşır. Bu işlevlerin daha güvenli sürümleri yeni kullanıyorsanız, bu sorun geçerli değildir; Örneğin, `strtok_s` Bu sorun mevcut değildir.

Bir DLL için statik bir CRT bağlayarak oluşturulan kendi CRT durumuna sahip olacağından statik olarak sonuçları, bu özellikle istenen ve anlaşılan bir DLL'de CRT bağlamak için önerilmez. Örneğin, eğer [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) kendi statik CRT'ye bağlı bir DLL'yi yükler bir yürütülebilir dosya içinde DLL içindeki kod tarafından oluşturulan herhangi bir donanım özel durumları translator ancak donanım özel durumları tarafından yakalanır değil ana kod tarafından oluşturulan yürütülebilir dosya yakalandı.

Kullanıyorsanız **/CLR** derleyici anahtarı, kodunuzu bağlı olmaları ile bir statik kitaplık, msvcmrt.lib. Statik kitaplık, yönetilen kod ile yerel CRT arasında bir proxy sağlar. Statik olarak bağlı CRT kullanamazsınız ( **/MT** veya **/mtd** seçenekleri) ile **/CLR**. Dinamik olarak bağlanan kitaplıkların kullanın (**/MD** veya **/MDd**) bunun yerine. Saf yönetilen CRT Kitaplığı Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

CRT ile kullanma hakkında daha fazla bilgi için **/CLR**, bkz: [karışık (yerel ve yönetilen) derlemeler](../dotnet/mixed-native-and-managed-assemblies.md).

Uygulamanızı hata ayıklama sürümünü oluşturmak için [_DEBUG](../c-runtime-library/debug.md) bayrağı tanımlanmalıdır ve uygulamayı Bu kitaplıklar birinin hata ayıklama sürümü ile bağlanması gerekir. Kitaplık dosyaları hata ayıklama sürümlerini kullanma hakkında daha fazla bilgi için bkz. [CRT hata ayıklama teknikleri](/visualstudio/debugger/crt-debugging-techniques).

CRT bu sürümü, tam olarak C99 standardı ile uyumlu değil. Özellikle, \<tgmath.h > üst bilgi ve CX_LIMITED_RANGE/FP_CONTRACT pragması makroları desteklenmez. Standart GÇ işlevlerde parametre belirticileri anlamını gibi belirli öğeleri varsayılan olarak eski ınterpretations kullanın. /Zc derleyici uyumluluğu seçenekleri kullanın ve kitaplık uygunluk bazı yönleri denetlemek için bağlayıcı seçenekleri belirtin,

## <a name="c-standard-library"></a>C++ Standart Kitaplığı

|C++ Standart Kitaplığı|Özellikler|Seçenek|Ön işlemci yönergeleri|
|----------------------------|---------------------|------------|-----------------------------|
|libcpmt.lib|Çok iş parçacıklı ve statik bağlantı|**/MT**|_MT|
|msvcprt.lib|Çok iş parçacıklı ve dinamik bağlantı (kitaplığı içeri aktarmak için MSVCP*sürüm*.dll)|**/MD**|_MT, _DLL|
|libcpmtd.lib|Çok iş parçacıklı ve statik bağlantı|**/MTd**|_DEBUG, _MT|
|msvcprtd.lib|Çok iş parçacıklı ve dinamik bağlantı (kitaplığı içeri aktarmak için MSVCP*sürüm*D.DLL)|**/MDd**|_DEBUG, _MT, _DLL|

Projenizin bir yayım sürümünü derlediğinizde temel C çalışma zamanı kitaplıkları (LIBCMT.lib, msvcmrt.lib, msvcrt.lib) biri bağlantılı varsayılan olarak, seçtiğiniz bağlı olarak derleyici seçeneği (çok iş parçacıklı, DLL, / CLR). Aşağıdakilerden birini eklerseniz [C++ Standart Kitaplığı üst bilgi dosyaları](../standard-library/cpp-standard-library-header-files.md) kodunuza, bir C++ Standart Kitaplığı içinde otomatik olarak Visual C++ tarafından derleme zamanında bağlanır. Örneğin:

```cpp
#include <ios>
```

İkili uyumluluğu sağlamak için birden fazla DLL dosyasının tek içeri aktarma kitaplığı tarafından belirtilebilir. Sürüm güncelleştirmelerini yol açabilir *nokta kitaplıkları*, yeni kitaplık işlevleri tanıtmak DLL'leri ayırın. Örneğin, Visual Studio 2017 sürüm 15.6 sunulan msvcp140_1.dll msvcp140.dll tarafından desteklenen ABI bozmadan ek standart kitaplık işlevleri desteklemek için. Her iki DLL'ler için Visual Studio 2017 sürüm 15.6 takımında yer msvcprt.lib içeri aktarma kitaplığı destekler ve hem DLL'leri vcredist bu sürümü için yükler. Sevk sonra bir nokta kitaplığı sabit ABI vardır ve bir sonraki nokta Kitaplığı'nda bir bağımlılık hiçbir zaman sahip olur.

## <a name="what-problems-exist-if-an-application-uses-more-than-one-crt-version"></a>Bir uygulamanın birden fazla CRT sürümü kullanıyorsa, hangi sorunları var?

Her bir yürütülebilir görüntü (EXE veya DLL), kendi statik olarak bağlı CRT olabilir veya bir CRT için dinamik olarak bağlayabilirsiniz. CRT dahil statik veya dinamik olarak belirli bir görüntü tarafından yüklenen sürümü ile oluşturulmuş kitaplıkları ve araçları sürümü bağlıdır. Tek bir işlem birden fazla EXE ve DLL görüntüleri, her biri kendi CRT yükleyebilir. Her büyüklükteki bu CRT'lerden farklı bir ayırıcı kullanabilir, farklı iç yapısı düzenlere sahip ve farklı depolama düzenlemeleri kullanabilir. Bellek, CRT kaynaklar veya sınıfların bir DLL sınırında geçirilen ayrılan anlamına gelir, bellek yönetimi, dahili statik kullanım veya Düzen yorumu sorunlara neden olabilir. Örneğin, bir sınıf bir DLL içinde ayrılmış, ancak geçirilen ve bir başkası tarafından silindi, hangi CRT birleştiricinin kullanılır? Neden olduğu hata Zarif hemen önemli aralığı ve bu nedenle böyle kaynaklar aktarımını kesinlikle önerilmez doğrudan.

Bu sorunların çoğu, kararlı ve sürümlenebilir olacak şekilde tasarlandığı gibi uygulama ikili arabirimi (ABI) teknolojilerini bunun yerine, kullanarak önleyebilirsiniz. Değere göre bilgi geçirmek veya çağıran tarafından geçirilen yerine yerel olarak tahsis ve çağırana döndürülen bellek üzerinde çalışmak için DLL dışarı aktarma arabirimleri tasarlayın. Yürütülebilir görüntüler arasında yapılandırılmış veri kopyalamak için sıralama tekniklerini kullanın. Yerel kaynakları kapsamak ve yalnızca işleme tutamaçlarını veya istemcilere göstermek işlevleri aracılığıyla izin verin.

Tüm görüntüleri işleminizin CRT aynı dinamik olarak yüklenen sürümünü kullanıyorsanız bu sorunlardan kaçınmak mümkündür. Tüm bileşenlerin aynı CRT DLL sürümünü kullandığınızdan emin olmak için bunları kullanarak yapı **/MD** seçenek ve aynı derleyici araç takımı ve özellik ayarlarını kullanın.

Bazı CRT kaynakları (örneğin, dosya tanıtıcıları, yerel ve ortam değişkenlerini) DLL sınırlarından CRT aynı sürümünü kullanırken bile, programınızın başarılı olursa, bazı bakım gereklidir. İlgili sorunlar hakkında daha fazla bilgi ve bunların nasıl çözüleceğine bakın [olası hataları geçirme CRT nesnelerini DLL sınırlar boyunca](../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md).

## <a name="see-also"></a>Ayrıca bkz.

- [C Çalışma Zamanı Kitaplığı Başvurusu](../c-runtime-library/c-run-time-library-reference.md)
