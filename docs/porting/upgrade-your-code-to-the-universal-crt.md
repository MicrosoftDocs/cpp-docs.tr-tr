---
title: "Evrensel CRT kodunuzu yükseltme | Microsoft Docs"
ms.custom: 
ms.date: 03/31/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eaf34c1b-da98-4058-a059-a10db693a5ce
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e63945dc51fe55d81963790e7373a3d4dc9b0efe
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2018
---
# <a name="upgrade-your-code-to-the-universal-crt"></a>Evrensel CRT kodunuzu yükseltme

Visual Studio 2015'te Microsoft C çalışma zamanı kitaplığı (CRT) bulunanad. Standart C Kitaplığı, POSIX uzantıları ve Microsoft'a özgü işlevleri, makroları ve genel değişkenler, Evrensel C çalışma zamanı kitaplığı (Evrensel CRT veya UCRT) gibi yeni bir kitaplık içine taşındı. CRT derleyici özgü bileşenlerinin yeni bir vcruntime kitaplık içine taşındı.  
  
UCRT artık Windows bir bileşenidir ve Windows 10 bir parçası olarak gelir. Yalnızca birkaç istisna dışında standart ISO C99 yakından uyacağını ve C çağırma kurallarına göre kararlı bir ABI UCRT destekler. Artık derleyici belirli bir sürümünü de bağlıdır. Visual Studio 2015 veya Visual Studio 2017 tarafından desteklenen Windows sürümlerini UCRT kullanabilirsiniz. Avantajı, artık derlemeleriniz CRT yeni bir sürümü Visual Studio'nun her yükseltme ile hedef güncelleştirmek yeterli olmasıdır.  
  
Bu yeniden düzenleme ile adlar veya konumlar birçok CRT üstbilgi dosyaları, kitaplık dosyalarını ve yeniden dağıtılabilir öğeleri ve kodunuz için gerekli dağıtım yöntemleri değiştirilmiştir. Ayrıca, birçok işlevleri ve UCRT makroları eklendi veya standartları uyumluluğu artırmak için değiştirildi. Bu değişiklikler yararlanmak için var olan kodu ve proje derleme sistemleri güncelleştirilmesi gerekir.  
  
## <a name="where-to-find-the-universal-crt-files"></a>Evrensel CRT dosyaları nerede bulacağını

Bir Windows bileşeni, UCRT kitaplık dosyalarını ve üstbilgileri artık Windows Yazılım Geliştirme Seti (SDK) parçasıdır. Visual Studio yüklediğinizde UCRT kullanmak için gereken Windows SDK bölümlerini de yüklenir. Visual Studio yükleyicisi UCRT üstbilgileri, kitaplıklar ve Visual Studio projesi tarafından kullanılan varsayılan yollara DLL dosyalarının konumlarını oluşturma sistemi ekler. Varsayılan proje ayarları kullanırsanız, Visual C++ projeleri güncelleştirdiğinizde, IDE üstbilgi dosyaları için yeni konumlar otomatik olarak bulur ve bağlayıcı vcruntime kitaplıkları ve yeni varsayılan UCRT otomatik olarak kullanır. Benzer şekilde, yapmak için geliştirici komut istemi kullanırsanız, komut satırı derlemeleri, iş otomatik olarak yanı ve ortamı üst bilgilerinin ve kitaplıklarının yollarını içeren değişkenler güncelleştirilir.  
  
Standart C Kitaplığı üstbilgi dosyaları artık Windows SDK'ın SDK sürüm özgü bir dizini INCLUDE klasöründe bulunamadı. Program dosyaları ya da Windows setleri (x86) Program Files dizininde üstbilgi dosyaları için tipik bir konum olduğundan\\10\\INCLUDE\\_sdk sürümü_\\ucrt, burada _sdk sürümü_ 10.0.14393.0 Yıldönümü güncelleştirme, Windows 10 için bir Windows sürümü veya güncelleştirme, örneğin karşılık gelir.   
  
UCRT statik kitaplıklar ve dinamik bağlantı saplama kitaplıkları Program dosyaları ya da Windows setleri (x86) Program Files dizininde bulunan\\10\\Lib\\_sdk sürümü_\\ucrt \\ _mimarisi_, burada _mimarisi_ , x 86 veya X64 koludur. Perakende ve hata ayıklama statik kitaplıklar libucrt.lib ve libucrtd.lib, ve UCRT DLL'ler için kitaplıkları ucrt.lib ve ucrtd.lib.  
  
Perakende ve hata ayıklama UCRT DLL'leri ayrı konumda bulunamadı. Perakende DLL'leri yeniden dağıtılabilir ve Program dosyaları ya da Windows setleri (x86) Program Files dizininde bulunan\\10\\Redist\\ucrt\\DLL'leri\\_mimarisi_\. UCRT hata ayıklama kitaplıkları dağıtılamaz ve Program dosyaları ya da Windows setleri (x86) Program Files dizininde bulunan\\10\\bin\\_mimarisi_\\ucrt klasör.   

C ve C++ Derleyici özgü çalışma zamanı destek kitaplığı, **vcruntime**, program başlatma desteklemek için gereken kodunu içerir ve özel durum işleme ve ön tanımlı gibi özellikleri. Kitaplık ve başlık dosyaları hala sürüme özgü Microsoft Visual Studio klasöründe Program Files veya Program dosyaları (x86) dizini bulunamadı. Visual Studio 2017 ' altında Microsoft Visual Studio üstbilgileri bulunan\\2017\\_edition_\\VC\\Araçları\\MSVC\\  _LIB sürüm_\\içerir ve bağlantı kitaplıkları Microsoft Visual Studio altında bulunan\\2017\\_edition_\\VC\\araçları \\MSVC\\_lib sürüm_\\lib\\_mimarisi_, burada _edition_ sürümü Visual Studio yüklüyse, _lib sürüm_ kitaplıkları sürümüdür ve _mimarisi_ İşlemci mimarisi. OneCore ve depolama için bağlantı kitaplıkları da kitaplıkları klasöründe bulunur. Statik kitaplık perakende ve hata ayıklama sürümleri libvcruntime.lib ve libvcruntimed.lib yayımlanır. Dinamik bağlantı perakende ve hata ayıklama saplama kitaplıkları vcruntime.lib ve vcruntimed.lib, sırasıyla ' dir.  
  
Güncelleştirdiğinizde, Visual C++ projeleri projenin ayarlarsanız **bağlayıcı** özelliği **tüm varsayılan kitaplıkları Yoksay** için **Evet** veya /NODEFAULTLIB bağlayıcı kullanıyorsanız Komut satırında, sonra seçeneği listenize yeni, işlenmiş kitaplıkları dahil kitaplıkların güncelleştirmeniz gerekir. Eski CRT kitaplık, örneğin, libcmt.lib, libcmtd.lib, msvcrt.lib veya msvcrtd.lib, eşdeğer işlenmiş kitaplıkları ile değiştirin. Kullanmak için belirli kitaplıkları hakkında daha fazla bilgi için bkz: [CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md).  
  
## <a name="deployment-and-redistribution-of-the-universal-crt"></a>Dağıtım ve evrensel CRT dağıtılması
  
UCRT artık Microsoft Windows işletim sisteminin bir bileşeni olduğundan, Windows 10 işletim sisteminin parçası olarak dahil edilir ve daha eski işletim sistemleri, Windows 8.1 ile Windows Vista için Windows Update aracılığıyla kullanılabilir. Yeniden dağıtılabilir sürüm, Windows XP için kullanılabilir. Bir işletim sistemi bileşeni olarak UCRT güncelleştirmeler ve Bakım Windows Update tarafından Visual Studio ve Microsoft C++ Derleyici sürümler bağımsız olarak yönetilir. UCRT güvenlik güncelleştirmeleri ve daha küçük bir görüntü boyutu kolaylığı için bir Windows bileşeni olduğundan, uygulamanız için UCRT merkezi dağıtımını kesinlikle öneririz.  
  
Visual Studio 2015 veya Visual Studio 2017 tarafından desteklenen Windows sürümlerini UCRT kullanabilirsiniz. Windows 10 dışında Windows'un desteklenen sürümleri için vcredist paketini kullanarak dağıtabilirsiniz. Vcredist paketleri UCRT bileşenleri içerir ve otomatik olarak Windows işletim sistemlerinde, varsayılan olarak yüklü olmayan yükleyin. Daha fazla bilgi için bkz: [Visual C++ dosyalarını yeniden dağıtma](../ide/redistributing-visual-cpp-files.md).  
  
Performans ve güvenlik nedeniyle önerilmez ancak UCRT yerel uygulama dağıtımını desteklenir. Uygulama yerel dağıtım DLL'leri altında Windows SDK'ın bir parçası olarak dahil edilen **redist** alt dizin. Ucrtbase.dll ve bir dizi gerekli DLL'leri dahil **APISet iletici** API adlı DLL'leri-ms-win -_alt_.dll. Her işletim sisteminde gerekli DLL'leri kümesi uygulama yerel dağıtım kullandığınızda tüm DLL'ler eklenmesi önerilen şekilde değişir. Ek ayrıntılar ve yerel uygulama dağıtımı hakkında uyarılar için bkz: [Visual C++ üzerinde dağıtım](../ide/deployment-in-visual-cpp.md).  
  
## <a name="changes-to-the-universal-crt-functions-and-macros"></a>Makrolar ve evrensel CRT işlevleri yapılan değişiklikler  

Birçok işlevini eklendi veya ISO C99 uyumluluğu artırmak için UCRT ve kod kalitesini ve güvenlik sorunlarını gidermek için güncelleştirildi. Bazı durumlarda, bu kitaplığa yeni değişiklikler gereklidir. CRT ancak UCRT kullanılarak derlendiğinde sonları eski bir sürümünü kullanırken, kodunuzu düzgün bir şekilde derlenmiş ise bu güncelleştirmeler ve Özellikler yararlanmak için kodunu değiştirmeniz gerekir. Önemli değişiklikler ve güncelleştirmeler Evrensel CRT bulunan CRT için ayrıntılı bir listesi için bkz: [C çalışma zamanı kitaplığı (CRT)](visual-cpp-change-history-2003-2015.md#BK_CRT) Visual C++ bölümünü değişiklik geçmişini. Etkilenen üstbilgileri ve kodunuzda gereken değişiklikleri belirlemek için kullanabileceğiniz işlevlerin bir listesini içerir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Visual C++ Taşıma ve Yükseltme Kılavuzu](visual-cpp-porting-and-upgrading-guide.md)  
[Olası Yükseltme Sorunlarına Genel Bakış (Visual C++)](overview-of-potential-upgrade-issues-visual-cpp.md)  
[Önceki Visual C++ Sürümü Projelerini Yükseltme](upgrading-projects-from-earlier-versions-of-visual-cpp.md)  
[Visual C++ değişiklik geçmişi 2003 - 2015](visual-cpp-change-history-2003-2015.md)  
[Visual Studio 2017’deki C++ uyumluluk geliştirmeleri](../cpp-conformance-improvements-2017.md)  
