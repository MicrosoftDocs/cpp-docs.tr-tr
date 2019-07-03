---
title: Yürütülebilir Hata Ayıklamayı Çalıştırmak için Test Makinesi Hazırlama
ms.date: 07/02/2019
helpviewer_keywords:
- debug executable, preparing a test machine to run
ms.assetid: f0400989-cc2e-4dce-9788-6bdbe91c6f5a
ms.openlocfilehash: 87d2bf434aef3a85bf7fa19f5886bec106515809
ms.sourcegitcommit: 9b904e490b1e262293a602bd1291a8f3045e755b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2019
ms.locfileid: "67552336"
---
# <a name="preparing-a-test-machine-to-run-a-debug-executable"></a>Yürütülebilir Hata Ayıklamayı Çalıştırmak için Test Makinesi Hazırlama

Visual C++ ile oluşturulan bir uygulamanın hata ayıklama sürümü test etmek için bir bilgisayarı hazırlamak için uygulamanın bağımlı Visual C++ Kitaplık DLL'lerin hata ayıklama sürümlerini dağıtmak zorunda. DLL'leri dağıtılacak olan belirlemek için adımları izleyin. [Visual C++ uygulaması bağımlılıklarını anlama](understanding-the-dependencies-of-a-visual-cpp-application.md). Genellikle, biten "d"; Visual C++ Kitaplık DLL'lerin hata ayıklama sürümlerine sahip Örneğin, hata ayıklama sürümünü msvcr100.DLL'i tekrar msvcr100d.dll olarak adlandırılır.

> [!NOTE]
>  Uygulama hata ayıklama sürümleri yeniden dağıtılamaz ve Visual C++ Kitaplık DLL'lerin hata ayıklama sürümleri yeniden dağıtılamaz. Uygulamalar ve Visual C++ DLL'lerini hata ayıklama sürümleri, hata ayıklama ve Visual Studio yüklü olmayan bir bilgisayarda test etme amacına yalnızca, diğer bilgisayarlara dağıtabilir. Daha fazla bilgi için [Visual C++ dosyalarını yeniden dağıtma](redistributing-visual-cpp-files.md).

Bir uygulamanın hata ayıklama sürümü ile birlikte Visual C++ Kitaplık DLL'lerin hata ayıklama sürümleri dağıtmanın üç yolu vardır.

- Belirli bir görsel hata ayıklama sürümünü yüklemek için merkezi dağıtım kullanmaktadır C++ DLL içeren Birleştirme modülleri için doğru kitaplık sürümü ve mimarisi, uygulamanızın Kurulum projesi kullanarak %windir%\system32\ dizinine. Birleştirme modülleri, Program dosyaları veya Program dosyaları (x86) \Common modülleri dizinde bulunur\\. Birleştirme modülü hata ayıklama sürümünü hata ayıklama namefor örnekte, Microsoft_VC110_DebugCRT_x86.msm vardır. Bu dağıtım örneği bulunabilir [izlenecek yol: Bir kurulum projesi kullanarak Visual C++ uygulamasını dağıtma](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).

- Belirli bir görsel hata ayıklama sürümünü yüklemek için yerel dağıtım kullanan C++ Program dosyaları veya Program dosyaları (x86) \Microsoft Visual Studio dizininde sağlanan dosyalarını kullanarak uygulama yükleme dizinindeki DLL'de \< Sürüm > \VC\redist\Debug_NonRedist\\.

    > [!NOTE]
    >  Visual hata ayıklama sürümlerini dağıtmak zorunda uzak başka bir bilgisayarda Visual Studio 2005 ya da Visual Studio 2008'i kullanarak oluşturulmuş uygulamanızın hata ayıklama için C++ kitaplık DLL'lerini paylaşılan yan yana derlemeler olarak. Karşılık gelen birleştirme modüllerini yüklemek için bir kurulum projesi veya Windows Installer'ı kullanabilirsiniz.

- The_ kullanın**Dağıt** seçeneğini **Configuration Manager** proje çıktısı ve diğer dosyaları uzak bilgisayara kopyalamak üzere Visual Studio'da iletişim kutusu.

Visual C++ DLL'leri yüklendikten sonra uzaktan hata ayıklayıcı bir ağ paylaşımı üzerinde çalıştırabilirsiniz. Uzaktan hata ayıklama hakkında daha fazla bilgi için bkz. [uzaktan hata ayıklama](/visualstudio/debugger/remote-debugging).

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ üzerinde Dağıtım](deployment-in-visual-cpp.md)<br>
[Windows Installer komut satırı seçenekleri](/windows/desktop/Msi/command-line-options)<br>
[Dağıtım Örnekleri](deployment-examples.md)<br>
[Uzaktan Hata Ayıklama](/visualstudio/debugger/remote-debugging)
