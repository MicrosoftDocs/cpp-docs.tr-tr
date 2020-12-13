---
description: "Hakkında daha fazla bilgi edinin: kodunuzu Evrensel CRT 'ye yükseltme"
title: Kodunuzu Evrensel CRT’ye yükseltme
ms.date: 03/31/2017
ms.assetid: eaf34c1b-da98-4058-a059-a10db693a5ce
ms.openlocfilehash: a69643fb2741cef929b7dfc4a3908c8001b367ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331204"
---
# <a name="upgrade-your-code-to-the-universal-crt"></a>Kodunuzu Evrensel CRT’ye yükseltme

Visual Studio 2015 ' de, Microsoft C çalışma zamanı kitaplığı (CRT) yeniden düzenlenmiş idi. Standart C Kitaplığı, POSIX uzantıları ve Microsoft 'a özgü işlevler, makrolar ve genel değişkenler, evrensel C çalışma zamanı kitaplığı (Universal CRT veya UCRT) yeni bir kitaplığa taşınmıştır. CRT 'ın derleyiciye özgü bileşenleri yeni bir vcruntime kitaplığına taşındı.

UıCRT artık bir Windows bileşenidir ve Windows 10 ' un bir parçası olarak gelir. UCRT, C çağırma kurallarını temel alan kararlı bir ABı destekler ve yalnızca birkaç özel durum ile ISO C99 standardına yakından uyumludur. Artık derleyicinin belirli bir sürümüne bağlı değildir. UıCRT ' i Visual Studio 2015 veya Visual Studio 2017 tarafından desteklenen herhangi bir Windows sürümünde kullanabilirsiniz. Bu avantajda, artık derlemelerinizi Visual Studio 'nun her yükseltmesinde yeni bir CRT sürümünü hedeflemek için güncelleştirmeniz gerekmez.

Bu yeniden düzenleme ile, çok sayıda CRT üstbilgi dosyası, kitaplık dosyası ve yeniden dağıtılabilir adları ve konumları ve kodunuz için gereken dağıtım yöntemleri değişmiştir. Ayrıca, standartlara uyum sağlamak için UCRT 'daki birçok işlev ve makro eklenmiştir veya değiştirilmiştir. Bu değişikliklerden faydalanmak için, mevcut kodunuz ve proje yapı sistemleriniz güncellenmelidir.

## <a name="where-to-find-the-universal-crt-files"></a>Evrensel CRT dosyalarının nerede bulunacağı

Windows bileşeni olarak, UıCRT kitaplık dosyaları ve üst bilgileri artık Windows yazılım geliştirme seti 'nin (SDK) bir parçasıdır. Visual Studio 'Yu yüklediğinizde, UCRT 'yi kullanmak için gereken Windows SDK bölümleri de yüklenir. Visual Studio yükleyicisi, UıCRT üstbilgileri, kitaplıkları ve DLL dosyalarının konumlarını Visual Studio proje yapı sistemi tarafından kullanılan varsayılan yollara ekler. Visual Studio C++ projelerinizi güncelleştirdiğinizde, varsayılan proje ayarlarını kullanıyorsa IDE otomatik olarak üstbilgi dosyaları için yeni konumları bulur ve bağlayıcı, yeni varsayılan UıCRT ve vcruntime kitaplıklarını otomatik olarak kullanır. Benzer şekilde, komut satırı yapılarını yapmak için bir geliştirici komut istemi kullanıyorsanız, üst bilgiler ve kitaplıklar için yol içeren ortam değişkenleri de güncelleştirilir ve otomatik olarak çalışır.

Standart C Kitaplığı üst bilgi dosyaları artık SDK sürümüne özgü bir dizindeki içerme klasöründeki Windows SDK bulunur. Üst bilgi dosyaları için tipik bir konum Windows Kits 10 ' un altındaki Program Files veya Program Files (x86) dizininde \\ yer \\ alır \\  \\ . burada _SDK-sürümü_ bir Windows sürümüne veya güncelleştirmesine karşılık gelir; Örneğin, Windows 10 ' un yıldönümü güncelleştirmesi için 10.0.14393.0.

UıCRT statik kitaplıkları ve dinamik bağlantı saplama kitaplıkları Windows Kits 10 lib SDK-Version UCRT mimarisinin altındaki Program Files veya Program Files (x86) dizininde bulunur \\ \\ \\  \\ \\ , burada _mimari_ ARM, x86 veya x64. Perakende ve hata ayıklama statik kitaplıkları libucrt. lib ve libucrtd. lib ' dir ve UCRT dll 'Leri için kitaplıklar UCRT. lib ve ucrtd. lib ' dir.

Perakende ve hata ayıklama UıCRT dll 'Leri ayrı konumlarda bulunur. Perakende dll 'Leri yeniden dağıtılabilir ve Windows Kits \\ 10 \\ Redist \\ UCRT \\ dll \\ _mimarisinde_ Program Files veya Program Files (x86) dizininde bulunabilir\. Hata ayıklama UıCRT kitaplıkları yeniden dağıtılabilir değildir ve Windows setleri \\ 10 \\ bin \\ _mimarisi_ \\ UCRT klasörü altındaki program dosyaları veya program dosyaları (x86) dizininde bulunabilir.

C ve C++ derleyiciye özel çalışma zamanı destek kitaplığı, **vcruntime**, program başlangıcını ve özel durum işleme ve iç bilgiler gibi özellikleri desteklemek için gereken kodu içerir. Kitaplık ve üst bilgi dosyaları, program dosyalarınızda veya Program Files (x86) dizininizdeki sürüme özgü Microsoft Visual Studio klasöründe hala bulunur. Visual Studio 2017 ' de üst bilgiler Microsoft Visual Studio \\ 2017 \\ _sürümü_ \\ VC \\ araçları \\ MSVC \\ _lib-version_' ın altında bulunur \\ ve bağlantı kitaplıkları Microsoft Visual Studio \\ 2017 \\ _Edition_ \\ VC \\ araçları \\ MSVC \\ _lib-Version_ \\ lib mimarisi altında bulunur; \\ burada _Sürüm_ Visual Studio 'nun yüklü olduğu, _LIB-Version_ , kitaplıkların sürümüdür ve _mimarinin_ işlemci mimarisidir. OneCore ve Store için bağlantı kitaplıkları kitaplıklar klasöründe de bulunur. Statik kitaplığın perakende ve hata ayıklama sürümleri libvcruntime. lib ve libvcruntimed. lib ' dir. Dinamik bağlantı perakende ve hata ayıklama saplama kitaplıkları sırasıyla vcruntime. lib ve vcruntimed. lib ' dir.

Visual Studio C++ projelerinizi güncelleştirdiğinizde, projenin **bağlayıcı** özelliğini **tüm varsayılan kitaplıkları** **Evet** olarak Yoksay ' ı veya `/NODEFAULTLIB` komut satırında bağlayıcı seçeneğini kullanırsanız, kitaplıkları listenizi yeni, yeniden düzenlenmiş kitaplıklarını içerecek şekilde güncelleştirmeniz gerekir. Eski CRT kitaplığı, örneğin, LIBCMT. lib, libcmtd. lib, Msvcrt. lib veya msvcrtd. lib gibi eşdeğer yeniden düzenlenmiş kitaplıklarıyla değiştirin. Kullanılacak belirli kitaplıklar hakkında daha fazla bilgi için bkz. [CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md).

## <a name="deployment-and-redistribution-of-the-universal-crt"></a>Evrensel CRT 'nın dağıtımı ve yeniden dağıtılması

UıCRT artık bir Microsoft Windows işletim sistemi bileşeni olduğundan, Windows 10 ' da işletim sisteminin bir parçası olarak dahil edilmiştir ve daha eski işletim sistemleri için Windows Update aracılığıyla, Windows Vista Windows 8.1 üzerinden kullanılabilir. Windows XP için yeniden dağıtılabilir bir sürüm kullanılabilir. Bir işletim sistemi bileşeni olarak, UCRT güncelleştirmeleri ve bakımı, Windows Update Visual Studio ve Microsoft C++ derleyicisi sürümlerinden bağımsız olarak yönetilir. UıCRT bir Windows bileşeni olduğundan, güvenlik ve güncelleştirme kolaylığı ve daha küçük bir görüntü boyutu için, uygulamanız için UıCRT 'nin merkezi dağıtımını öneririz.

UıCRT ' i Visual Studio 2015 veya Visual Studio 2017 tarafından desteklenen herhangi bir Windows sürümünde kullanabilirsiniz. Windows 10 dışındaki desteklenen Windows sürümleri için bir VCRedist paketi kullanarak yeniden dağıtabilirsiniz. VCRedist paketleri UCRT bileşenleri içerir ve bunları varsayılan olarak yüklenmeyen Windows işletim sistemlerine otomatik olarak yükler. Daha fazla bilgi için bkz. [Visual C++ dosyalarını yeniden dağıtma](../windows/redistributing-visual-cpp-files.md).

UıCRT 'ın uygulama yerel dağıtımı desteklenir, ancak hem performans hem de güvenlik nedenleriyle önerilmez. Uygulama yerel dağıtımı için dll 'Ler, **Redist** alt dizininin altında Windows SDK bir parçası olarak dahil edilir. Gerekli dll 'Ler ucrtbase.dll ve API-MS-Win-_altkümesi_. dll adlı bir **apiset iletici** dll kümesi içerir. Her işletim sisteminde gereken dll 'Ler kümesi farklılık gösterir, bu nedenle App-Local dağıtımını kullandığınızda tüm dll 'Leri dahil etmeniz önerilir. Uygulama yerel dağıtımı hakkında ek ayrıntılar ve uyarılar için bkz. [Visual C++ dağıtım](../windows/deployment-in-visual-cpp.md).

## <a name="changes-to-the-universal-crt-functions-and-macros"></a>Evrensel CRT işlevleri ve Makrolarındaki Değişiklikler

ISO C99 uyumlarını artırmak ve kod kalitesi ve güvenlik sorunlarını gidermek için UCRT 'ye çok sayıda işlev eklenmiştir veya güncelleştirilir. Bazı durumlarda, bu gerekli önemli değişiklikleri kitaplıkta değiştirir. Daha eski bir CRT sürümü kullanılırken kodunuz düzgün şekilde derlenirse, ancak UCRT kullanılarak derlendiğinde, Bu güncelleştirmelerden ve özelliklerden yararlanmak için kodunuzu değiştirmelisiniz. Evrensel CRT 'de bulunan CRT üzerinde yapılan son değişikliklerin ve güncelleştirmelerin ayrıntılı bir listesi için, Visual C++ değişiklik geçmişinin [C çalışma zamanı kitaplığı (CRT)](visual-cpp-change-history-2003-2015.md#BK_CRT) bölümüne bakın. Kodunuzda gereken değişiklikleri belirlemek için kullanabileceğiniz etkilenen üstbilgiler ve işlevlerin bir listesini içerir.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Taşıma ve Yükseltme Kılavuzu](visual-cpp-porting-and-upgrading-guide.md)<br/>
[Olası Yükseltme Sorunlarına Genel Bakış (Visual C++)](overview-of-potential-upgrade-issues-visual-cpp.md)<br/>
[Visual C++ önceki sürümlerinden projeleri yükseltme](upgrading-projects-from-earlier-versions-of-visual-cpp.md)<br/>
[Visual C++ değişiklik geçmişi 2003 - 2015](visual-cpp-change-history-2003-2015.md)<br/>
[Visual Studio 2017’deki C++ uyumluluk geliştirmeleri](../overview/cpp-conformance-improvements.md)
