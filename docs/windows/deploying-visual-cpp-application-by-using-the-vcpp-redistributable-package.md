---
title: Yeniden dağıtılabilir paket (C++) kullanarak uygulama dağıtma
ms.date: 04/23/2019
helpviewer_keywords:
- walkthrough, deploying a Visual C++ application by using the redistributable package
ms.assetid: e59becbf-b8c6-4c8e-bab3-b69cc1ed3e5e
ms.openlocfilehash: 1e09debc53e5b1b3e1eeaa6a63924b04fd2b7ca5
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443885"
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-the-visual-c-redistributable-package"></a>İzlenecek Yol: Visual C++ Yeniden Dağıtılabilir Paketini Kullanarak Visual C++ Uygulaması Dağıtmak

Bu adım adım makalede, Visual bir C++ C++ uygulamayı dağıtmak Için Visual yeniden dağıtılabilir paketin nasıl kullanılacağı açıklanır.

## <a name="prerequisites"></a>Önkoşullar

Bu yönergeyi tamamlamak için aşağıdaki bileşenlere sahip olmanız gerekir:

- Visual Studio 'nun yüklü olduğu bir bilgisayar.

- Görsel C++ kitaplıkları olmayan ek bir bilgisayar.

### <a name="to-use-the-visual-c-redistributable-package-to-deploy-an-application"></a>Bir uygulamayı dağıtmak üzere C++ yeniden dağıtılabilir Visual paketini kullanmak için

1.  [Izlenecek yol: kurulum projesi kullanarak C++ görsel uygulama dağıtma](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md)BÖLÜMÜNDEKI adımları izleyerek bir MFC uygulaması oluşturun ve oluşturun.

1. Bir dosya oluşturun, Setup. bat olarak adlandırın ve aşağıdaki komutları buna ekleyin. `MyMFCApplication` projenizin adıyla değiştirin.

    ```cmd
    @echo off
    vcredist_x86.exe
    mkdir "C:\Program Files\MyMFCApplication"
    copy MyMFCApplication.exe "C:\Program Files\MyMFCApplication"
    ```

1. Kendiliğinden ayıklanan kurulum dosyası oluşturma:

   1. Bir komut isteminde veya **Çalıştır** penceresinde, IExpress. exe ' yi çalıştırın.

   1. **Yeni kendi kendine ayıklama yönergesi dosyası oluştur** ' u seçin ve ardından **İleri** düğmesini seçin.

   1. **Dosyaları ayıkla ' yı seçin ve bir yükleme komutu çalıştırın** ve ardından **İleri**' yi seçin.

   1. Metin kutusuna MFC uygulamanızın adını girin ve ardından **İleri**' yi seçin.

   1. **Onay istemi** sayfasında, **istem yok** ' u seçin ve ardından **İleri**' yi seçin.

   1. **Lisans Sözleşmesi** sayfasında, **Lisans görüntüleme** ' yi seçin ve ardından **İleri**' yi seçin.

   1. **Paketlenmiş dosyalar** sayfasında, aşağıdaki dosyaları ekleyin ve ardından **İleri**' yi seçin.

      - MFC uygulamanız (. exe dosyası).

      - vcredist_x86. exe. Visual Studio 2015 ' de bu dosya *% VCInstallDir% redist\\1033\\* konumunda bulunuyor. Visual Studio 2017 ve Visual Studio 2019 ' de bu dosya *% Vcaraçları Redistdir%* konumunda bulunuyor. [Microsoft 'tan desteklenen en son Redist dosyasını da indirebilirsiniz](https://support.microsoft.com/help/2977003/the-latest-supported-visual-c-downloads).

      - Önceki adımda oluşturduğunuz setup. bat dosyası.

   1. **Başlatılacak programı yüklemeye dön** sayfasında, **programı yüklemek** metin kutusuna aşağıdaki komut satırını girin ve ardından **İleri**' yi seçin.

      **cmd. exe/c "Setup. bat"**

   1. **Pencereyi göster** sayfasında, **varsayılan** ' i seçin ve ardından **İleri**' yi seçin.

   1. **Bitmiş ileti** sayfasında **ileti yok** ' u seçin ve ardından **İleri**' yi seçin.

   1. **Paket adı ve seçenekler** sayfasında, kendi kendine ayıklanan kurulum dosyanız için bir ad girin, **paket Içinde uzun dosya adı kullanarak mağaza dosyaları** seçeneğini belirleyin ve ardından **İleri**' yi seçin. Dosya adının sonu Setup. exe olmalıdır — örneğin, *MyMFCApplicationSetup. exe*.

   1. **Yeniden başlatma yapılandırma** sayfasında, **yeniden başlatma yok** ' u seçin ve ardından **İleri**' yi seçin.

   1. **Kendi kendine ayıklama yönergesini kaydet** sayfasında, **kendi kendine ayıklama yönergesi (SED) dosyasını Kaydet** ' i seçin ve ardından **İleri**' yi seçin.

   1. **Paket oluştur** sayfasında **İleri**' yi seçin. **Son**' a tıklayın.

1. Kendi kendine ayıklanan kurulum dosyasını, Visual C++ kitaplıkları olmayan diğer bilgisayarda test edin:

   1. Diğer bilgisayarda, kurulum dosyasının bir kopyasını indirin ve ardından çalıştırarak ve sağladığı adımları izleyerek yükleyin. Seçilen seçeneklere bağlı olarak yükleme, **yönetici olarak çalıştır** komutu gerektirebilir.

   1. MFC uygulamasını çalıştırın.

      Kendiliğinden ayıklanan kurulum dosyası, adım 2 ' de belirttiğiniz klasördeki MFC uygulamasını yüklenir. Visual C++ yeniden dağıtılabilir paket yükleyicisi kendi kendine ayıklanan kurulum dosyasına eklendiğinden uygulama başarıyla çalışıyor.

      > [!IMPORTANT]
      > Çalışma zamanının hangi sürümünün yüklü olduğunu anlamak için yükleyici, HKLM\\SOFTWARE\\Microsoft\\VisualStudio\\_sürüm_\\VC\\çalışma _zamanları\\\\_ kayıt defteri anahtarını kontrol eder.\\ Şu anda yüklü olan sürüm yükleyicinin yüklemeye çalışan sürümden daha yeniyse, yükleyici eski sürümü yüklemeden başarı döndürür ve Denetim Masası 'ndaki yüklü programlar sayfasında ek bir giriş bırakır.

## <a name="see-also"></a>Ayrıca bkz.

[Dağıtım Örnekleri](deployment-examples.md)<br/>
