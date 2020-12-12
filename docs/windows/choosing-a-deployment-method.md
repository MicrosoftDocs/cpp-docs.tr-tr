---
description: 'Hakkında daha fazla bilgi edinin: dağıtım yöntemi seçme'
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
ms.openlocfilehash: 9b1ae942ff189bf9073059a55a195860bd3efc26
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327180"
---
# <a name="choosing-a-deployment-method"></a>Dağıtım Yöntemi Seçme

Visual C++ uygulamanız kendi içinde ve bir kopyalama komutu kullanılarak dağıtılırsa, dağıtım için Windows Installer kullanmanızı öneririz. Windows Installer yükleme, onarım ve kaldırma işlemlerini ve ayrıca uygulama dosyalarının, bağımlılıkların ve kayıt defteri girişlerinin atomik güncelleştirilmesini destekler. 

> [!NOTE]
> Visual C++ yerel uygulamalar için [ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment) dağıtımı, Visual Studio 'da mümkün olsa da, ek adımlar gerektirir. Daha fazla bilgi için bkz. [Visual C++ uygulamalar Için ClickOnce dağıtımı](clickonce-deployment-for-visual-cpp-applications.md).

## <a name="visual-c-libraries-are-shared-dlls"></a>Visual C++ Kitaplıkları Paylaşılan DLL'lerdir

Visual C++ kitaplıkları Visual Studio yükleyicisi tarafından %windir%\system32\ dizinine yüklendiğinden, bu kitaplıklara bağlı bir Visual C++ uygulaması geliştirdiğinizde uygulama beklendiği şekilde çalışacaktır. Bununla birlikte, uygulamayı Visual Studio bulunmayan bilgisayarlara dağıtmak için, uygulamayla birlikte kitaplıkların da bu bilgisayarlara yüklenmesini sağlamanızı öneririz.

## <a name="redistributing-visual-c-libraries"></a>Visual C++ Kitaplıklarını Yeniden Dağıtma

Dağıtımlarınızda, yeniden dağıtım için lisanslı herhangi bir Visual C++ kitaplığı sürümünü yeniden dağıtabilirsiniz. Bunları dağıtmanın üç yolu vardır:

- Visual C++ kitaplıklarını%Windir%\System32 içinde paylaşılan DLL 'Ler olarak yükleyecek olan yeniden dağıtılabilir paketleri kullanarak merkezi dağıtım \\ . (Bu klasöre yüklemek için yönetici hakları gerekir.) Uygulamanızı hedef bilgisayara yüklemeden önce yeniden dağıtılabilir paketi çalıştıran bir betik veya Kurulum programı oluşturabilirsiniz. Yeniden dağıtılabilir paketler x 86, x 64 ve ARM platformları (VCRedist_x86.exe, VCRedist_x64.exe veya VCRedist_arm.exe) için kullanılabilir. Visual Studio,% ProgramFiles (x86)% \ Microsoft Visual Studio `version` \Vc\redist içindeki paketleri içerir \\ `locale ID` \\ . Bunları [Microsoft Indirme merkezi](https://www.microsoft.com/download)' nden de indirebilirsiniz. (Uygulama ile eşleşen "Visual C++ yeniden dağıtılabilir paket *Visual Studio sürümü ve güncelleştirmesi*" için arama yapmak üzere indirme merkezi 'ndeki arama kutusunu kullanın. Örneğin, uygulamanızı derlemek için Visual Studio 2015 güncelleştirme 3 ' ü kullandıysanız, "Visual C++ yeniden dağıtılabilir paket 2015 güncelleştirme 3" aratın. Yeniden dağıtılabilir paket kullanma hakkında daha fazla bilgi için bkz. [Walkthrough: Visual C++ yeniden dağıtılabilir paketini kullanarak Visual C++ uygulaması dağıtma](deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).

- Her biri belirli bir Visual C++ kitaplığını%Windir%\System32 içinde paylaşılan DLL olarak yüklediği birleştirme modüllerini kullanarak merkezi dağıtım \\ . (Bu klasöre yüklemek için yönetici hakları gerekir.) Birleştirme modülleri, uygulamanız için. msi yükleyici dosyasının bir parçası haline gelir. Visual C++ yeniden dağıtılabilir birleştirme modülleri, Visual Studio 'da \Program Files (x86) \Common Files\Merge modüllerine dahil edilmiştir \\ . Daha fazla bilgi için bkz. [birleştirme modüllerini kullanarak yeniden dağıtma](redistributing-components-by-using-merge-modules.md).

- Visual Studio yüklemenizden (genellikle \Program Files (x86) \Microsoft Visual Studio \vc\redist \ içinde) özel Visual C++ dll 'leri kopyaladığınız yerel dağıtım `version` \\ `platform` \\ `library` ve bunları hedef bilgisayarlara uygulama yürütülebiliri ile aynı klasörde yükleme. Yönetici hakları olmayan kullanıcıların yükleme yapabilmesini sağlamak veya bir ağ paylaşımından çalıştırılabilen uygulamalar için bu dağıtım yöntemini kullanabilirsiniz.

Bir dağıtım yeniden dağıtılabilir birleştirme modülleri kullanıyorsa ve bir yükleme, yönetici haklarına sahip olmayan bir kullanıcı tarafından çalıştırıldığında, Visual C++ dll 'Ler yüklenmez ve uygulama çalışmaz. Ayrıca, kullanıcı başına esasına göre yüklemeye izin veren birleştirme modülleriyle derlenmiş uygulama yükleyicileri, kitaplıkları, tüm sistem kullanıcılarını etkileyen bir paylaşılan konuma yükler. Gerekli Visual C++ dll 'Leri, diğer kullanıcıları etkilemeden veya yönetici hakları isteyerek belirli bir kullanıcının uygulamasının dizinine yüklemek için yerel dağıtım kullanabilirsiniz. Bu, bakım sorunları oluşturabileceğinden, Visual C++ yeniden dağıtılabilir DLL 'lerin yerel dağıtımını önermiyoruz.

Visual C++ kitaplıklarının yanlış dağıtılması, onlara bağımlı olan bir uygulamanın çalıştırılması esnasında çalışma zamanı hatalarına neden olabilir. İşletim sistemi uygulamayı yüklediğinde, [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)bölümünde açıklanan arama sırasını kullanır.

## <a name="dynamic-linking-is-better-than-static-linking"></a>Dinamik Bağlama Statik Bağlamadan İyidir

Visual C++ kitaplıklarını yeniden dağıttığınızda statik bağlama yapmaktan kaçınmanızı öneririz. Statik bağlama uygulama performansını neredeyse hiçbir zaman önemli ölçüde artırmamasına karşın, bakım uygulamalarını hemen her zaman daha pahalı kılar. Örneğin, güvenlik iyileştirmeleriyle güncelleştirilmiş bir kitaplığa statik olarak bağlı bir uygulama düşünün; uygulama yeniden derlenmediği ve yeniden dağıtılmadığı sürece bir fayda sağlayamaz. Bunun yerine, uygulamalarınızı bağlı oldukları kitaplıklar ile dinamik olarak ilişkilendirmenizi öneririz; böylece kitaplıklar dağıtıldıkları her konumda güncelleştirilebilirler.

## <a name="see-also"></a>Ayrıca bkz.

[Masaüstü uygulamaları dağıtma](deploying-native-desktop-applications-visual-cpp.md)<br>
[ClickOnce güvenliği ve dağıtımı](/visualstudio/deployment/clickonce-security-and-deployment)<br>
[Dağıtım örnekleri](deployment-examples.md)
