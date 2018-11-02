---
title: Yürütülebilir Hata Ayıklamayı Çalıştırmak için Test Makinesi Hazırlama
ms.date: 11/04/2016
helpviewer_keywords:
- debug executable, preparing a test machine to run
ms.assetid: f0400989-cc2e-4dce-9788-6bdbe91c6f5a
ms.openlocfilehash: 95633a9b6b04be7e551934744868e10f60d51fb4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50509115"
---
# <a name="preparing-a-test-machine-to-run-a-debug-executable"></a>Yürütülebilir Hata Ayıklamayı Çalıştırmak için Test Makinesi Hazırlama

Visual C++ ile oluşturulan bir uygulamanın hata ayıklama sürümü test etmek için bir bilgisayarı hazırlamak için uygulamanın bağımlı Visual C++ Kitaplık DLL'lerin hata ayıklama sürümlerini dağıtmak zorunda. DLL'leri dağıtılacak olan belirlemek için adımları izleyin. [Visual C++ uygulaması bağımlılıklarını anlama](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md). Genellikle, biten "d"; Visual C++ Kitaplık DLL'lerin hata ayıklama sürümlerine sahip Örneğin, hata ayıklama sürümünü msvcr100.DLL'i tekrar msvcr100d.dll olarak adlandırılır.

> [!NOTE]
>  Uygulama hata ayıklama sürümleri yeniden dağıtılamaz ve Visual C++ Kitaplık DLL'lerin hata ayıklama sürümleri yeniden dağıtılamaz. Uygulamalar ve Visual C++ DLL'lerini hata ayıklama sürümleri, hata ayıklama ve Visual Studio yüklü olmayan bir bilgisayarda test etme amacına yalnızca, diğer bilgisayarlara dağıtabilir. Daha fazla bilgi için [Visual C++ dosyalarını yeniden dağıtma](../ide/redistributing-visual-cpp-files.md).

Bir uygulamanın hata ayıklama sürümü ile birlikte Visual C++ Kitaplık DLL'lerin hata ayıklama sürümleri dağıtmanın üç yolu vardır.

- Merkezi dağıtım, birleştirme modülleri için doğru kitaplık sürümünü ve uygulamanızın mimarisini içeren bir kurulum projesi kullanarak belirli bir Visual C++ DLL'ye hata ayıklama sürümü %windir%\system32\ dizinine yüklemek için kullanın. Birleştirme modülleri, Program dosyaları veya Program dosyaları (x86) \Common modülleri dizinde bulunur\\. Birleştirme modülü hata ayıklama sürümünü hata ayıklama namefor örnekte, Microsoft_VC110_DebugCRT_x86.msm vardır. Bu dağıtım örneği bulunabilir [izlenecek yol: Kurulum projesi dağıtma bir Visual C++ Application By Using](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).

- Program dosyaları veya Program dosyaları (x86) \Microsoft Visual Studio dizininde sağlanan dosyalarını kullanarak uygulama yükleme dizininde belirli bir Visual C++ DLL'ye hata ayıklama sürümünü yüklemek için yerel dağıtım kullanan \<sürüm > \VC\redist\Debug_NonRedist\\.

    > [!NOTE]
    >  Visual C++ Kitaplığı'nı DLL'ler paylaşılan yan yana derlemeler olarak hata ayıklama sürümlerini dağıtmak zorunda uzak başka bir bilgisayarda Visual C++ 2005 ya da Visual C++ 2008 kullanılarak oluşturulmuş uygulamanızın hata ayıklama için. Karşılık gelen birleştirme modüllerini yüklemek için bir kurulum projesi veya Windows Installer'ı kullanabilirsiniz.

- The_ kullanın**Dağıt** seçeneğini **Configuration Manager** proje çıktısı ve diğer dosyaları uzak bilgisayara kopyalamak üzere Visual Studio'da iletişim kutusu.

Visual C++ DLL'leri yüklendikten sonra uzaktan hata ayıklayıcı bir ağ paylaşımı üzerinde çalıştırabilirsiniz. Uzaktan hata ayıklama hakkında daha fazla bilgi için bkz. [uzaktan hata ayıklama](/visualstudio/debugger/remote-debugging.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++ üzerinde Dağıtım](../ide/deployment-in-visual-cpp.md)<br>
[Windows Installer komut satırı seçenekleri](/windows/desktop/Msi/command-line-options)<br>
[Dağıtım Örnekleri](../ide/deployment-examples.md)<br>
[Uzaktan Hata Ayıklama](/visualstudio/debugger/remote-debugging.md)