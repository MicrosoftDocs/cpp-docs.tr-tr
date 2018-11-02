---
title: Dağıtım Yöntemi Seçme
ms.date: 11/04/2016
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
ms.openlocfilehash: eb9b0784dc5a31accc086314e64758b5bd91033f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607655"
---
# <a name="choosing-a-deployment-method"></a>Dağıtım Yöntemi Seçme

Visual C++ uygulamanızı kendi içinde bağımsızdır ve bir kopyalama komutu kullanılarak dağıtılabilir sürece, Windows Installer dağıtımı için kullanmanızı öneririz. Windows Installer yükleme, onarım ve kaldırma işlemlerini ve ayrıca uygulama dosyalarının, bağımlılıkların ve kayıt defteri girişlerinin atomik güncelleştirilmesini destekler. 

> [!NOTE]
>  Ancak [ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment) Visual Studio'daki Visual C++ yerel uygulamalar için dağıtım mümkündür, ek adımlar gerektirir. Daha fazla bilgi için [Visual C++ uygulamaları için ClickOnce dağıtımı](../ide/clickonce-deployment-for-visual-cpp-applications.md).

## <a name="visual-c-libraries-are-shared-dlls"></a>Visual C++ Kitaplıkları Paylaşılan DLL'lerdir

Visual C++ kitaplıkları Visual Studio yükleyicisi tarafından %windir%\system32\ dizinine yüklendiğinden, bu kitaplıklara bağlı bir Visual C++ uygulaması geliştirdiğinizde uygulama beklendiği şekilde çalışacaktır. Bununla birlikte, uygulamayı Visual Studio bulunmayan bilgisayarlara dağıtmak için, uygulamayla birlikte kitaplıkların da bu bilgisayarlara yüklenmesini sağlamanızı öneririz.

## <a name="redistributing-visual-c-libraries"></a>Visual C++ Kitaplıklarını Yeniden Dağıtma

Dağıtımlarınızda, yeniden dağıtım için lisanslı herhangi bir Visual C++ kitaplığı sürümünü yeniden dağıtabilirsiniz. Bunları dağıtmanın üç yolu vardır:

- Visual C++ kitaplıklarının %windir%\system32 paylaşılan dll olarak yükleyen yeniden dağıtılabilir paketleri kullanarak merkezi dağıtım\\. (Bu klasöre yüklemek için yönetici hakları gerekir.) Uygulamanızı hedef bilgisayara yüklemeden önce yeniden dağıtılabilir paketi çalıştıran bir komut dosyası veya kurulum programı oluşturabilirsiniz. Yeniden dağıtılabilir paketler x 86, x 64 ve ARM platformları (VCRedist_x86.exe, VCRedist_x64.exe veya VCRedist_arm.exe) için kullanılabilir. Visual Studio bu paketleri % ProgramFiles (x86) %\Microsoft Visual Studio içerir `version`\VC\Redist\\`locale ID`\\. Bunları da indirebilirsiniz [Microsoft Download Center](http://go.microsoft.com/fwlink/p/?linkid=132793). (Aramak için İndirme Merkezi'nde arama kutusunu kullanın "Visual C++ yeniden dağıtılabilir paketi *Visual Studio sürümü ve güncelleştirme*" uygulamanızla uyuşan. Uygulamanızı oluşturmak için Visual Studio 2015 güncelleştirme 3 kullandıysanız, for example, ardından aramak "Visual C++ yeniden dağıtılabilir paket 2015 güncelleştirme 3".) Yeniden dağıtılabilir paketin nasıl kullanılacağı hakkında daha fazla bilgi için bkz. [izlenecek yol: bir Visual C++ Application By Using Visual C++ yeniden dağıtılabilir paketi dağıtma](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).

- Her biri yükler belirli bir Visual C++ Kitaplık %windir%\system32 paylaşılan DLL olarak birleştirme modüllerini kullanarak merkezi dağıtım\\. (Bu klasöre yüklemek için yönetici hakları gerekir.) Birleştirme modülleri uygulamanız için .msi yükleyicisinin bir parçası haline gelir. Visual C++ yeniden dağıtılabilir birleştirme modülleri \Program dosyaları (x86) \Common Files\Merge modülleri Visual Studio'da eklenir\\. Daha fazla bilgi için [yeniden dağıtma tarafından kullanarak birleştirme modülleri](../ide/redistributing-components-by-using-merge-modules.md).

- Kopyalayıp belirli Visual C++ DLL'lerini Visual Studio yüklemenizin yerel dağıtım — genellikle \Program dosyaları (x86) \Microsoft Visual Studio içinde `version`\VC\Redist\\`platform`\\`library`\—and bunları hedef bilgisayarlarda uygulama yürütülebilir olarak aynı klasöre yükleyin. Yönetici hakları olmayan kullanıcıların yükleme yapabilmesini sağlamak veya bir ağ paylaşımından çalıştırılabilen uygulamalar için bu dağıtım yöntemini kullanabilirsiniz.

Bir dağıtımı yeniden dağıtılabilir birleştirme modülleri kullanılıyorsa ve yükleme yönetici haklarına sahip olmayan bir kullanıcı tarafından çalıştırılırsa, Visual C++ DLL'leri yüklenmez ve uygulama çalışmaz. Ayrıca, kullanıcı başına esasına göre yüklemeye izin veren birleştirme modülleriyle derlenmiş uygulama yükleyicileri, kitaplıkları, tüm sistem kullanıcılarını etkileyen bir paylaşılan konuma yükler. Diğer kullanıcıları etkilemeden veya yönetici haklarına gerek duyulmadan belirli bir kullanıcının uygulama dizininde gerekli Visual C++ DLL'lerini yüklemek için yerel dağıtımı kullanabilirsiniz. Bu durum hizmet sunulabilirliği sorunları yaratabileceğinden, Visual C++ yeniden dağıtılabilir DLL'lerinin yerel dağıtımını önermiyoruz.

Visual C++ kitaplıklarının yanlış dağıtılması, onlara bağımlı olan bir uygulamanın çalıştırılması esnasında çalışma zamanı hatalarına neden olabilir. İşletim sistemi uygulamayı yüklerken, açıklanan arama düzenini kullanır. [LoadLibraryEx](http://go.microsoft.com/fwlink/p/?linkid=132792)

## <a name="dynamic-linking-is-better-than-static-linking"></a>Dinamik Bağlama Statik Bağlamadan İyidir

Visual C++ kitaplıklarını yeniden dağıtırken statik bağlamadan kaçınmanızı öneririz. Statik bağlama uygulama performansını neredeyse hiçbir zaman önemli ölçüde artırmamasına karşın, bakım uygulamalarını hemen her zaman daha pahalı kılar. Örneğin, güvenlik iyileştirmeleriyle güncelleştirilmiş bir kitaplığa statik olarak bağlı bir uygulama düşünün; uygulama yeniden derlenmediği ve yeniden dağıtılmadığı sürece bir fayda sağlayamaz. Bunun yerine, uygulamalarınızı bağlı oldukları kitaplıklar ile dinamik olarak ilişkilendirmenizi öneririz; böylece kitaplıklar dağıtıldıkları her konumda güncelleştirilebilirler.

## <a name="see-also"></a>Ayrıca Bkz.

[Masaüstü uygulamalarını dağıtma](../ide/deploying-native-desktop-applications-visual-cpp.md)<br>
[ClickOnce Güvenliği ve Dağıtımı](/visualstudio/deployment/clickonce-security-and-deployment)<br>
[Dağıtım Örnekleri](../ide/deployment-examples.md)