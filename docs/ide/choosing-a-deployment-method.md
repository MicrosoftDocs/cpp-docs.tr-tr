---
title: "Dağıtım yöntemi seçme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4e4336f200f736ea7656af11c7c7c43ca32f27f9
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="choosing-a-deployment-method"></a>Dağıtım Yöntemi Seçme
Visual C++ uygulamanız kendi içinde yer alan ve bir kopya komutu kullanılarak dağıtılabilir sürece, Windows Installer dağıtımı için kullanmanızı öneririz. Windows Installer yükleme, onarım ve kaldırma işlemlerini ve ayrıca uygulama dosyalarının, bağımlılıkların ve kayıt defteri girişlerinin atomik güncelleştirilmesini destekler.   
  
> [!NOTE]
>  Ancak [ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment) dağıtım Visual C++ yerel uygulamalar için Visual Studio'da mümkündür, ek adımlar gerektirir. Daha fazla bilgi için bkz: [Visual C++ uygulamaları için ClickOnce dağıtımı](../ide/clickonce-deployment-for-visual-cpp-applications.md).  
  
## <a name="visual-c-libraries-are-shared-dlls"></a>Visual C++ Kitaplıkları Paylaşılan DLL'lerdir  
 Visual C++ kitaplıkları Visual Studio yükleyicisi tarafından %windir%\system32\ dizinine yüklendiğinden, bu kitaplıklara bağlı bir Visual C++ uygulaması geliştirdiğinizde uygulama beklendiği şekilde çalışacaktır. Bununla birlikte, uygulamayı Visual Studio bulunmayan bilgisayarlara dağıtmak için, uygulamayla birlikte kitaplıkların da bu bilgisayarlara yüklenmesini sağlamanızı öneririz.  
  
## <a name="redistributing-visual-c-libraries"></a>Visual C++ Kitaplıklarını Yeniden Dağıtma  
 Dağıtımlarınızda, yeniden dağıtım için lisanslı herhangi bir Visual C++ kitaplığı sürümünü yeniden dağıtabilirsiniz. Bunları dağıtmanın üç yolu vardır:  
  
-   Visual C++ kitaplıkları paylaşılan DLL'ler %windir%\system32 olarak yükleyen yeniden dağıtılabilir paketleri kullanılarak merkezi dağıtım\\. (Bu klasöre yüklemek için yönetici hakları gerekir.) Uygulamanızı hedef bilgisayara yüklemeden önce yeniden dağıtılabilir paketi çalıştıran bir komut dosyası veya kurulum programı oluşturabilirsiniz. Yeniden dağıtılabilir paketler x 86, x 64 ve ARM platformları (VCRedist_x86.exe, VCRedist_x64.exe veya VCRedist_arm.exe) için kullanılabilir. Visual Studio % ProgramFiles (x86) %\Microsoft Visual Studio bu paketleri içerir `version`\VC\Redist\\`locale ID`\\. Ayrıca bunları indirebilirsiniz [Microsoft Download Center](http://go.microsoft.com/fwlink/p/?linkid=132793). (İndirme Merkezi'nde, arama "Visual C++ yeniden dağıtılabilir paketi *Visual Studio sürümü ve güncelleştirme*" uygulamanızı eşleşir. Örneğin, uygulamanızı derlemek için Visual Studio 2012 güncelleştirmesi 4'ü kullandıysanız, "Visual C++ Yeniden Dağıtılabilir Paketi 2012 güncelleştirme 4" öğesini arayın.) Yeniden dağıtılabilir paketi kullanma hakkında daha fazla bilgi için bkz: [izlenecek yol: Visual C++ uygulaması tarafından kullanarak bir Visual C++ yeniden dağıtılabilir paketi dağıtma](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).  
  
-   Her biri belirli bir Visual C++ Kitaplık olarak yükler %windir%\system32 paylaşılan DLL'de birleştirme modüllerini kullanarak merkezi dağıtım\\. (Bu klasöre yüklemek için yönetici hakları gerekir.) Birleştirme modülleri uygulamanız için .msi yükleyicisinin bir parçası haline gelir. Visual C++ yeniden dağıtılabilir birleştirme modülleri yer alan Visual Studio'da \Program dosyaları (x86) \Common Files\Merge modülleri\\. Daha fazla bilgi için bkz: [yeniden dağıtma tarafından kullanarak birleştirme modülleri](../ide/redistributing-components-by-using-merge-modules.md).  
  
-   İçinde kopyaladığınız belirli Visual C++ DLL'leri Visual Studio yüklemenizin yerel dağıtım — genellikle \Program Files (x86) \Microsoft Visual Studio içinde `version`\VC\Redist\\`platform`\\`library`\—and bunları, yürütülebilir uygulama ile aynı klasörde hedef bilgisayarlara yükleyin. Yönetici hakları olmayan kullanıcıların yükleme yapabilmesini sağlamak veya bir ağ paylaşımından çalıştırılabilen uygulamalar için bu dağıtım yöntemini kullanabilirsiniz.  
  
 Bir dağıtımı yeniden dağıtılabilir birleştirme modüllerini kullanır ve bir yükleme yönetici haklarına sahip olmayan bir kullanıcı tarafından çalıştırırsanız, Visual C++ DLL'ler yüklü değil ve uygulama çalışmaz. Ayrıca, kullanıcı başına esasına göre yüklemeye izin veren birleştirme modülleriyle derlenmiş uygulama yükleyicileri, kitaplıkları, tüm sistem kullanıcılarını etkileyen bir paylaşılan konuma yükler. Diğer kullanıcıları etkileyen veya yönetici hakları gerektiren belirli bir kullanıcının uygulama dizininde gerekli Visual C++ DLL'leri yüklemek için yerel dağıtım kullanabilirsiniz. Bu bakım yapılabilirliğini sorunları oluşturduğundan, Visual C++ yeniden dağıtılabilir DLL'leri yerel dağıtımını önermiyoruz.  
  
 Visual C++ kitaplıklarının yanlış dağıtılması, onlara bağımlı olan bir uygulamanın çalıştırılması esnasında çalışma zamanı hatalarına neden olabilir. İşletim sistemini uygulama yüklendiğinde açıklanan arama sırasını kullanır [LoadLibraryEx](http://go.microsoft.com/fwlink/p/?linkid=132792)  
  
## <a name="dynamic-linking-is-better-than-static-linking"></a>Dinamik Bağlama Statik Bağlamadan İyidir  
 Visual C++ kitaplıkları yeniden dağıtırken statik bağlama kaçınmanızı öneririz. Statik bağlama uygulama performansını neredeyse hiçbir zaman önemli ölçüde artırmamasına karşın, bakım uygulamalarını hemen her zaman daha pahalı kılar. Örneğin, güvenlik iyileştirmeleriyle güncelleştirilmiş bir kitaplığa statik olarak bağlı bir uygulama düşünün; uygulama yeniden derlenmediği ve yeniden dağıtılmadığı sürece bir fayda sağlayamaz. Bunun yerine, uygulamalarınızı bağlı oldukları kitaplıklar ile dinamik olarak ilişkilendirmenizi öneririz; böylece kitaplıklar dağıtıldıkları her konumda güncelleştirilebilirler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Masaüstü uygulamaları dağıtma](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [ClickOnce güvenliği ve dağıtımı](/visualstudio/deployment/clickonce-security-and-deployment)   
 [Dağıtım Örnekleri](../ide/deployment-examples.md)