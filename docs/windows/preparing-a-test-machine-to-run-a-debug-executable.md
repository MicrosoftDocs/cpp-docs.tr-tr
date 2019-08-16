---
title: Yürütülebilir Hata Ayıklamayı Çalıştırmak için Test Makinesi Hazırlama
ms.date: 07/02/2019
helpviewer_keywords:
- debug executable, preparing a test machine to run
ms.assetid: f0400989-cc2e-4dce-9788-6bdbe91c6f5a
ms.openlocfilehash: ae751b1632473fa316c7965bc751e91b782a89ea
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513674"
---
# <a name="preparing-a-test-machine-to-run-a-debug-executable"></a>Yürütülebilir Hata Ayıklamayı Çalıştırmak için Test Makinesi Hazırlama

Bir bilgisayarı Görselle C++oluşturulmuş bir uygulamanın hata ayıklama sürümünü test etmek üzere hazırlamak için, uygulamanın bağımlı olduğu görsel C++ kitaplık dll 'lerinin hata ayıklama sürümlerini dağıtmanız gerekir. Hangi dll 'Lerin dağıtılması gerektiğini belirlemek için, [bir görsel C++ uygulamanın bağımlılıklarını anlama başlıklı](understanding-the-dependencies-of-a-visual-cpp-application.md)adımları izleyin. Genellikle, Visual C++ Library DLL 'lerinin hata ayıklama sürümlerinin "d" ile biten adları vardır; Örneğin, Msvcr100. dll ' nin hata ayıklama sürümü msvcr100d. dll olarak adlandırılır.

> [!NOTE]
>  Uygulamanın hata ayıklama sürümleri yeniden dağıtılabilir değildir ve Visual C++ Library DLL 'lerinin hata ayıklama sürümleri yeniden dağıtılabilir değildir. Visual Studio 'nun yüklü olmadığı bir bilgisayardaki uygulamaların hata C++ ayıklamasını ve test edilmesini sağlamak amacıyla, uygulamaların ve Visual dll 'lerinin hata ayıklama sürümlerini yalnızca diğer bilgisayarlarınıza dağıtabilirsiniz. Daha fazla bilgi için bkz. [görsel C++ dosyaları yeniden dağıtma](redistributing-visual-cpp-files.md).

Visual C++ Library DLL 'lerinin hata ayıklama sürümlerini bir uygulamanın hata ayıklama sürümüyle birlikte dağıtmanın üç yolu vardır.

- Doğru kitaplık sürümü ve uygulamanızın mimarisi için birleştirme modülleri içeren bir kurulum C++ projesi kullanarak belirli bir Visual dll 'nin hata ayıklama sürümünü%windir%\system32\ dizinine yüklemek için merkezi dağıtım kullanın. Birleştirme modülleri, \Common Files\Merge modüllerinde\\Program Files veya Program Files (x86) dizininde bulunur. Birleştirme modülünün hata ayıklama sürümünde, namefor örneğinde, Microsoft_VC110_DebugCRT_x86. msm dosyasında hata ayıklama vardır. Bu dağıtıma [bir örnek, izlenecek yol: Bir kurulum projesi C++ ](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md)kullanarak görsel uygulama dağıtma.

- Visual Studio \< 'da Program Files veya Program Files (x86) dizininde C++ belirtilen dosyaları kullanarak uygulamanın yükleme dizinindeki belirli bir Visual dll 'nin hata ayıklama sürümünü yüklemek için yerel dağıtımı kullanın sürüm > \Vc\redist\debug_nonredıst\\.

    > [!NOTE]
    >  Visual Studio 2005 veya Visual Studio 2008 kullanılarak oluşturulan uygulamanızda uzaktan hata ayıklama için başka bir bilgisayarda, Visual C++ Library DLL 'lerinin hata ayıklama sürümlerini paylaşılan yan yana derlemeler olarak dağıtmanız gerekir. Bir kurulum projesi veya Windows Installer, ilgili birleştirme modüllerini yüklemek için kullanabilirsiniz.

- Proje çıkışını ve diğer dosyaları uzak bilgisayara kopyalamak için Visual Studio 'daki **Configuration Manager** iletişim kutusunda the_**Deploy** seçeneğini kullanın.

Visual C++ dll 'ler yüklendikten sonra bir ağ paylaşımında uzaktan hata ayıklayıcı çalıştırabilirsiniz. Uzaktan hata ayıklama hakkında daha fazla bilgi için bkz. [Uzaktan hata ayıklama](/visualstudio/debugger/remote-debugging).

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ üzerinde Dağıtım](deployment-in-visual-cpp.md)<br>
[Komut satırı seçeneklerini Windows Installer](/windows/win32/Msi/command-line-options)<br>
[Dağıtım Örnekleri](deployment-examples.md)<br>
[Uzaktan Hata Ayıklama](/visualstudio/debugger/remote-debugging)
