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
ms.openlocfilehash: e2281effaa94c32454e88100c8b7020961f748d9
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514835"
---
# <a name="choosing-a-deployment-method"></a>Dağıtım Yöntemi Seçme

Görsel C++ uygulamanız kendi içinde ve bir Copy komutu kullanılarak dağıtılırsa, dağıtım için Windows Installer kullanmanızı öneririz. Windows Installer yükleme, onarım ve kaldırma işlemlerini ve ayrıca uygulama dosyalarının, bağımlılıkların ve kayıt defteri girişlerinin atomik güncelleştirilmesini destekler.

> [!NOTE]
>  Visual [](/visualstudio/deployment/clickonce-security-and-deployment) Studio 'da Visual C++ Native uygulamalar için ClickOnce dağıtımı mümkün olsa da, ek adımlar gerektirir. Daha fazla bilgi için bkz. [Visual C++ uygulamaları için ClickOnce dağıtımı](clickonce-deployment-for-visual-cpp-applications.md).

## <a name="visual-c-libraries-are-shared-dlls"></a>Visual C++ Kitaplıkları Paylaşılan DLL'lerdir

Visual C++ kitaplıkları Visual Studio yükleyicisi tarafından %windir%\system32\ dizinine yüklendiğinden, bu kitaplıklara bağlı bir Visual C++ uygulaması geliştirdiğinizde uygulama beklendiği şekilde çalışacaktır. Bununla birlikte, uygulamayı Visual Studio bulunmayan bilgisayarlara dağıtmak için, uygulamayla birlikte kitaplıkların da bu bilgisayarlara yüklenmesini sağlamanızı öneririz.

## <a name="redistributing-visual-c-libraries"></a>Visual C++ Kitaplıklarını Yeniden Dağıtma

Dağıtımlarınızda, yeniden dağıtım için lisanslı herhangi bir Visual C++ kitaplığı sürümünü yeniden dağıtabilirsiniz. Bunları dağıtmanın üç yolu vardır:

- Visual C++ kitaplıklarını%Windir%\System32\\içinde paylaşılan DLL 'ler olarak yükleyecek olan yeniden dağıtılabilir paketleri kullanarak merkezi dağıtım. (Bu klasöre yüklemek için yönetici hakları gerekir.) Uygulamanızı hedef bilgisayara yüklemeden önce yeniden dağıtılabilir paketi çalıştıran bir komut dosyası veya kurulum programı oluşturabilirsiniz. Yeniden dağıtılabilir paketler x 86, x 64 ve ARM platformları (VCRedist_x86.exe, VCRedist_x64.exe veya VCRedist_arm.exe) için kullanılabilir. Visual Studio,% ProgramFiles (x86)% \ `version`Microsoft Visual Studio \vc\redist\\`locale ID`\\içindeki paketleri içerir. Bunları [Microsoft Indirme merkezi](https://www.microsoft.com/download)' nden de indirebilirsiniz. (Uygulama ile eşleşen "Visual C++ yeniden dağıtılabilir paket *Visual Studio sürümünü ve güncelleştirmesini*" aramak için indirme merkezi 'ndeki arama kutusunu kullanın. Örneğin, uygulamanızı derlemek için Visual Studio 2015 güncelleştirme 3 kullandıysanız, "Visual C++ yeniden dağıtılabilir paket 2015 güncelleştirme 3" ifadesini aratın.) Yeniden dağıtılabilir paket kullanma hakkında daha fazla bilgi için bkz [. İzlenecek yol: Görsel C++ C++ yeniden dağıtılabilir paketi](deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md)kullanarak görsel uygulama dağıtma.

- Her biri özel bir görsel C++ kitaplığı%windir%\System32\\içinde paylaşılan DLL olarak yüklediği birleştirme modüllerini kullanarak merkezi dağıtım. (Bu klasöre yüklemek için yönetici hakları gerekir.) Birleştirme modülleri uygulamanız için .msi yükleyicisinin bir parçası haline gelir. Visual C++ yeniden dağıtılabilir birleştirme modülleri, Visual Studio 'Da \Program Files (x86) \Common Files\merge modüllerinde\\bulunur. Daha fazla bilgi için bkz. [birleştirme modüllerini kullanarak yeniden dağıtma](redistributing-components-by-using-merge-modules.md).

- C++ Visual Studio yüklemenizin belirli görsel dll 'lerini (genellikle \Program Files (x86) \Microsoft Visual Studio `version`\vc\redist\\`platform`\\`library`\ içinde kopyaladığınız yerel dağıtım. — ve bunları hedef bilgisayarlara uygulama yürütülebiliri ile aynı klasöre yükler. Yönetici hakları olmayan kullanıcıların yükleme yapabilmesini sağlamak veya bir ağ paylaşımından çalıştırılabilen uygulamalar için bu dağıtım yöntemini kullanabilirsiniz.

Bir dağıtım yeniden dağıtılabilir birleştirme modülleri kullanıyorsa ve bir yükleme, yönetici haklarına sahip olmayan bir kullanıcı tarafından çalıştırıldığında, görsel C++ dll 'ler yüklenmez ve uygulama çalışmaz. Ayrıca, kullanıcı başına esasına göre yüklemeye izin veren birleştirme modülleriyle derlenmiş uygulama yükleyicileri, kitaplıkları, tüm sistem kullanıcılarını etkileyen bir paylaşılan konuma yükler. Gerekli görsel C++ dll 'leri, diğer kullanıcıları etkilemeden veya yönetici hakları gerektirmeden, belirli bir kullanıcının uygulamasının dizinine yüklemek için yerel dağıtım kullanabilirsiniz. Bu, bakım sorunları oluşturabileceğinden, Visual C++ yeniden dağıtılabilir DLL 'lerin yerel dağıtımını önermiyoruz.

Visual C++ kitaplıklarının yanlış dağıtılması, onlara bağımlı olan bir uygulamanın çalıştırılması esnasında çalışma zamanı hatalarına neden olabilir. İşletim sistemi uygulamayı yüklediğinde, [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)bölümünde açıklanan arama sırasını kullanır.

## <a name="dynamic-linking-is-better-than-static-linking"></a>Dinamik Bağlama Statik Bağlamadan İyidir

Görsel C++ kitaplıkları yeniden dağıttığınızda statik bağlama yapmaktan kaçınmanızı öneririz. Statik bağlama uygulama performansını neredeyse hiçbir zaman önemli ölçüde artırmamasına karşın, bakım uygulamalarını hemen her zaman daha pahalı kılar. Örneğin, güvenlik iyileştirmeleriyle güncelleştirilmiş bir kitaplığa statik olarak bağlı bir uygulama düşünün; uygulama yeniden derlenmediği ve yeniden dağıtılmadığı sürece bir fayda sağlayamaz. Bunun yerine, uygulamalarınızı bağlı oldukları kitaplıklar ile dinamik olarak ilişkilendirmenizi öneririz; böylece kitaplıklar dağıtıldıkları her konumda güncelleştirilebilirler.

## <a name="see-also"></a>Ayrıca bkz.

[Masaüstü uygulamaları dağıtma](deploying-native-desktop-applications-visual-cpp.md)<br>
[ClickOnce Güvenliği ve Dağıtımı](/visualstudio/deployment/clickonce-security-and-deployment)<br>
[Dağıtım Örnekleri](deployment-examples.md)
