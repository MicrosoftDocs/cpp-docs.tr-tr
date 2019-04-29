---
title: Yeniden dağıtılabilir paketini (C++) kullanarak uygulama dağıtma
ms.date: 09/17/2018
helpviewer_keywords:
- walkthrough, deploying a Visual C++ application by using the redistributable package
ms.assetid: e59becbf-b8c6-4c8e-bab3-b69cc1ed3e5e
ms.openlocfilehash: ccf6b74096894c2e48258e6e0a60b807c7c6c5b4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62345467"
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-the-visual-c-redistributable-package"></a>İzlenecek yol: Visual C++ yeniden dağıtılabilir paketini kullanarak bir Visual C++ uygulamasını dağıtma

Bu makalede, Visual C++ uygulaması dağıtmak için Visual C++ yeniden dağıtılabilir paketi kullanmayı açıklar.

## <a name="prerequisites"></a>Önkoşullar

Bu bileşenler, bu izlenecek yolu tamamlamak için aşağıdakiler gereklidir:

- Visual Studio'nun yüklü olduğu bir bilgisayar.

- Visual C++ kitaplıkları yok. başka bir bilgisayar.

### <a name="to-use-the-visual-c-redistributable-package-to-deploy-an-application"></a>Bir uygulamayı dağıtmak için Visual C++ yeniden dağıtılabilir paketi kullanmak için

1.  İçindeki adımları izleyerek bir MFC uygulaması oluşturmayı ve [izlenecek yol: Bir kurulum projesi kullanarak Visual C++ uygulamasını dağıtma](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).

1. Bir dosya oluşturun, setup.bat adlandırın ve aşağıdakileri ekleyin. Değişiklik `MyMFCApplication` projenizin adı.

    ```cmd
    @echo off
    vcredist_x86.exe
    mkdir "C:\Program Files\MyMFCApplication"
    copy MyMFCApplication.exe "C:\Program Files\MyMFCApplication"
    ```

1. Kendi kendine ayıklanan bir kurulum dosyası oluşturun:

   1. Bir komut isteminde veya **çalıştırma** penceresinde iexpress.exe çalıştırın.

   1. Seçin **yeni kendi kendine ayıklama yönergesi dosya oluştur** seçip **sonraki** düğmesi.

   1. Seçin **dosyaları ayıklayın ve bir yükleme komutunu Çalıştır** seçip **sonraki**.

   1. MFC uygulamanızı adını metin kutusuna girin ve ardından **sonraki**.

   1. Üzerinde **onay istemi** sayfasında **istem yok** seçip **sonraki**.

   1. Üzerinde **lisans sözleşmesini** sayfasında **lisans gösterme** seçip **sonraki**.

   1. Üzerinde **paketlenen dosyalar** sayfasında, aşağıdaki dosyaları ekleyin ve ardından **sonraki**.

      - MFC uygulamanızı (.exe dosyası).

      - vcredist_x86.exe. Bu dosya \Program dosyaları (x86) \Microsoft Visual Studio bulunur \<sürüm > \SDK\Bootstrapper\Packages\. Ayrıca bu dosyayı indirebileceğiniz [Microsoft](https://www.microsoft.com/download/confirmation.aspx?id=5555).

      - Önceki adımda oluşturduğunuz setup.bat dosya.

   1. Üzerinde **yükleme programı başlatmak için** sayfasında **yükleme programı** metin kutusunda, aşağıdaki komut satırını girin ve ardından **sonraki**.

      **cmd.exe /c "setup.bat"**

   1. Üzerinde **Göster penceresi** sayfasında **varsayılan** seçip **sonraki**.

   1. Üzerinde **tamamlandı iletisi** sayfasında **ileti** seçip **sonraki**.

   1. Üzerinde **paket adı ve seçenekleri** , kendiliğinden kurulum dosyası için bir ad girin **Store paket içinde uzun dosya adı'nı kullanarak dosyaları** seçeneğini ve ardından **sonraki**. Dosya adının sonuna Setup.exe—for örnek olmalıdır *MyMFCApplicationSetup.exe*.

   1. Üzerinde **yeniden yapılandırma** sayfasında **yeniden başlatma yok** seçip **sonraki**.

   1. Üzerinde **Kaydet kendi kendine ayıklama yönergesi** sayfasında **Kaydet Self ayıklama yönergesi (SED) dosyası** seçip **sonraki**.

   1. Üzerinde **paketi oluştur** sayfasında **sonraki**. Seçin **son**.

1. Visual C++ kitaplıkları olmayan diğer bilgisayarda kendiliğinden kurulum dosyası test edin:

   1. Başka bir bilgisayarda Kurulum dosyasının bir kopyasını indirin ve ardından çalıştığına ve sağladığı adımları izleyerek yükleyin. Seçilen seçeneklere bağlı olarak, yükleme gerektirebilir **yönetici olarak çalıştır** komutu.

   1. MFC uygulamasını çalıştırın.

      Kendiliğinden kurulum dosyası 2. adımda belirttiğiniz klasörde MFC uygulamasını yükler. Visual C++ yeniden dağıtılabilir paketi yükleyici kendiliğinden kurulum dosyasına dahil edilir çünkü uygulama başarıyla çalışır.

      > [!IMPORTANT]
      > Yükleyici çalışma zamanının hangi sürümünün yüklü olduğunu belirlemek için kayıt defteri anahtarı \HKLM\SOFTWARE\Microsoft\VisualStudio denetler\\\<sürüm > \VC\Runtimes\\<platform>. Şu anda yüklü olan sürümü yükleyici yüklemeye çalıştığı sürümden daha yeniyse, yükleyici eski sürümü yüklemeden başarı döndürür ve ek bir giriş Denetim Masası'ndaki yüklü programlar sayfasında bırakır.

## <a name="see-also"></a>Ayrıca bkz.

[Dağıtım Örnekleri](deployment-examples.md)<br/>
