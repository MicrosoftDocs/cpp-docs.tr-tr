---
title: Dağıtım Yöntemi Seçme
ms.date: 03/14/2019
helpviewer_keywords:
- redistributing DLLs
- manifests [C++]
- DLLs [C++], redistributing
- side-by-side assemblies [C++]
- dynamic linking [C++]
- application deployment [C++], methods
- deploying applications [C++], methods
- static linking [C++]
- libraries [C++], application deployment issues
ms.assetid: fd8eb956-f4a0-4ffb-b401-328c73e66986
ms.openlocfilehash: 633b76458fdc24ef9ba551d8209c5c99720df37e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377402"
---
# <a name="choosing-a-deployment-method"></a>Dağıtım Yöntemi Seçme

Visual C++ uygulamanız bağımsız değilse ve bir kopya komutu kullanılarak dağıtılamıyorsa, dağıtım için Windows Installer'ı kullanmanızı öneririz. Windows Installer yükleme, onarım ve kaldırma işlemlerini ve ayrıca uygulama dosyalarının, bağımlılıkların ve kayıt defteri girişlerinin atomik güncelleştirilmesini destekler. 

> [!NOTE]
> Visual Studio'da Visual C++ yerel uygulamaları için [ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment) dağıtımı mümkün olsa da, ek adımlar gerekir. Daha fazla bilgi için [Visual C++ Uygulamaları için ClickOnce Dağıtım'a](clickonce-deployment-for-visual-cpp-applications.md)bakın.

## <a name="visual-c-libraries-are-shared-dlls"></a>Visual C++ Kitaplıkları Paylaşılan DLL'lerdir

Visual C++ kitaplıkları Visual Studio yükleyicisi tarafından %windir%\system32\ dizinine yüklendiğinden, bu kitaplıklara bağlı bir Visual C++ uygulaması geliştirdiğinizde uygulama beklendiği şekilde çalışacaktır. Bununla birlikte, uygulamayı Visual Studio bulunmayan bilgisayarlara dağıtmak için, uygulamayla birlikte kitaplıkların da bu bilgisayarlara yüklenmesini sağlamanızı öneririz.

## <a name="redistributing-visual-c-libraries"></a>Visual C++ Kitaplıklarını Yeniden Dağıtma

Dağıtımlarınızda, yeniden dağıtım için lisanslı herhangi bir Visual C++ kitaplığı sürümünü yeniden dağıtabilirsiniz. Bunları dağıtmanın üç yolu vardır:

- Visual C++ kitaplıklarını %windir%\system32'de\\paylaşılan DL'ler olarak yükleyen yeniden dağıtılabilir paketler kullanarak merkezi dağıtım. (Bu klasöre yükleme yönetici hakları gerektirir.) Uygulamanızı hedef bilgisayara yüklemeden önce yeniden dağıtılabilir paketi çalıştıran bir komut dosyası veya kurulum programı oluşturabilirsiniz. Yeniden dağıtılabilir paketler x 86, x 64 ve ARM platformları (VCRedist_x86.exe, VCRedist_x64.exe veya VCRedist_arm.exe) için kullanılabilir. Visual Studio bu paketleri %ProgramFiles(x86)%\Microsoft `version`Visual Studio\\`locale ID`\\\VC\Redist'te içerir. Ayrıca [Microsoft Download Center'dan](https://www.microsoft.com/download)da indirebilirsiniz. (Uygulamanızla eşleşen "Visual C++ Yeniden Dağıtılabilir Paket Görsel Stüdyosu sürümünü ve *güncellemeyi*" aramak için İndirme Merkezi'ndeki arama kutusunu kullanın. Örneğin, uygulamanızı oluşturmak için Visual Studio 2015 update 3'u kullandıysanız, "Visual C++ Yeniden Dağıtılabilir Paket 2015 güncelleştirmesi 3" aramasını yapın.) Yeniden dağıtılabilir bir paketin nasıl kullanılacağı hakkında bilgi için Bkz. [Walkthrough: Visual C++ Yeniden Dağıtılabilir Paketi Kullanarak Visual C++ Uygulamasını Dağıtma](deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).

- Her biri %windir%\system32'de\\paylaşılan bir DLL olarak belirli bir Visual C++ kitaplığını yükleyen birleştirme modülleri kullanarak merkezi dağıtım. (Bu klasöre yükleme yönetici hakları gerektirir.) Birleştirme modülleri, uygulamanız için .msi yükleyici dosyasının bir parçası haline gelir. Visual C++ yeniden dağıtılabilir birleştirme modülleri Visual Studio'da, \Program Dosyaları 'nda (x86)\Ortak Dosyalar\Birleştirme Modülleri\\dahildir. Daha fazla bilgi için, [Birleştirme Modüllerini Kullanarak Yeniden Dağıtma'ya](redistributing-components-by-using-merge-modules.md)bakın.

- Visual Studio yüklemenizden belirli Visual C++ DLL'leri kopyaladığınızı ve genellikle \Program Dosyaları (x86)\Microsoft\\`platform`\\`library`Visual Studio `version`\VC\Redist \— ve bunları yürütülebilir uygulamayla aynı klasördeki hedef bilgisayarlara yükleyin. Yönetici hakları olmayan kullanıcıların yükleme yapabilmesini sağlamak veya bir ağ paylaşımından çalıştırılabilen uygulamalar için bu dağıtım yöntemini kullanabilirsiniz.

Dağıtım yeniden dağıtılabilir birleştirme modülleri kullanırsa ve yükleme yönetim hakları olmayan bir kullanıcı tarafından çalıştırılırsa, Visual C++ DLL'ler yüklenmez ve uygulama çalışmaz. Ayrıca, kullanıcı başına esasına göre yüklemeye izin veren birleştirme modülleriyle derlenmiş uygulama yükleyicileri, kitaplıkları, tüm sistem kullanıcılarını etkileyen bir paylaşılan konuma yükler. Diğer kullanıcıları etkilemeden veya yönetici hakları gerektirmeden, belirli bir kullanıcının uygulamasının dizinine gerekli Visual C++ DLL'leri yüklemek için yerel dağıtımı kullanabilirsiniz. Bu, hizmet verebilirlik sorunları oluşturabileceğinden, Visual C++ yeniden dağıtılabilir DL'lerin yerel olarak dağıtılmasını önermiyoruz.

Visual C++ kitaplıklarının yanlış dağıtılması, onlara bağımlı olan bir uygulamanın çalıştırılması esnasında çalışma zamanı hatalarına neden olabilir. İşletim sistemi uygulamayı yüklerken, [LoadLibraryEx'te](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)açıklanan arama sırasını kullanır.

## <a name="dynamic-linking-is-better-than-static-linking"></a>Dinamik Bağlama Statik Bağlamadan İyidir

Visual C++ kitaplıklarını yeniden dağıttığınızda statik bağlantıdan kaçınmanızı öneririz. Statik bağlama uygulama performansını neredeyse hiçbir zaman önemli ölçüde artırmamasına karşın, bakım uygulamalarını hemen her zaman daha pahalı kılar. Örneğin, güvenlik iyileştirmeleriyle güncelleştirilmiş bir kitaplığa statik olarak bağlı bir uygulama düşünün; uygulama yeniden derlenmediği ve yeniden dağıtılmadığı sürece bir fayda sağlayamaz. Bunun yerine, uygulamalarınızı bağlı oldukları kitaplıklar ile dinamik olarak ilişkilendirmenizi öneririz; böylece kitaplıklar dağıtıldıkları her konumda güncelleştirilebilirler.

## <a name="see-also"></a>Ayrıca bkz.

[Masaüstü Uygulamalarını Dağıtma](deploying-native-desktop-applications-visual-cpp.md)<br>
[ClickOnce Güvenliği ve Dağıtımı](/visualstudio/deployment/clickonce-security-and-deployment)<br>
[Dağıtım Örnekleri](deployment-examples.md)
