---
title: Visual C++ Dosyalarını Yeniden Dağıtma
ms.date: 11/04/2016
helpviewer_keywords:
- application deployment [C++], file redistributing
- redistributing applications [C++]
- deploying applications [C++], file redistributing
- file redistribution [C++]
- redistributing applications [C++], about redistributing applications
ms.assetid: d201b2ce-36f1-44e5-a96c-0db81a1ba652
ms.openlocfilehash: 46192fe7ff5b29c22a5001cc460c74f5ddf6d1bb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167933"
---
# <a name="redistributing-visual-c-files"></a>Visual C++ Dosyalarını Yeniden Dağıtma

> [!NOTE]
> Visual C++ çalışma zamanı dosyalarından birinin indirileceği için buraya misiniz? [Microsoft Web sitesine](https://www.microsoft.com/) gidin ve arama kutusuna **görsel C++ yeniden dağıtılabilir** yazın. Bilgisayarınızın mimarisine yönelik yeniden dağıtılabilir paketi (örneğin, 64 bit Windows çalıştırıyorsanız x64) ve ihtiyacınız olan görsel C++ sürümünü (örneğin, 2015) indirip yükleyin.

Bir uygulamayı dağıtırken, onu desteklemek için gerekli tüm dosyaları da dağıtmalısınız. Bu dosyalardan herhangi biri Microsoft tarafından sağlanıyorsa, bunları yeniden dağıtma izniniz olup olmadığını kontrol edin. Visual Studio lisans koşulları 'nı gözden geçirmek için IDE 'deki Microsoft Visual Studio hakkında iletişim kutusunda lisans koşulları bağlantısına bakın veya [Microsoft yazılımı lisans koşulları](https://visualstudio.microsoft.com/license-terms/mlt687465/) dosyasını indirin. Visual Studio 'nun belirli sürümleri için Microsoft yazılımı lisans koşulları 'nın "dağıtılabilir kod" bölümünde başvurulan "REDıST listesi" ni görüntülemek için bkz. [Microsoft Visual Studio 2017 ve Microsoft Visual Studio 2017 SDK Için dağıtılabilir kod (yardımcı programları ve BuildServer dosyalarını içerir)](/visualstudio/productinfo/2017-redistribution-vs)veya Visual Studio 2015 için bkz. [Microsoft Visual Studio 2015 ve Microsoft Visual Studio 2015 SDK için dağıtılabilir kod](/visualstudio/productinfo/2015-redistribution-vs). Yeniden dağıtılabilir dosyalar hakkında daha fazla bilgi için bkz. [hangi dll 'lerin yeniden dağıtılacağını](determining-which-dlls-to-redistribute.md) ve [dağıtım örneklerini](deployment-examples.md)belirleme.

Yeniden dağıtılabilir görsel C++ dosyaları dağıtmak için, Visual Studio 'Da bulunan C++ Visual yeniden dağıtılabilir paketleri (VCRedist\_x86. exe, VCRedist\_x64. exe veya VCRedist\_ARM. exe) kullanabilirsiniz. Visual Studio 2017 ' de, bu dosyalar program dosyaları [(x86)]\\Microsoft Visual Studio\\2017\\_edition_\\VC\\REDIST\\MSVC\\_lib-Version_ klasöründe bulunabilir; burada _Sürüm_ Visual Studio Edition yüklü ve _LIB-Version_ , yeniden dağıtmak için kitaplıkların sürümüdür. Visual Studio 2015 ' de bu dosyalar, [(x86)] \Microsoft Visual Studio *Version*\Vc\redist\\*locale*\\Program Files içindeki Visual Studio yükleme dizininizin altında bulunabilir. Diğer bir seçenek de, Visual Studio 2017 ' de Program Files [(x86)]\\Microsoft Visual Studio\\2017\\_edition_\\VC\\REDIST\\MSVC\\_lib-sürümü_\\mergemodules\\ klasöründe bulunan yeniden dağıtılabilir birleştirme modüllerini (. msm dosyaları) kullanmaktır. Visual Studio 2015 ' de bu dosyalar program dosyaları [(x86)] \Ortak Files\Merge modülleri\\bulunabilir. Yeniden dağıtılabilir görsel C++ dll 'leri, yürütülebilir uygulama dosyanızı içeren klasörü olan *uygulama yerel klasörüne*doğrudan yüklemek de mümkündür. Bakım nedenleriyle, bu yükleme konumunu kullanmanızı önermiyoruz.

Visual C++ Yeniden Dağıtılabilir Paketleri tüm Visual C++ kitaplıklarını yükler ve kaydeder. Bu paketlerden birini kullanırsanız, uygulamanın yüklenmesi için bir önkoşul olarak hedef sistem üzerinde çalışacak şekilde ayarlamanız gerekir. Visual C++ kitaplıklarının otomatik güncelleştirilmesini sağladıklarından, dağıtımlarınız için bu paketleri kullanmanızı öneririz. Bu paketlerin nasıl kullanılacağına ilişkin bir örnek için bkz. [Izlenecek yol: görsel C++ yeniden dağıtılabilir C++ paketi kullanarak görsel uygulama dağıtma](deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).

Her bir C++ görsel yeniden dağıtılabilir paket, makinede daha yeni bir sürümün varlığını denetler. Daha yeni bir sürüm bulunursa paket yüklenmez. Visual Studio 2015 ' den başlayarak yeniden dağıtılabilir paketler, Kurulumun başarısız olduğunu belirten bir hata mesajı görüntüler. Bir paket **/quiet** bayrağını kullanarak çalışıyorsa, hata iletisi gösterilmez. Her iki durumda da, Microsoft yükleyicisi tarafından bir hata kaydedilir ve çağırana bir hata sonucu döndürülür. Visual Studio 2015 paketlerinde başlayarak, daha yeni bir sürümünün yüklü olup olmadığını öğrenmek için kayıt defterini denetleyerek bu hatadan kaçınabilirsiniz. Şu anda yüklü olan sürüm HKEY_LOCAL_MACHINE \SOFTWARE [\Wow6432Node] \Microsoft\VisualStudio\\_vs-Version_\Vc\çalışma zamanları\\{x86 | x64 | ARM} anahtarı, _vs-Version_ , Visual Studio 'nun sürüm numarasıdır (visual Studio 2015 ve visual Studio 2017 için 14,0), güncelleştirilmiş 2017 redistributable, 2015 sürümü ile ikili uyumlu olduğundan ve anahtarın ARM, x86 veya x64 olduğu, platform için yüklü VCRedist sürümlerine bağlı olarak. (Bir x64 platformunda yüklü x86 paketinin sürümünü görüntülemek için RegEdit kullanmıyorsanız Wow6432Node alt anahtarını denetlemeniz gerekmez.) Sürüm numarası REG_SZ dize değeri **sürümünde** ve ayrıca **ana**, **Ikincil**, **Bld**ve **rbld** REG_DWORD değerleri kümesinde depolanır. Yükleme zamanında bir hatadan kaçınmak için, şu anda yüklü olan sürüm daha yeni ise yeniden dağıtılabilir paket yüklemesini atlamanız gerekir.

Visual C++ dll içeren bir birleştirme modülü kullanıyorsanız, uygulamayı dağıtmak için kullandığınız Windows Installer paketine (veya benzer yükleme paketine) eklemeniz gerekir. Daha fazla bilgi için bkz. [birleştirme modüllerini kullanarak yeniden dağıtma](redistributing-components-by-using-merge-modules.md). Bir örnek için bkz. [Izlenecek yol: bir kurulum C++ projesi kullanarak görsel uygulama dağıtma](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md), ayrıca InstallShield Limited Edition 'ın bir yükleme paketi oluşturmak için nasıl kullanılacağı gösterilmektedir.

## <a name="potential-run-time-errors"></a>Olası Çalışma Zamanı Hataları

Windows uygulamanız için gerekli olan yeniden dağıtılabilir kitaplık dll 'Lerden birini bulamazsa aşağıdakine benzer bir ileti görüntülenebilir: " *Library*. dll bulunamadığı için bu uygulama başlatılamadı. Uygulamayı yeniden yüklemek bu sorunu çözebilir. "

Bu tür bir hatayı gidermek için, uygulama yükleyicinizin doğru şekilde yapılamadığını ve yeniden dağıtılabilir kitaplıkların hedef sistemde doğru bir şekilde dağıtıldığından emin olun. Daha fazla bilgi için bkz. [bir görsel C++ uygulamanın bağımlılıklarını anlama](understanding-the-dependencies-of-a-visual-cpp-application.md).

## <a name="related-topics"></a>İlgili Konular

|Başlık|Açıklama|
|-----------|-----------------|
|[Birleştirme modüllerini kullanarak yeniden dağıtma](redistributing-components-by-using-merge-modules.md)|Visual C++ Runtime kitaplıklarını%windir%\system32\ klasöründe C++ paylaşılan DLL 'Ler olarak yüklemek için Visual yeniden dağıtılabilir birleştirme modüllerinin nasıl kullanılacağını açıklar.|
|[Visual C++ ActiveX Denetimlerini Yeniden Dağıtma](redistributing-visual-cpp-activex-controls.md)|ActiveX Denetimlerini kullanan bir uygulamanın nasıl yeniden dağıtılması gerektiği açıklanmaktadır.|
|[MFC Kitaplığını Yeniden Dağıtma](redistributing-the-mfc-library.md)|MFC kullanan bir uygulamanın nasıl yeniden dağıtılacağı açıklanmaktadır.|
|[ATL uygulamasını yeniden dağıtma](redistributing-an-atl-application.md)|ATL kullanan bir uygulamanın nasıl yeniden dağıtılacağını açıklar. Visual Studio 2012 ' den itibaren, ATL için yeniden dağıtılabilir kitaplık gerekli değildir.|
|[Dağıtım Örnekleri](deployment-examples.md)|Visual C++ uygulamalarının nasıl dağıtıldığını gösteren örneklere bağlantılar verir.|
|[Masaüstü uygulamaları dağıtma](deploying-native-desktop-applications-visual-cpp.md)|Visual C++ dağıtım kavramlarını ve teknolojilerini tanıtır.|
