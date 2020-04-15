---
title: Yeniden Dağıtılabilir Paketi (C++) Kullanarak Bir Uygulamayı Dağıtma
ms.date: 04/23/2019
helpviewer_keywords:
- walkthrough, deploying a Visual C++ application by using the redistributable package
ms.assetid: e59becbf-b8c6-4c8e-bab3-b69cc1ed3e5e
ms.openlocfilehash: d2bd0794a67cf70b9da0499e3d2cafa553531fe1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370249"
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-the-visual-c-redistributable-package"></a>İzlenecek Yol: Visual C++ Yeniden Dağıtılabilir Paketini Kullanarak Visual C++ Uygulaması Dağıtmak

Bu adım adım makale, Visual C++ uygulamasını dağıtmak için Visual C++ Yeniden Dağıtılabilir Paket'in nasıl kullanılacağını açıklar.

## <a name="prerequisites"></a>Ön koşullar

Bu gözden geçirmeyi tamamlamak için bu bileşenlere sahip olmalısınız:

- Visual Studio yüklü bir bilgisayar.

- Visual C++ kitaplıkları olmayan ek bir bilgisayar.

### <a name="to-use-the-visual-c-redistributable-package-to-deploy-an-application"></a>Bir uygulamayı dağıtmak için Visual C++ Yeniden Dağıtılabilir Paketi'ni kullanmak için

1. [Walkthrough: Visual C++ Uygulamasını Kurulum Projesi Kullanarak Dağıtma](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md)adımlarını izleyerek bir MFC uygulaması oluşturun ve oluşturun.

1. Bir dosya oluşturun, setup.bat adını ve aşağıdaki komutları ekleyin. Projenizin adını değiştirin. `MyMFCApplication`

    ```cmd
    @echo off
    vcredist_x86.exe
    mkdir "C:\Program Files\MyMFCApplication"
    copy MyMFCApplication.exe "C:\Program Files\MyMFCApplication"
    ```

1. Kendi kendini ayıklayan bir kurulum dosyası oluşturun:

   1. Komut isteminde veya **Çalıştır** penceresinde iexpress.exe'yi çalıştırın.

   1. **Yeni Self Extraction Yönergesi oluştur dosyasını** seçin ve ardından **Sonraki** düğmesini seçin.

   1. **Dosyaları Ayıkla'yı seçin ve bir yükleme komutu çalıştırın** ve sonra **İleri'yi**seçin.

   1. Metin kutusuna, MFC uygulamanızın adını girin ve sonra **İleri'yi**seçin.

   1. Onay **komut istemi** sayfasında **İstem Yok'u** seçin ve ardından **İleri'yi**seçin.

   1. Lisans **sözleşmesi** sayfasında, **lisans görüntüleme yi** seçin ve **sonra İleri'yi**seçin.

   1. Paketlenmiş **dosyalar** sayfasında, aşağıdaki dosyaları ekleyin ve sonra **İleri'yi**seçin.

      - MFC uygulamanız (.exe dosyası).

      - vcredist_x86.exe. Visual Studio 2015'te bu dosya *%VCINSTALLDIR%redist\\1033'te\\*yer almaktadır. Visual Studio 2017 ve Visual Studio 2019'da bu dosya *%VCToolsRedistDir%* içinde yer almaktadır. Ayrıca [Microsoft'tan en son desteklenen redist dosyasını indirebilirsiniz.](https://support.microsoft.com/help/2977003/the-latest-supported-visual-c-downloads)

      - Önceki adımda oluşturduğunuz setup.bat dosyası.

   1. **Başlat'a Yükleme Programı** sayfasında, **Programı Yükle** metin kutusunda aşağıdaki komut satırını girin ve sonra **İleri'yi**seçin.

      **cmd.exe /c "setup.bat"**

   1. Göster **penceresinde** **Varsayılan'ı** seçin ve sonra **İleri'yi**seçin.

   1. Tamamlanan **İleti** sayfasında **İleti yok'u** seçin ve **sonra İleri'yi**seçin.

   1. Paket **Adı ve Seçenekleri** sayfasında, kendi kendini ayıklayan kurulum dosyanız için bir ad girin, **Paket seçeneğinin içinde Uzun Dosya Adı kullanarak Mağaza dosyalarını** seçin ve **sonra İleri'yi**seçin. Dosya adının sonu Setup.exe olmalıdır—örneğin, *MyMFCApplicationSetup.exe*.

   1. Yeniden **Başlat'ı Yapılandır** sayfasında, **Yeniden Başlat'ı seçin** ve **sonra İleri'yi**seçin.

   1. Kendi **Kendini Çıkarma Yönergesi Kaydet** sayfasında, **Kendi Kendini Çıkarma Yönergesi (SED) dosyasını kaydet'i** seçin ve ardından **İleri'yi**seçin.

   1. Paket **Oluştur** sayfasında **İleri'yi**seçin. **Son**’u seçin.

1. Visual C++ kitaplıkları olmayan diğer bilgisayarda kendi kendini ayıklayan kurulum dosyasını sınayın:

   1. Diğer bilgisayarda, kurulum dosyasının bir kopyasını indirin ve ardından çalıştırarak ve sağladığı adımları izleyerek yükleyin. Seçilen seçeneklere bağlı olarak, yükleme yönetici komutu **olarak Çalıştır** gerektirebilir.

   1. MFC uygulamasını çalıştırın.

      Kendi kendini ayıklayan kurulum dosyası, adım 2'de belirttiğiniz klasördeki MFC uygulamasını yükler. Visual C++ Yeniden Dağıtılabilir Paket yükleyici kendi kendini ayıklayan kurulum dosyasına dahil olduğundan uygulama başarılı bir şekilde çalışır.

      > [!IMPORTANT]
      > Çalışma zamanının hangi sürümünün yüklü olduğunu belirlemek için, yükleyici\\kayıt\\\\defteri\\anahtarı \\\\HKLM\\SOFTWARE Microsoft VisualStudio_sürüm_\\VC Runtimes_platformu_\\Sürümünü denetler. Şu anda yüklenen sürüm yüklemeye çalıştığı sürümden daha yeniyse, yükleyici eski sürümü yüklemeden başarıyı döndürür ve Denetim Masası'ndaki yüklü programlar sayfasına ek bir giriş bırakır.

## <a name="see-also"></a>Ayrıca bkz.

[Dağıtım Örnekleri](deployment-examples.md)<br/>
