---
title: "Yeniden dağıtılabilir paketi (C++) kullanarak bir uygulamayı dağıtma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: walkthrough, deploying a Visual C++ application by using the redistributable package
ms.assetid: e59becbf-b8c6-4c8e-bab3-b69cc1ed3e5e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 52e3b048f896f0cfd532cb3000617756af2dca92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-the-visual-c-redistributable-package"></a>İzlenecek Yol: Visual C++ Yeniden Dağıtılabilir Paketini Kullanarak Visual C++ Uygulaması Dağıtmak
Bu adım adım makalede, Visual C++ uygulaması dağıtmak için Visual C++ yeniden dağıtılabilir paketi kullanmayı açıklar.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuzu tamamlamak için bu bileşenlere sahip olmanız gerekir:  
  
-   Visual Studio yüklü olan bir bilgisayar.  
  
-   Visual C++ kitaplıkları bulunmayan başka bir bilgisayar.  
  
### <a name="to-use-the-visual-c-redistributable-package-to-deploy-an-application"></a>Bir uygulamayı dağıtmak için Visual C++ yeniden dağıtılabilir paketi kullanmak için  
  
1.  Ve MFC uygulaması ilk üç adımları izleyerek oluşturmak [izlenecek yol: bir Visual C++ uygulamasını kullanarak bir kurulum projesi dağıtma](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).  
  
2.  Bir dosya oluşturun, setup.bat adlandırın ve aşağıdaki komutları ekleyin. Değişiklik `MyMFCApplication` projenizin adına.  
  
    ```cmd
    @echo off  
    vcredist_x86.exe  
    mkdir "C:\Program Files\MyMFCApplication"  
    copy MyMFCApplication.exe "C:\Program Files\MyMFCApplication"  
    ```  
  
3.  Kendi kendine ayıklanan bir kurulum dosyası oluşturun:  
  
    1.  Bir komut isteminde veya **çalıştırmak** penceresinde iexpress.exe çalıştırın.  
  
    2.  Seçin **yeni kendi kendine ayıklama yönergesi dosyası oluştur** ve ardından **sonraki** düğmesi.  
  
    3.  Seçin **dosyaları ayıklayın ve bir yükleme komutunu Çalıştır** ve ardından **sonraki**.  
  
    4.  MFC uygulamanızın adı metin kutusuna girin ve ardından **sonraki**.  
  
    5.  Üzerinde **onay istemi** sayfasında, **istem yok** ve ardından **sonraki**.  
  
    6.  Üzerinde **lisans sözleşmesini** sayfasında, **lisans gösterme** ve ardından **sonraki**.  
  
    7.  Üzerinde **paketlenen dosyalar** sayfasında, aşağıdaki dosyaları ekleyin ve ardından **sonraki**.  
  
        -   MFC uygulamanız (.exe dosyası).  
  
        -   VCRedist_x86.exe. Bu dosya SDKs\Windows\v7.0A\Bootstrapper\Packages\vcredist_x86 \Program Files\Microsoft bulunur\\.  
  
        -   Önceki adımda oluşturduğunuz setup.bat dosyasıdır.  
  
    8.  Üzerinde **yükleme programı başlatmak için** sayfasında **yükleme programı** metin kutusunda, aşağıdaki komut satırını girin ve ardından **sonraki**.  
  
         **cmd.exe /c "setup.bat"**  
  
    9. Üzerinde **Göster penceresi** sayfasında, **varsayılan** ve ardından **sonraki**.  
  
    10. Üzerinde **tamamlanmış ileti** sayfasında, **hiçbir ileti** ve ardından **sonraki**.  
  
    11. Üzerinde **paket adı ve seçenekleri** sayfasında, kendiliğinden açılan kurulum dosyası için bir ad girin **depolamak paketin içindeki uzun dosya adını kullanarak dosyaları** seçeneğini ve ardından **İleri**. Dosya adının sonuna Setup.exe—for örnek, MyMFCApplicationSetup.exe olması gerekir.  
  
    12. Üzerinde **yeniden yapılandırma** sayfasında, **yeniden başlatma yok** ve ardından **sonraki**.  
  
    13. Üzerinde **kendi kendine ayıklama yönergesi Kaydet** sayfasında, **kaydetmek kendi kendine ayıklama yönergesi (Azaltılabilir) dosya** ve ardından **sonraki**.  
  
    14. Üzerinde **Paket Oluştur** sayfasında, **sonraki**.  
  
4.  Visual C++ kitaplıkları olmayan başka bir bilgisayarda kendiliğinden açılan kurulum dosyasını test edin:  
  
    1.  Diğer bilgisayarda Kurulum dosyasının bir kopyasını indirin ve ardından onu çalıştıran ve sağladığı adımları izleyerek yükleyin.  
  
    2.  MFC uygulamasını çalıştırın.  
  
         2. adımda belirttiğiniz klasöründeki MFC uygulaması kendiliğinden açılan kurulum dosyasını yükler. Visual C++ yeniden dağıtılabilir paketi yükleyici kendiliğinden açılan kurulum dosyasında yer aldığından uygulama başarıyla çalışır.  
  
        > [!IMPORTANT]
        >  Çalışma zamanı hangi sürümünün yüklü belirlemek üzere kayıt defteri anahtarı \HKLM\SOFTWARE\Microsoft\VisualStudio\11.0\VC\Runtimes yükleyici denetler\\[platform]. Şu anda yüklü olan sürümü yükleyici yüklenmeye çalışılırken sürümden yeni ise, yükleyici eski sürümü yüklemeden başarı döndürür ve Denetim Masası'nda yüklü programlar sayfasında ek bir giriş bırakır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dağıtım Örnekleri](../ide/deployment-examples.md)