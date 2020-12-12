---
description: 'Hakkında daha fazla bilgi edinin: bir test makinesini hata ayıklama yürütülebiliri çalıştırmak Için hazırlama'
title: Yürütülebilir Hata Ayıklamayı Çalıştırmak için Test Makinesi Hazırlama
ms.date: 07/02/2019
helpviewer_keywords:
- debug executable, preparing a test machine to run
ms.assetid: f0400989-cc2e-4dce-9788-6bdbe91c6f5a
ms.openlocfilehash: 28bc1d328cf1ea1d7c9738012407f3190e3a65bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180012"
---
# <a name="preparing-a-test-machine-to-run-a-debug-executable"></a>Yürütülebilir Hata Ayıklamayı Çalıştırmak için Test Makinesi Hazırlama

Bir bilgisayarı, Visual C++ ile oluşturulmuş bir uygulamanın hata ayıklama sürümünü test etmek üzere hazırlamak için, uygulamanın bağımlı olduğu Visual C++ kitaplık dll 'lerinin hata ayıklama sürümlerini dağıtmanız gerekir. Hangi dll 'Lerin dağıtılması gerektiğini belirlemek için [bir Visual C++ uygulamasının bağımlılıklarını anlama](understanding-the-dependencies-of-a-visual-cpp-application.md)bölümündeki adımları izleyin. Genellikle, Visual C++ kitaplığı dll 'Lerinin hata ayıklama sürümlerinin "d" ile biten adları vardır; Örneğin, msvcr100.dll hata ayıklama sürümü msvcr100d.dll olarak adlandırılır.

> [!NOTE]
> Bir uygulamanın hata ayıklama sürümleri yeniden dağıtılabilir değildir ve Visual C++ kitaplığı dll 'Lerinin hata ayıklama sürümleri yeniden dağıtılabilir değildir. Visual Studio yüklü olmayan bir bilgisayardaki uygulamaların hata ayıklamasını ve test edilmesini sağlamak için uygulamaların hata ayıklama sürümlerini ve yalnızca diğer bilgisayarlarınıza Visual C++ dll 'Leri dağıtabilirsiniz. Daha fazla bilgi için bkz. [Visual C++ dosyalarını yeniden dağıtma](redistributing-visual-cpp-files.md).

Visual C++ kitaplığı dll 'lerinin hata ayıklama sürümlerini uygulamanın hata ayıklama sürümüyle birlikte dağıtmanın üç yolu vardır.

- Doğru kitaplık sürümü ve uygulamanızın mimarisi için birleştirme modülleri içeren bir kurulum projesi kullanarak belirli bir Visual C++ DLL 'nin hata ayıklama sürümünü%windir%\system32\ dizinine yüklemek için merkezi dağıtım kullanın. Birleştirme modülleri, \Common Files\Merge modüllerinde Program Files veya Program Files (x86) dizininde bulunur \\ . Birleştirme modülünün hata ayıklama sürümü, namefor örneğinde, Microsoft_VC110_DebugCRT_x86. msm ' de hata ayıklamıştır. Bu dağıtıma bir örnek, [bir kurulum projesi kullanarak bir Visual C++ uygulaması dağıtma Kılavuzu](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md)'nda bulunabilir.

- \Microsoft Visual Studio \<version> \Vc\redist\ Debug_NonRedist Içindeki Program Files veya Program Files (x86) dizininde bulunan dosyaları kullanarak uygulamanın yükleme dizinindeki belirli bir VISUAL C++ dll 'nin hata ayıklama sürümünü yüklemek için yerel dağıtımı kullanın \\ .

    > [!NOTE]
    >  Visual Studio 2005 veya Visual Studio 2008 kullanılarak oluşturulan uygulamanızda uzaktan hata ayıklama için başka bir bilgisayarda, Visual C++ kitaplığı dll 'lerinin hata ayıklama sürümlerini paylaşılan yan yana derlemeler olarak dağıtmanız gerekir. Bir kurulum projesi veya Windows Installer, ilgili birleştirme modüllerini yüklemek için kullanabilirsiniz.

- Proje çıkışını ve diğer dosyaları uzak bilgisayara kopyalamak için Visual Studio 'daki **Configuration Manager** iletişim kutusunda the_ **Dağıt** seçeneğini kullanın.

Visual C++ dll 'Ler yüklendikten sonra, bir ağ paylaşımında uzaktan hata ayıklayıcı çalıştırabilirsiniz. Uzaktan hata ayıklama hakkında daha fazla bilgi için bkz. [Uzaktan hata ayıklama](/visualstudio/debugger/remote-debugging).

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ üzerinde Dağıtım](deployment-in-visual-cpp.md)<br>
[Komut satırı seçeneklerini Windows Installer](/windows/win32/Msi/command-line-options)<br>
[Dağıtım örnekleri](deployment-examples.md)<br>
[Uzaktan hata ayıklama](/visualstudio/debugger/remote-debugging)
