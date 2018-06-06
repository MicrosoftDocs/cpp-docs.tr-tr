---
title: Hata ayıklama yürütülebilir dosyayı çalıştırmak için Test Makinesi hazırlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- debug executable, preparing a test machine to run
ms.assetid: f0400989-cc2e-4dce-9788-6bdbe91c6f5a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33683ebe349fbfdcb3fd51179ed6bc3140510c00
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33330303"
---
# <a name="preparing-a-test-machine-to-run-a-debug-executable"></a>Yürütülebilir Hata Ayıklamayı Çalıştırmak için Test Makinesi Hazırlama
Visual C++ ile yerleşik bir uygulamanın hata ayıklama sürümü test etmek için bir bilgisayarı hazırlamak için uygulamanın bağımlı Visual C++ Kitaplık DLL'lerde hata ayıklama sürümleri dağıtmak zorunda. DLL'leri dağıtılacak olan belirlemek için adımları [bir Visual C++ uygulaması bağımlılıklarını anlama](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md). Genellikle, Visual C++ Kitaplık DLL'lerde hata ayıklama sürümleri "d"; bitiş adlara sahip Örneğin, msvcr100.dll hata ayıklama sürümü msvcr100d.dll olarak adlandırılır.  
  
> [!NOTE]
>  Bir uygulamanın hata ayıklama sürümleri dağıtılamaz ve Visual C++ Kitaplık DLL'lerde hata ayıklama sürümleri dağıtılamaz. Hata ayıklama ve Visual Studio yüklü olmayan bir bilgisayarda uygulamaları test etme amacına yalnızca, diğer bilgisayarlar için hata ayıklama sürümleri uygulamalar ve Visual C++ DLL'ler dağıtabilirsiniz. Daha fazla bilgi için bkz: [Visual C++ dosyalarını yeniden dağıtma](../ide/redistributing-visual-cpp-files.md).  
  
 Bir uygulamanın hata ayıklama sürümü ile birlikte Visual C++ Kitaplık DLL'lerde hata ayıklama sürümleri dağıtmak için üç yolu vardır.  
  
-   Birleştirme modülleri için doğru kitaplık sürümü ve uygulamanızın mimarisini içeren bir kurulum projesi kullanarak %windir%\system32\ dizine belirli Visual C++ DLL hata ayıklama sürümü yüklemek için merkezi dağıtım kullanın. Birleştirme modüllerini Program Files veya \Common Files\Merge modülleri (x86) Program Files dizini içinde bulunan\\. Bir birleştirme modülü hata ayıklama sürümü hata ayıklama namefor örnekte Microsoft_VC110_DebugCRT_x86.msm sahiptir. Bu dağıtım örneği bulunabilir [izlenecek yol: bir Visual C++ uygulamasını kullanarak bir kurulum projesi dağıtma](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).  
  
-   Belirli Visual C++ DLL hata ayıklama sürümü uygulamanın yükleme dizininde Program dosyaları veya Program dosyaları (x86) directory \Microsoft Visual Studio içinde sağlanan dosyalarını kullanarak yüklemek için yerel dağıtım kullanmak \<sürüm > \VC\redist\Debug_NonRedist\\.  
  
    > [!NOTE]
    >  Visual C++ Kitaplık DLL'ler paylaşılan yan yana derlemeler olarak hata ayıklama sürümleri dağıtmak zorunda uzak başka bir bilgisayara Visual C++ 2005 veya Visual C++ 2008 kullanılarak oluşturulmuş uygulamanızın, hata ayıklama için. Karşılık gelen birleştirme modüllerini yüklemek için Kurulum projesi veya Windows Installer'ı kullanabilirsiniz.  
  
-   The_ kullanmak**dağıtma** seçeneğini **Configuration Manager** proje çıktı ve diğer dosyaları uzak bilgisayara kopyalamak için Visual Studio'da iletişim kutusu. 
  
 Visual C++ DLL'leri yüklendikten sonra bir ağ paylaşımına uzaktan hata ayıklayıcı çalıştırabilirsiniz. Uzaktan hata ayıklama hakkında daha fazla bilgi için bkz: [uzaktan hata ayıklama](/visualstudio/debugger/remote-debugging.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
 [Visual C++ üzerinde dağıtım](../ide/deployment-in-visual-cpp.md)   
 [Windows Installer komut satırı seçenekleri](http://msdn.microsoft.com/library/windows/desktop/aa367988.aspx)   
 [Dağıtım örnekleri](../ide/deployment-examples.md) [uzaktan hata ayıklama](/visualstudio/debugger/remote-debugging.md)