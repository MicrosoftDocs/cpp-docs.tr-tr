---
title: Kodunuzu Evrensel CRT’ye yükseltme
ms.date: 03/31/2017
ms.assetid: eaf34c1b-da98-4058-a059-a10db693a5ce
ms.openlocfilehash: 0554ff713b499f99e7e7508faf687c1635e6d912
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627180"
---
# <a name="upgrade-your-code-to-the-universal-crt"></a>Kodunuzu Evrensel CRT’ye yükseltme

Visual Studio 2015 ' de, Microsoft C çalışma zamanı kitaplığı (CRT) yeniden düzenlenmiş idi. Standart C Kitaplığı, POSIX uzantıları ve Microsoft 'a özgü işlevler, makrolar ve genel değişkenler, evrensel C çalışma zamanı kitaplığı (Universal CRT veya UCRT) yeni bir kitaplığa taşınmıştır. CRT 'ın derleyiciye özgü bileşenleri yeni bir vcruntime kitaplığına taşındı.

UıCRT artık bir Windows bileşenidir ve Windows 10 ' un bir parçası olarak gelir. UCRT, C çağırma kurallarını temel alan kararlı bir ABı destekler ve yalnızca birkaç özel durum ile ISO C99 standardına yakından uyumludur. Artık derleyicinin belirli bir sürümüne bağlı değildir. UıCRT ' i Visual Studio 2015 veya Visual Studio 2017 tarafından desteklenen herhangi bir Windows sürümünde kullanabilirsiniz. Bu avantajda, artık derlemelerinizi Visual Studio 'nun her yükseltmesinde yeni bir CRT sürümünü hedeflemek için güncelleştirmeniz gerekmez.

Bu yeniden düzenleme ile, çok sayıda CRT üstbilgi dosyası, kitaplık dosyası ve yeniden dağıtılabilir adları ve konumları ve kodunuz için gereken dağıtım yöntemleri değişmiştir. Ayrıca, standartlara uyum sağlamak için UCRT 'daki birçok işlev ve makro eklenmiştir veya değiştirilmiştir. Bu değişikliklerden faydalanmak için, mevcut kodunuz ve proje yapı sistemleriniz güncellenmelidir.

## <a name="where-to-find-the-universal-crt-files"></a>Evrensel CRT dosyalarının nerede bulunacağı

Windows bileşeni olarak, UıCRT kitaplık dosyaları ve üst bilgileri artık Windows yazılım geliştirme seti 'nin (SDK) bir parçasıdır. Visual Studio 'Yu yüklediğinizde, UCRT 'yi kullanmak için gereken Windows SDK bölümleri de yüklenir. Visual Studio yükleyicisi, UıCRT üstbilgileri, kitaplıkları ve DLL dosyalarının konumlarını Visual Studio proje yapı sistemi tarafından kullanılan varsayılan yollara ekler. Visual Studio C++ projelerinizi güncelleştirdiğinizde, varsayılan proje AYARLARıNı kullanıyorsa IDE otomatik olarak üstbilgi dosyaları için yeni konumları bulur ve bağlayıcı, yeni varsayılan uıcrt ve vcruntime kitaplıklarını otomatik olarak kullanır. Benzer şekilde, komut satırı yapılarını yapmak için bir geliştirici komut istemi kullanıyorsanız, üst bilgiler ve kitaplıklar için yol içeren ortam değişkenleri de güncelleştirilir ve otomatik olarak çalışır.

Standart C Kitaplığı üst bilgi dosyaları artık SDK sürümüne özgü bir dizindeki içerme klasöründeki Windows SDK bulunur. Üst bilgi dosyaları için tipik bir konum Windows Kits 'in altındaki Program Files veya Program Files (x86) dizininde bulunur\\10\\, _SDK sürümü_ bir Windows sürümüne karşılık gelen\\_sdk-sürümü_\\UCRT içerir. güncelleştirme, örneğin, Windows 10 ' un yıldönümü güncelleştirmesi için 10.0.14393.0.

UıCRT statik kitaplıkları ve dinamik bağlantı saplama kitaplıkları Windows Kits altındaki Program Files veya Program Files (x86) dizininde bulunur\\10\\lib\\_SDK-sürümü_\\UCRT\\_mimari_, burada  _mimari_ ARM, x86 veya x64. Perakende ve hata ayıklama statik kitaplıkları libucrt. lib ve libucrtd. lib ' dir ve UCRT dll 'Leri için kitaplıklar UCRT. lib ve ucrtd. lib ' dir.

Perakende ve hata ayıklama UıCRT dll 'Leri ayrı konumlarda bulunur. Perakende dll 'Leri yeniden dağıtılabilir ve Windows Kits 'in altındaki Program Files veya Program Files (x86) dizininde,\\10\\Redist\\uıcrt\\dll\\_mimari_\. Hata ayıklama UıCRT kitaplıkları yeniden dağıtılabilir değildir ve Windows setleri\\10\\bin\\_mimarisi_\\UCRT klasörü altında Program Files veya Program Files (x86) dizininde bulunabilir.

C ve C++ derleyiciye özgü çalışma zamanı destek kitaplığı, **vcruntime**, program başlangıcını ve özel durum işleme ve iç bilgiler gibi özellikleri desteklemek için gereken kodu içerir. Kitaplık ve üst bilgi dosyaları, program dosyalarınızda veya Program Files (x86) dizininizdeki sürüme özgü Microsoft Visual Studio klasöründe hala bulunur. Visual Studio 2017 ' de üst bilgiler Microsoft Visual Studio\\2017\\_edition_\\VC\\araçları\\MSVC\\_lıb-Version_\\Içerir ve bağlantı kitaplıkları Microsoft altında bulunur Visual Studio\\2017\\_edition_\\VC\\araçları\\MSVC\\_lıb-Version_\\lib\\_mimarisi_ _, sürüm Visual_ Studio 'nun sürümüdür yüklü, _LIB-Version_ , kitaplıkların sürümüdür ve _mimaride_ işlemcinin mimarisi vardır. OneCore ve Store için bağlantı kitaplıkları kitaplıklar klasöründe de bulunur. Statik kitaplığın perakende ve hata ayıklama sürümleri libvcruntime. lib ve libvcruntimed. lib ' dir. Dinamik bağlantı perakende ve hata ayıklama saplama kitaplıkları sırasıyla vcruntime. lib ve vcruntimed. lib ' dir.

Visual C++ Studio projelerinizi güncelleştirdiğinizde, projenin **bağlayıcı** özelliği **tüm varsayılan kitaplıkları** **Evet** olarak Yoksay ' ı veya komut satırında `/NODEFAULTLIB` bağlayıcı seçeneğini kullanırsanız, sizin listenizi güncelleştirmeniz gerekir New, yeniden düzenlenmiş kitaplıklarını dahil etmek için kitaplıklar. Eski CRT kitaplığı, örneğin, LIBCMT. lib, libcmtd. lib, Msvcrt. lib veya msvcrtd. lib gibi eşdeğer yeniden düzenlenmiş kitaplıklarıyla değiştirin. Kullanılacak belirli kitaplıklar hakkında daha fazla bilgi için bkz. [CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md).

## <a name="deployment-and-redistribution-of-the-universal-crt"></a>Evrensel CRT 'nın dağıtımı ve yeniden dağıtılması

UıCRT artık bir Microsoft Windows işletim sistemi bileşeni olduğundan, Windows 10 ' da işletim sisteminin bir parçası olarak dahil edilmiştir ve daha eski işletim sistemleri için Windows Update aracılığıyla, Windows Vista Windows 8.1 üzerinden kullanılabilir. Windows XP için yeniden dağıtılabilir bir sürüm kullanılabilir. Bir işletim sistemi bileşeni olarak, UCRT güncelleştirmeleri ve bakımı, Windows Update Visual Studio ve Microsoft C++ derleyicisi sürümlerinden bağımsız olarak yönetilir. UıCRT bir Windows bileşeni olduğundan, güvenlik ve güncelleştirme kolaylığı ve daha küçük bir görüntü boyutu için, uygulamanız için UıCRT 'nin merkezi dağıtımını öneririz.

UıCRT ' i Visual Studio 2015 veya Visual Studio 2017 tarafından desteklenen herhangi bir Windows sürümünde kullanabilirsiniz. Windows 10 dışındaki desteklenen Windows sürümleri için bir VCRedist paketi kullanarak yeniden dağıtabilirsiniz. VCRedist paketleri UCRT bileşenleri içerir ve bunları varsayılan olarak yüklenmeyen Windows işletim sistemlerine otomatik olarak yükler. Daha fazla bilgi için bkz. [görsel C++ dosyaları yeniden dağıtma](../windows/redistributing-visual-cpp-files.md).

UıCRT 'ın uygulama yerel dağıtımı desteklenir, ancak hem performans hem de güvenlik nedenleriyle önerilmez. Uygulama yerel dağıtımı için dll 'Ler, **Redist** alt dizininin altında Windows SDK bir parçası olarak dahil edilir. Gerekli dll 'Ler, uıcrtbase. dll dosyasını ve API-MS-Win-_altkümesi_. dll adlı bir **apiset iletici** dll kümesini içerir. Her işletim sisteminde gereken dll 'Ler kümesi farklılık gösterir, bu nedenle App-Local dağıtımını kullandığınızda tüm dll 'Leri dahil etmeniz önerilir. Uygulama yerel dağıtımı hakkında ek ayrıntılar ve uyarılar için bkz. [ C++Visual 'te dağıtım ](../windows/deployment-in-visual-cpp.md).

## <a name="changes-to-the-universal-crt-functions-and-macros"></a>Evrensel CRT işlevleri ve Makrolarındaki Değişiklikler

ISO C99 uyumlarını artırmak ve kod kalitesi ve güvenlik sorunlarını gidermek için UCRT 'ye çok sayıda işlev eklenmiştir veya güncelleştirilir. Bazı durumlarda, bu gerekli önemli değişiklikleri kitaplıkta değiştirir. Daha eski bir CRT sürümü kullanılırken kodunuz düzgün şekilde derlenirse, ancak UCRT kullanılarak derlendiğinde, Bu güncelleştirmelerden ve özelliklerden yararlanmak için kodunuzu değiştirmelisiniz. Evrensel CRT 'ta bulunan CRT üzerinde yapılan son değişikliklerin ve güncelleştirmelerin ayrıntılı bir listesi için görsel C++ değişiklik geçmişinin [C çalışma zamanı kitaplığı (CRT)](visual-cpp-change-history-2003-2015.md#BK_CRT) bölümüne bakın. Kodunuzda gereken değişiklikleri belirlemek için kullanabileceğiniz etkilenen üstbilgiler ve işlevlerin bir listesini içerir.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Taşıma ve Yükseltme Kılavuzu](visual-cpp-porting-and-upgrading-guide.md)<br/>
[Olası Yükseltme Sorunlarına Genel Bakış (Visual C++)](overview-of-potential-upgrade-issues-visual-cpp.md)<br/>
[Projeleri Visual 'ın önceki sürümlerinden yükseltmeC++](upgrading-projects-from-earlier-versions-of-visual-cpp.md)<br/>
[Visual C++ değişiklik geçmişi 2003 - 2015](visual-cpp-change-history-2003-2015.md)<br/>
[Visual Studio’deki C++ uyumluluk geliştirmeleri](../overview/cpp-conformance-improvements.md)
