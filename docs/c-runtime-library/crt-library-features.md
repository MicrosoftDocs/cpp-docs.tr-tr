---
title: "CRT kitaplık özellikleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.runtime
dev_langs: C++
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
caps.latest.revision: "32"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 50ca3fd6d60e7fecf84c81d14c859f5b2f51e120
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="crt-library-features"></a>CRT Kitaplık Özellikleri
Bu konuda C çalışma zamanı kitaplıkları yanı sıra bunların ilişkili derleyici seçenekleri ve önişlemci yönergeleri oluşturan çeşitli .lib dosyaları anlatılmaktadır.  
  
## <a name="c-run-time-libraries-crt"></a>C Çalışma Zamanı Kitaplıkları (CRT)  
 C çalışma zamanı kitaplığı (CRT), ISO C99 standart kitaplığı içerir C++ Standart Kitaplığı, parçasıdır. CRT uygulayan Visual C++ kitaplıkları yerel kod geliştirme ve hem karışık yerel ve yönetilen kod ve saf yönetilen kod için .NET geliştirme desteği. Çok iş parçacıklı geliştirme CRT'in tüm sürümleri destekler. Hem statik, doğrudan kodunuza, kitaplık bağlamak için bağlama veya kod kullanımı ortak DLL dosyalarınızı izin vermek için dinamik bağlantılandırma kitaplıkları çoğunu destekler.  
  
 Visual Studio 2015'ten başlayarak, CRT yeni ikili dosyalar içinde bulunanad. Evrensel CRT (UCRT) tarafından standart C99 CRT kitaplık dışarı globals ve işlevler içerir. UCRT artık Windows bir bileşenidir ve Windows 10 bir parçası olarak gelir. Statik kitaplık, DLL içeri aktarma kitaplığı ve başlık dosyaları UCRT için artık Windows 10 SDK bulunamadı. Visual C++ yüklediğinizde Visual Studio Kurulumu Windows 10 SDK UCRT kullanmak için gereken alt yükler. Visual Studio 2015 ve sonraki sürümleri tarafından desteklenen Windows sürümlerini UCRT kullanabilirsiniz. Windows 10 dışında Windows'un desteklenen sürümleri için vcredist kullanarak dağıtabilirsiniz. Daha fazla bilgi için bkz: [Visual C++ dosyalarını yeniden dağıtma](../ide/redistributing-visual-cpp-files.md).  
  
 Aşağıdaki tabloda UCRT uygulamak kitaplıkları listeler.  
  
|Kitaplığı|İlişkili DLL|Özellikler|Seçenek|Ön işlemci yönergeleri|  
|-------------|--------------------|---------------------|------------|-----------------------------|  
|libucrt.lib|Yok.|Statik olarak UCRT kodunuza bağlar.|**/ MT**|_MT|  
|libucrtd.lib|Yok.|Statik bağlama için UCRT sürümü hata ayıklama. Değil yeniden dağıtılabilir.|**/ MTd**|_DEBUG, _MT|  
|ucrt.lib|ucrtbase.dll|DLL içeri aktarma kitaplığını UCRT için.|**/MD**|_MT, _DLL|  
|ucrtd.lib|ekler|DLL UCRT hata ayıklama sürümü için kitaplığı içeri aktarın. Değil yeniden dağıtılabilir.|**/ MDd**|_DEBUG, _MT, _DLL|  
  
 Vcruntime kitaplığı özel durum işleme ve hata ayıklama desteği, çalışma zamanı denetimleri ve tür bilgileri, uygulama ayrıntılarını ve bazı genişletilmiş kitaplık işlevleri gibi Visual C++ CRT uygulamaya özel kod içerir. Bu kitaplık kullanılan derleyici sürümüne özeldir.  
  
 Bu tablo vcruntime kitaplığı uygulamak kitaplıkları listeler.  
  
|Kitaplığı|İlişkili DLL|Özellikler|Seçenek|Ön işlemci yönergeleri|  
|-------------|--------------------|---------------------|------------|-----------------------------|  
|libvcruntime.lib|Yok.|Statik olarak kodunuza bağlı.|**/ MT**|_MT|  
|libvcruntimed.lib|Yok.|Statik bağlama için sürüm hata ayıklama. Değil yeniden dağıtılabilir.|**/ MTd**|_MT, _DEBUG|  
|vcruntime.lib|vcruntime\<sürüm > .dll|DLL içeri aktarma kitaplığını vcruntime için.|**/MD**|_MT, _DLL|  
|vcruntimed.lib|vcruntime\<sürüm > d.dll|Hata ayıklama vcruntime için DLL içeri aktarma kitaplığı. Değil yeniden dağıtılabilir.|**/ MDd**|_DEBUG, _MT, _DLL|  
  
 CRT başlatır CRT kitaplık statik veya dinamik olarak bağlı, veya yerel, yönetilen veya karma kodu olduğuna bağlı birden çok kitaplık birinde koddur. Bu kod CRT başlatma, iç iş parçacığı başına veri başlatma ve sonlandırma işler. Kullanılan derleyici sürümüne özeldir. Dinamik olarak bağlı UCRT kullanırken bile bu kitaplığı her zaman statik olarak bağlanır.  
  
 Bu tablo CRT başlatma ve sonlandırma uygulamak kitaplıkları listeler.  
  
|Kitaplığı|Özellikler|Seçenek|Ön işlemci yönergeleri|  
|-------------|---------------------|------------|-----------------------------|  
|Libcmt.lib|Statik olarak yerel CRT başlatma kodunuza bağlar.|**/ MT**|_MT|  
|libcmtd.lib|Statik olarak yerel CRT başlatma hata ayıklama sürümü bağlar. Değil yeniden dağıtılabilir.|**/ MTd**|_DEBUG, _MT|  
|Msvcrt.lib|DLL UCRT ve vcruntime ile kullanım için yerel CRT başlatma için statik kitaplığı.|**/MD**|_MT, _DLL|  
|msvcrtd.lib|Statik kitaplık yerel CRT başlatma DLL UCRT ve vcruntime ile kullanmak için hata ayıklama sürümü. Değil yeniden dağıtılabilir.|**/ MDd**|_DEBUG, _MT, _DLL|  
|msvcmrt.lib|DLL UCRT ve vcruntime ile kullanmak için karışık yerel ve yönetilen CRT başlatma için statik kitaplığı.|**/ CLR**||  
|msvcmrtd.lib|Statik kitaplık karışık yerel ve yönetilen CRT başlatma DLL UCRT ve vcruntime ile kullanmak için hata ayıklama sürümü. Değil yeniden dağıtılabilir.|**/ CLR**||  
|Msvcurt.lib|**Kullanım dışı** saf için statik kitaplık yönetilen CRT.|**/ CLR: pure**||  
|msvcurtd.lib|**Kullanım dışı** saf hata ayıklama sürümü için statik kitaplık yönetilen CRT. Değil yeniden dağıtılabilir.|**/ CLR: pure**||  
  
 Komut satırında C çalışma zamanı kitaplığı belirtir derleyici seçeneği olmadan programınızdan bağlantı varsa, bağlayıcı statik olarak bağlantılı CRT kitaplıklar kullanır: libcmt.lib, libvcruntime.lib ve libucrt.lib.  
  
 Statik olarak bağlantılı CRT kullanarak C çalışma zamanı kitaplığı tarafından kaydedilen herhangi bir durum bilgisini CRT için bu örneği yerel olacağı anlamına gelir. Kullanırsanız, örneğin, [strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l](../c-runtime-library/reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) konumunu statik olarak bağlantılı bir CRT kullanırken `strtok` ayrıştırıcı ilgisi olmayan `strtok` aynı işlemde kod içinde kullanılan durumu (ancak farklı DLL veya EXE) statik CRT başka bir örneğine bağlanır. Buna karşılık, dinamik olarak bağlı CRT CRT dinamik olarak bağlı bir işlemdeki tüm kod durumu paylaşır. Bu işlevler yeni daha güvenli sürümlerini kullanırsanız bu sorun geçerli değildir; Örneğin, `strtok_s` Bu sorun yok.  
  
 CRT durumu için statik bir CRT bağlayarak yerleşik bir DLL olacağı için statik olarak bu sonuçlarını özellikle istenen ve anladım sürece DLL'de CRT bağlamak için önerilmez. Örneğin, çağırırsanız [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) kendi statik CRT bağlı DLL yükleyen bir yürütülebilir dosya içinde DLL kod tarafından oluşturulan tüm donanım özel durumları Çeviricisi, ancak donanım özel durumları tarafından Yakalanacak değil ana kod tarafından oluşturulan yürütülebilir yakalanma yeri.  
  
 Kullanıyorsanız **/CLR** derleyici geçiş kodunuzu bağlantılı olması ile bir statik kitaplık, msvcmrt.lib. Statik kitaplık, yönetilen kod ve yerel CRT arasındaki proxy sağlar. Statik olarak bağlantılı CRT kullanamazsınız ( **/MT** veya **/MTd** seçenekleri) ile **/CLR**. Dinamik olarak bağlı kitaplıklarını kullanma (**/MD** veya **/MDd**) yerine.  
  
 Kullanıyorsanız **/CLR: pure** derleyici anahtar kodunuzu statik kitaplık msvcurt.lib ile bağlanır. İle **/CLR**, statik olarak bağlantılı kitaplıkla bağlayamazsınız. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri, Visual Studio 2015'ten başlayarak dışıdır.  
  
 CRT ile kullanma hakkında daha fazla bilgi için **/CLR**, bkz: [karışık (yerel ve yönetilen) derlemeler](../dotnet/mixed-native-and-managed-assemblies.md); için **/CLR: pure**, bkz: [saf ve doğrulanabilen kod (C + +/ CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Hata ayıklama sürümü, uygulamanızın oluşturmak için [_DEBUG](../c-runtime-library/debug.md) bayrağı tanımlanmalıdır ve uygulama bir hata ayıklama sürümü bu kitaplıklar biri ile bağlanması gerekir. Kitaplık dosyaları hata ayıklama sürümleri kullanma hakkında daha fazla bilgi için bkz: [CRT hata ayıklama teknikleri](/visualstudio/debugger/crt-debugging-techniques).  
  
 CRT bu sürümü tam olarak C99 standart ile uyumlu değil. Özellikle, \<tgmath.h > Üstbilgi ve CX_LIMITED_RANGE/FP_CONTRACT pragması makroları desteklenmez. Standart GÇ işlevlerinde parametre belirticileri anlamını gibi belirli öğeleri varsayılan olarak eski yorumlar kullanır. /Zc derleyici uyumluluğu seçenekleri kullanın ve kitaplık uygunluk bazı yönlerini denetlemek için bağlayıcı seçenekleri belirtin,  
  
## <a name="c-standard-library"></a>C++ Standart Kitaplığı  
  
|C++ Standart Kitaplığı|Özellikler|Seçenek|Ön işlemci yönergeleri|  
|----------------------------|---------------------|------------|-----------------------------|  
|LIBCPMT. LIB|Birden çok iş parçacıklı, statik bağlantı|**/ MT**|_MT|  
|MSVCPRT. LIB|Birden çok iş parçacıklı, dinamik bağlantı (kitaplığı içeri aktarmak için MSVCP\<sürüm > .dll)|**/MD**|_MT, _DLL|  
|LIBCPMTD. LIB|Birden çok iş parçacıklı, statik bağlantı|**/ MTd**|_DEBUG, _MT|  
|MSVCPRTD. LIB|Birden çok iş parçacıklı, dinamik bağlantı (kitaplığı içeri aktarmak için MSVCP\<sürüm > D.DLL)|**/ MDd**|_DEBUG, _MT, _DLL|  
  
 Yayın sürümü, projenizin temel C çalışma zamanı kitaplıkları (LIBCMT. birini oluşturduğunuzda LIB, MSVCMRT. LIB, MSVCRT. LIB) varsayılan olarak bağlı olduğu, seçtiğiniz bağlı olarak derleyici seçeneği (birden çok iş parçacıklı, DLL, / CLR). Aşağıdakilerden birini eklerseniz [C++ standart kitaplık üstbilgi dosyaları](../standard-library/cpp-standard-library-header-files.md) kodunuzda C++ Standart Kitaplığı, otomatik olarak tarafından Visual C++ derleme zamanında bağlanır. Örneğin:  
  
```  
#include <ios>   
```  
  
## <a name="what-problems-exist-if-an-application-uses-more-than-one-crt-version"></a>Bir uygulama birden fazla CRT sürümü kullanıyorsa, hangi sorunları var?  
 Birden fazla DLL veya EXE varsa, Visual C++'ün farklı sürümlerini kullanan olup olmadığına bakılmaksızın birden fazla CRT olabilir. Örneğin, statik olarak CRT birden çok DLL'lere bağlantılandırma aynı sorun yaratabilir. Bu sorun statik büyüklükteki CRT'lerden karşılaşmadan geliştiriciler belirtildiği ile derlemek için **/MD** CRT DLL kullanılacak. DLL'leri DLL sınırından CRT kaynakları geçirirseniz, eşleşmeyen büyüklükteki CRT'lerden sorunlarla karşılaşırsanız ve Visual C++ ile projenizi yeniden derleyin gerekir.  
  
 Programınızı CRT birden fazla sürümünü kullanıyorsanız, bazı dikkatli DLL sınırlarından belirli CRT nesnelerini (örneğin, dosya tanıtıcısı, yerel ve ortam değişkenleri) geçirilirken gereklidir. İlgili sorunlar hakkında daha fazla bilgi ve bunların nasıl çözüleceği için bkz: [olası hataları geçirme CRT nesnelerini DLL sınırlar boyunca](../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Çalışma Zamanı Kitaplığı Başvurusu](../c-runtime-library/c-run-time-library-reference.md)