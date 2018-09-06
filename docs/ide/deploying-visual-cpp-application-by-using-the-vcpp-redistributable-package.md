---
title: Yeniden dağıtılabilir paketini (C++) kullanarak uygulama dağıtma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- walkthrough, deploying a Visual C++ application by using the redistributable package
ms.assetid: e59becbf-b8c6-4c8e-bab3-b69cc1ed3e5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 569c5c8adcb57ae92f111929efca544c76412a4b
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43895285"
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-the-visual-c-redistributable-package"></a>İzlenecek Yol: Visual C++ Yeniden Dağıtılabilir Paketini Kullanarak Visual C++ Uygulaması Dağıtmak

Bu makalede, Visual C++ uygulaması dağıtmak için Visual C++ yeniden dağıtılabilir paketi kullanmayı açıklar.

## <a name="prerequisites"></a>Önkoşullar

Bu bileşenler, bu izlenecek yolu tamamlamak için aşağıdakiler gereklidir:

- Visual Studio'nun yüklü olduğu bir bilgisayar.

- Visual C++ kitaplıkları yok. başka bir bilgisayar.

### <a name="to-use-the-visual-c-redistributable-package-to-deploy-an-application"></a>Bir uygulamayı dağıtmak için Visual C++ yeniden dağıtılabilir paketi kullanmak için

1. İlk üç adımları izleyerek bir MFC uygulaması oluşturma ve [izlenecek yol: Kurulum projesi dağıtma bir Visual C++ Application By Using](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).

2. Bir dosya oluşturun, setup.bat adlandırın ve aşağıdakileri ekleyin. Değişiklik `MyMFCApplication` projenizin adı.

    ```cmd
    @echo off
    vcredist_x86.exe
    mkdir "C:\Program Files\MyMFCApplication"
    copy MyMFCApplication.exe "C:\Program Files\MyMFCApplication"
    ```  

3. Kendi kendine ayıklanan bir kurulum dosyası oluşturun:

   1. Bir komut isteminde veya **çalıştırma** penceresinde iexpress.exe çalıştırın.

   2. Seçin **yeni kendi kendine ayıklama yönergesi dosya oluştur** seçip **sonraki** düğmesi.

   3. Seçin **dosyaları ayıklayın ve bir yükleme komutunu Çalıştır** seçip **sonraki**.

   4. MFC uygulamanızı adını metin kutusuna girin ve ardından **sonraki**.

   5. Üzerinde **onay istemi** sayfasında **istem yok** seçip **sonraki**.

   6. Üzerinde **lisans sözleşmesini** sayfasında **lisans gösterme** seçip **sonraki**.

   7. Üzerinde **paketlenen dosyalar** sayfasında, aşağıdaki dosyaları ekleyin ve ardından **sonraki**.

      - MFC uygulamanızı (.exe dosyası).

      - VCRedist_x86.exe. Bu dosya SDKs\Windows\v7.0A\Bootstrapper\Packages\vcredist_x86 \Program Files\Microsoft bulunur\\.

      - Önceki adımda oluşturduğunuz setup.bat dosya.

   8. Üzerinde **yükleme programı başlatmak için** sayfasında **yükleme programı** metin kutusunda, aşağıdaki komut satırını girin ve ardından **sonraki**.

      **cmd.exe /c "setup.bat"**  

   9. Üzerinde **Göster penceresi** sayfasında **varsayılan** seçip **sonraki**.

   10. Üzerinde **tamamlandı iletisi** sayfasında **ileti** seçip **sonraki**.

   11. Üzerinde **paket adı ve seçenekleri** , kendiliğinden kurulum dosyası için bir ad girin **Store paket içinde uzun dosya adı'nı kullanarak dosyaları** seçeneğini ve ardından **sonraki**. Dosya adının sonuna Setup.exe—for örnek, MyMFCApplicationSetup.exe olması gerekir.

   12. Üzerinde **yeniden yapılandırma** sayfasında **yeniden başlatma yok** seçip **sonraki**.

   13. Üzerinde **Kaydet kendi kendine ayıklama yönergesi** sayfasında **Kaydet Self ayıklama yönergesi (SED) dosyası** seçip **sonraki**.

   14. Üzerinde **paketi oluştur** sayfasında **sonraki**.

4. Visual C++ kitaplıkları olmayan diğer bilgisayarda kendiliğinden kurulum dosyası test edin:

   1. Başka bir bilgisayarda Kurulum dosyasının bir kopyasını indirin ve ardından çalıştığına ve sağladığı adımları izleyerek yükleyin.

   2. MFC uygulamasını çalıştırın.

      Kendiliğinden kurulum dosyası 2. adımda belirttiğiniz klasörde MFC uygulamasını yükler. Visual C++ yeniden dağıtılabilir paketi yükleyici kendiliğinden kurulum dosyasına dahil edilir çünkü uygulama başarıyla çalışır.

      > [!IMPORTANT]
      > Yükleyici çalışma zamanının hangi sürümünün yüklü olduğunu belirlemek için kayıt defteri anahtarı \HKLM\SOFTWARE\Microsoft\VisualStudio\11.0\VC\Runtimes denetler\\[platform]. Şu anda yüklü olan sürümü yükleyici yüklemeye çalıştığı sürümden daha yeniyse, yükleyici eski sürümü yüklemeden başarı döndürür ve ek bir giriş Denetim Masası'ndaki yüklü programlar sayfasında bırakır.

## <a name="see-also"></a>Ayrıca Bkz.

[Dağıtım Örnekleri](../ide/deployment-examples.md)