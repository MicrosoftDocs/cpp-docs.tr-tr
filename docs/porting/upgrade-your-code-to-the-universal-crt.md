---
title: Kodunuzu Evrensel CRT'ye yükseltme
ms.date: 03/31/2017
ms.assetid: eaf34c1b-da98-4058-a059-a10db693a5ce
ms.openlocfilehash: bdf1615d47361654e9690977520d01c332098438
ms.sourcegitcommit: b72a10a7b12e722fd91a17406b91b270026f763a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/03/2019
ms.locfileid: "58898771"
---
# <a name="upgrade-your-code-to-the-universal-crt"></a>Kodunuzu Evrensel CRT'ye yükseltme

Microsoft C çalışma zamanı kitaplığı (CRT), Visual Studio 2015'te yeniden düzenlenen. Standart C Kitaplığı, POSIX uzantıları ve Microsoft'a özgü işlevleri, makroları ve genel değişkenler, Evrensel C çalışma zamanı kitaplığı (Evrensel CRT veya UCRT) gibi yeni bir kitaplık içine taşındı. CRT derleyici özgü bileşenlerinin yeni bir vcruntime kitaplık içine taşındı.

UCRT artık Windows bir bileşendir ve Windows 10 'un bir parçası olarak sunulur. C çağırma kurallarına dayalı kararlı bir ABI UCRT destekler ve yalnızca birkaç özel durum ile birlikte standart ISO C99 yakından uyacağını. Artık, belirli bir derleyici sürümü için de bağlıdır. Visual Studio 2015 veya Visual Studio 2017 tarafından desteklenen Windows sürümlerini UCRT kullanabilirsiniz. Yararı, artık derlemelerinizi CRT gpprep'i her yükseltme Visual Studio'nun yeni bir sürümü hedeflemek için güncelleştirilecek olmanızın gerekmesidir.

Bu yeniden düzenleme ile adlar veya konumlar birçok CRT üst bilgi dosyaları, kitaplık dosyalarını ve yeniden dağıtılabilir dosyaları, kodunuz için gerekli dağıtım yöntemleri değişti. Ayrıca, birçok işlevi ve UCRT makrolarındaki eklenmiş veya standartlara uyumluluk geliştirmek için değiştirildi. Bu değişikliklerin yararlanmak için mevcut kodunuzu ve Proje yapı sistemi güncelleştirilmesi gerekir.

## <a name="where-to-find-the-universal-crt-files"></a>Evrensel CRT dosyaları nerede bulacağını

Bir Windows bileşeni, UCRT kitaplık dosyalarını ve üst bilgiler artık Windows Yazılım Geliştirme Seti (SDK) parçası olan. Visual Studio'yu yüklediğinizde UCRT kullanmak için gerekli Windows SDK'sının bölümleri de yüklenir. Visual Studio yükleyicisi UCRT üst bilgiler, kitaplıklar ve DLL dosyaları Visual Studio Proje tarafından kullanılan varsayılan yollara konumlarını yapı sistemi ekler. Varsayılan proje ayarlarını kullanıyorlarsa, Visual C++ projeleri güncelleştirdiğinizde, IDE'nin başlık dosyaları için yeni konumlar otomatik olarak bulur ve bağlayıcı otomatik olarak vcruntime kitaplıkları ve yeni varsayılan UCRT kullanır. Benzer şekilde, bir geliştirici komut istemi yapmak için kullandığınız komut satırı derlemeleri, otomatik olarak iyi iş ve ortamı içeren üst bilgiler ve kitaplıklar için yolları değişkenler güncelleştirilir.

Standart C Kitaplığı üst bilgi dosyaları artık Windows SDK'yı bir SDK sürümüne özel dizin Ekle klasöründe bulunamadı. Program dosyaları veya Program dosyaları (x86) Windows Setleri dizininde üst bilgi dosyaları için tipik bir konum olduğu\\10\\INCLUDE\\_sdk sürümü_\\ucrt, burada _sdk sürümü_ bir Windows sürümü veya güncelleştirme, örneğin 10.0.14393.0 Yıldönümü güncelleştirmesi, Windows 10 için karşılık gelir.

Dinamik bağlantı saplama kitaplıkları ve statik kitaplıklar UCRT Program dosyaları veya Program dosyaları (x86) Windows Setleri dizininde bulunan\\10\\LIB\\_sdk sürümü_\\ucrt \\ _mimarisi_burada _mimarisi_ ARM, x 86 veya X64 olduğu. Perakende ve hata ayıklama statik kitaplıklar libucrt.lib ve libucrtd.lib ve UCRT DLL'ler kitaplıkları ucrt.lib ve ucrtd.lib vardır.

Perakende ve UCRT DLL'lerin hata ayıklama ayrı konumlarda bulunabilir. Perakende DLL'leri yeniden dağıtılabilir ve Program dosyaları veya Program dosyaları (x86) Windows Setleri dizininde bulunabilir\\10\\Redist\\ucrt\\DLL'leri\\_mimarisi_\. Hata ayıklama UCRT kitaplıkları yeniden dağıtılamaz ve Program dosyaları veya Program dosyaları (x86) Windows Setleri dizininde bulunabilir\\10\\bin\\_mimarisi_\\ucrt klasör.

C ve C++ Derleyici özgü çalışma zamanı desteği Kitaplığı **vcruntime**, program başlatma desteklemek için gereken kodu içerir ve özel durum işleme ve yapı içleri gibi özellikleri. Kitaplık ve üstbilgi dosyaları yine de Program dosyaları veya Program files (x86) dizini sürüme özgü Microsoft Visual Studio klasöründe bulunur. Visual Studio 2017'de üstbilgileri Microsoft Visual Studio altında bulunan\\2017\\_edition_\\VC\\Araçları\\MSVC\\  _LIB sürüm_\\içerir ve bağlantı kitaplıkları, Microsoft Visual Studio altında bulunan\\2017\\_edition_\\VC\\araçları \\MSVC\\_LIB sürüm_\\LIB\\_mimarisi_burada _edition_ sürümü Visual Studio'nun yüklü _LIB sürüm_ kitaplıkları sürümüdür ve _mimarisi_ İşlemci mimarisi. OneCore ve Store için bağlantı kitaplıkları da kitaplıklar klasöründe bulunur. Perakende ve hata ayıklama statik kitaplığı libvcruntime.lib ve libvcruntimed.lib sürümleridir. Dinamik bağlantı perakende ve hata ayıklama saplama kitaplıkları vcruntime.lib ve vcruntimed.lib, sırasıyla vardır.

Güncelleştirdiğinizde, Visual C++ projeleri projenin ayarlarsanız **bağlayıcı** özelliği **tüm varsayılan kitaplıkları Yoksay** için **Evet** veya kullanıyorsanız `/NODEFAULTLIB` komut satırını ve ardından bağlayıcı seçeneğini listenize yeni, işlenmiş kitaplıkları eklenecek kitaplıklar güncelleştirmeniz gerekir. Eski CRT kitaplığı, LIBCMT.lib, lıbcmtd.lib, msvcrt.lib veya msvcrtd.lib, eşdeğer UIMap'e yeniden işlenmiş kitaplıkları ile değiştirin. Kullanılacak belirli kitaplıkları hakkında daha fazla bilgi için bkz: [CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md).

## <a name="deployment-and-redistribution-of-the-universal-crt"></a>Dağıtım ve evrensel CRT dağıtılması

UCRT artık Microsoft Windows işletim sisteminin bir bileşeni olduğundan, Windows 10 işletim sisteminin parçası olarak dahil edilir ve eski işletim sistemleri, Windows Vista ile Windows 8.1 için Windows Update aracılığıyla kullanılabilir. Yeniden dağıtılabilir sürüm, Windows XP için kullanılabilir. Bir işletim sistemi bileşeni olarak bağımsız olarak Visual Studio ve Microsoft C++ Derleyici sürümleri UCRT güncelleştirmeler ve Bakım Windows Update tarafından yönetilir. Güvenlik ve güncelleştirmeler ve daha küçük bir görüntü boyutu kolaylığı için bir Windows bileşeni UCRT olduğundan UCRT uygulamanız için merkezi dağıtımı önerilir.

Visual Studio 2015 veya Visual Studio 2017 tarafından desteklenen Windows sürümlerini UCRT kullanabilirsiniz. Windows 10 dışında Windows'ın desteklenen sürümleri için vcredist paketini kullanarak dağıtabilirsiniz. Vcredist paketleri UCRT bileşenleri içerir ve otomatik olarak Windows işletim sistemlerinde, bunları varsayılan olarak yüklü olmayan yükleyin. Daha fazla bilgi için [Visual C++ dosyalarını yeniden dağıtma](../windows/redistributing-visual-cpp-files.md).

Hem performans hem de güvenlik nedeniyle önerilmez olsa UCRT uygulaması yerel dağıtımını desteklenir. Uygulama yerel dağıtım DLL'leri altında Windows SDK ' nın bir parçası olarak dahil edilen **redist** alt. Gereken DLL'leri ucrtbase.dll ve bir dizi içeren **APISet ileticisi** API adlı DLL'leri-ms-win -_alt_.dll. Her işletim sisteminde gerekli DLL'lerin kümesini uygulaması yerel dağıtım kullandığınızda tüm DLL'leri dahil önerilen şekilde değişir. Ek ayrıntılar ve yerel uygulama dağıtımı hakkında uyarılar için bkz: [Visual C++ üzerinde dağıtım](../windows/deployment-in-visual-cpp.md).

## <a name="changes-to-the-universal-crt-functions-and-macros"></a>Değişiklikleri makroları ve evrensel CRT işlevleri

Birçok işlev eklendi veya ISO C99 uyumluluğu artırmak için UCRT ve kod kalitesi ve güvenlik sorunlarını gidermek için güncelleştirildi. Bazı durumlarda, bu kitaplığa önemli değişiklikler gereklidir. CRT ancak UCRT kullanılarak derlendiğinde sonları daha eski bir sürümünü kullanırken kodunuzun düzgün bir şekilde derlenir, bu güncelleştirmeler ve özelliklerle yararlanmak için kodunuzu değiştirmeniz gerekir. CRT Evrensel CRT içinde bulunan güncelleştirmeleri ve önemli değişiklikler ayrıntılı listesi için bkz: [C çalışma zamanı kitaplığı (CRT)](visual-cpp-change-history-2003-2015.md#BK_CRT) bölümü Visual C++ değişiklik geçmişi. Bu, etkilenen üst bilgiler ve kodunuzda gereken değişiklikleri belirlemek için kullanabileceğiniz işlevlerin listesini içerir.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ taşıma ve yükseltme Kılavuzu](visual-cpp-porting-and-upgrading-guide.md)<br/>
[Olası yükseltme sorunlarına (Visual C++) genel bakış](overview-of-potential-upgrade-issues-visual-cpp.md)<br/>
[Önceki Visual C++ Sürümü Projelerini Yükseltme](upgrading-projects-from-earlier-versions-of-visual-cpp.md)<br/>
[Visual C++ değişiklik geçmişi 2003-2015](visual-cpp-change-history-2003-2015.md)<br/>
[Visual Studio'da C++ uyumluluk geliştirmeleri](../overview/cpp-conformance-improvements.md)
