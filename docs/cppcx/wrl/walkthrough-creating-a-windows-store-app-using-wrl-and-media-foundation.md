---
title: 'İzlenecek yol: WRL ve Medya Altyapısı kullanarak UWP uygulaması oluşturma'
ms.date: 04/23/2019
ms.topic: reference
ms.assetid: 0336c550-fbeb-4dc4-aa9b-660f9fc45382
ms.openlocfilehash: 272092982c5e9cc57f52043e08c8bd384c43ea96
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82031517"
---
# <a name="walkthrough-creating-a-uwp-app-using-wrl-and-media-foundation"></a>İzlenecek yol: WRL ve Medya Altyapısı kullanarak UWP uygulaması oluşturma

> [!NOTE]
> Yeni UWP uygulamaları ve bileşenleri için, Windows Runtime API'leri için yeni bir standart C++17 dil projeksiyonu olan [C++/WinRT'yi](/windows/uwp/cpp-and-winrt-apis/)kullanmanızı öneririz. C++/WinRT, Windows 10 SDK'da 1803 sürümünden itibaren kullanılabilir. C++/WinRT tamamen üstbilgi dosyalarında uygulanır ve modern Windows API'sine birinci sınıf erişim sağlamak üzere tasarlanmıştır.

Bu eğitimde, [Microsoft Media Foundation'ı](/windows/win32/medfound/microsoft-media-foundation-sdk)kullanan evrensel bir Windows Platformu (UWP) uygulaması oluşturmak için Windows Runtime C++ Şablon Kitaplığı'nı (WRL) nasıl kullanacağınızı öğreneceksiniz.

Bu örnek, web kamerasından yakalanan görüntülere gri tonlama efekti uygulayan özel bir Medya Temel dönüşümü oluşturur. Uygulama, özel dönüşümü tanımlamak için C++ ve yakalanan görüntüleri dönüştürmek için bileşeni kullanmak için C# kullanır.

> [!NOTE]
> C# yerine, özel dönüştürme bileşenini kullanmak için JavaScript, Visual Basic veya C++ da kullanabilirsiniz.

Çoğu durumda, Windows Runtime oluşturmak için C++/CX kullanabilirsiniz. Ancak, bazen WRL kullanmanız gerekir. Örneğin, Microsoft Media Foundation için bir ortam uzantısı oluşturduğunuzda, hem COM hem de Windows Runtime arabirimlerini uygulayan bir bileşen oluşturmanız gerekir. C++/CX yalnızca Windows Runtime nesneleri oluşturabildiği için, bir ortam uzantısı oluşturmak için WRL'yi kullanmanız gerekir, çünkü hem COM hem de Windows Runtime arabirimlerinin uygulanmasını sağlar.

> [!NOTE]
> Bu kod örneği uzun olsa da, yararlı bir Media Foundation dönüşümü oluşturmak için gereken minimum tutarı gösterir. Kendi özel dönüşümünüz için bir başlangıç noktası olarak kullanabilirsiniz. Bu örnek, videoya efekt uygulamak, videoyu çözmek ve ortam akışları üreten şema işleyicileri oluşturmak için ortam uzantıları nı kullanan [Medya uzantıları örneğinden](https://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)uyarlanmıştır.

## <a name="prerequisites"></a>Önkoşullar

- Visual Studio 2017 ve sonrası, UWP desteği isteğe bağlı bir bileşendir. Yüklemek için Windows Başlat menüsünden Visual Studio Yükleyici'yi açın ve Visual Studio sürümünü bulun. **Değiştir'i** seçin ve ardından **Evrensel Windows Platform Geliştirme** döşemesinin denetlendirildiğinden emin olun. **İsteğe Bağlı Bileşenler** altında Visual Studio 2017 **için UWP için C++ Araçlarını (v141)** veya Visual Studio 2019 **için UWP için C++ Araçları'nı (v142)** kontrol edin. Ardından kullanmak istediğiniz Windows SDK sürümünü denetleyin.

- [Windows Runtime](/uwp/api/)ile deneyim.

- COM ile deneyim.

- Bir Web kamerası.

## <a name="key-points"></a>Önemli noktalar

- Özel bir Media Foundation bileşeni oluşturmak için, arabirimi tanımlamak, bu arabirimi uygulamak ve diğer bileşenlerden etkinleştirilebilir hale getirmek için bir Microsoft Arabirimi Tanımı Dili (MIDL) tanım dosyası kullanın.

- Ve `namespace` `runtimeclass` öznitelikleri ve `NTDDI_WIN8` [sürüm](/windows/win32/Midl/version) öznitelik değeri WRL kullanan bir Media Foundation bileşeni için MIDL tanımının önemli parçalarıdır.

- [Microsoft::WRL::RuntimeClass,](runtimeclass-class.md) özel Media Foundation bileşeninin temel sınıfıdır. Şablon bağımsız değişkeni olarak sağlanan [Microsoft::WRL::RuntimeClassType::WinRtClassicComMix](runtimeclasstype-enumeration.md) enum değeri, hem Windows Runtime sınıfı olarak hem de klasik com çalışma zamanı sınıfı olarak kullanılmak üzere sınıfı işaretler.

- [InspectableClass](inspectableclass-macro.md) makrosu, başvuru sayımı ve yöntem `QueryInterface` gibi temel COM işlevlerini uygular ve çalışma zamanı sınıf adı ve güven düzeyini ayarlar.

- [DllGetActivationFactory](/windows/win32/winrt/functions), [DllCanUnloadNow](/windows/win32/api/combaseapi/nf-combaseapi-dllcanunloadnow)ve [DllGetClassObject](/windows/win32/api/combaseapi/nf-combaseapi-dllgetclassobject)gibi DLL giriş noktası işlevlerini uygulamak için Microsoft:WRL::[Modül sınıfını](module-class.md) kullanın.

- Bileşeninizin DLL'sini runtimeobject.lib'e bağla. Ayrıca Windows meta verileri oluşturmak için bağlayıcı satırında [/WINMD](../../cppcx/compiler-and-linker-options-c-cx.md) belirtin.

- WRL bileşenlerini UWP uygulamaları için erişilebilir hale getirmek için proje başvurularını kullanın.

### <a name="to-use-the-wrl-to-create-the-media-foundation-grayscale-transform-component"></a>Media Foundation gri tonlama dönüştürme bileşenini oluşturmak için WRL'yi kullanmak

1. Visual Studio'da **boş** çözüm projesi oluşturun. Projeyi adlandırın, örneğin, *MediaCapture*.

1. Çözüme bir **DLL (Evrensel Windows)** projesi ekleyin. Projeadı, örneğin, *GrayscaleTransform*.

1. Projeye bir **Midl Dosyası (.idl)** dosyası ekleyin. Dosyayı adlandırın, örneğin, *GrayscaleTransform.idl*.

1. Bu kodu GrayscaleTransform.idl'ye ekleyin:

   [!code-cpp[wrl-media-capture#1](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_1.idl)]

1. İçeriği değiştirmek için aşağıdaki kodu `pch.h`kullanın:

   [!code-cpp[wrl-media-capture#2](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_2.h)]

1. Projeye yeni bir üstbilgi dosyası ekleyin, adlandırın `BufferLock.h`ve içeriği bu kodla değiştirin:

   [!code-cpp[wrl-media-capture#3](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_3.h)]

1. `GrayscaleTransform.h`bu örnekte kullanılmaz. İsterseniz projeden kaldırabilirsiniz.

1. İçeriği değiştirmek için aşağıdaki kodu `GrayscaleTransform.cpp`kullanın:

   [!code-cpp[wrl-media-capture#4](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_4.cpp)]

1. Projeye yeni bir modül tanımlı dosya `GrayscaleTransform.def`ekleyin, adlandırın ve sonra bu kodu ekleyin:

   ```
   EXPORTS
       DllCanUnloadNow                     PRIVATE
       DllGetActivationFactory             PRIVATE
       DllGetClassObject                   PRIVATE
   ```

1. İçeriği değiştirmek için aşağıdaki kodu `dllmain.cpp`kullanın:

   [!code-cpp[wrl-media-capture#6](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_6.cpp)]

1. Projenin **Özellik Sayfaları** iletişim kutusunda, aşağıdaki **Bağlayıcı** özelliklerini ayarlayın.

   1. **Input**altında , **Modül Tanımı** `GrayScaleTransform.def`Dosyası için , belirtin .

   1. Ayrıca **Giriş**altında `runtimeobject.lib`, `mfuuid.lib`eklemek `mfplat.lib` , ve **Ek Bağımlılıklar** özelliği.

   1. **Windows Meta verileri** **altında, Windows Meta verilerini** Evet **(/WINMD)** olarak oluşturun'u ayarlayın.

### <a name="to-use-the-wrl-the-custom-media-foundation-component-from-a-c-app"></a>WRL'yi kullanmak için bir C# uygulamasından özel Media Foundation bileşeni

1. Çözüme yeni bir **C# Blank App (Evrensel Windows)** projesi ekleyin. `MediaCapture` Projeyi adlandırın, örneğin, *MediaCapture*.

1. **MediaCapture** projesinde `GrayscaleTransform` projeye bir başvuru ekleyin. Nasıl yapılacağını öğrenmek [için bkz: Başvuru Yöneticisi'ni Kullanarak Referans Ekleme veya Kaldırma.](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager)

1. Özellikler `Package.appxmanifest` **sekmesinde** **Mikrofon** ve Web **Kamerası'nı**seçin. Web kamerasından fotoğraf çekmek için her iki özellik de gereklidir.

1. In `MainPage.xaml`, kök [Grid](/uwp/api/windows.ui.xaml.controls.grid) öğesine bu kodu ekleyin:

   [!code-xml[wrl-media-capture#7](../codesnippet/Xaml/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_7.xaml)]

1. İçeriği değiştirmek için aşağıdaki kodu `MainPage.xaml.cs`kullanın:

   [!code-cs[wrl-media-capture#8](../codesnippet/CSharp/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_8.cs)]

Aşağıdaki resimde `MediaCapture app`.

![MediaCapture uygulaması fotoğraf çekme](../media/wrl_media_capture.png "WRL_Media_Capture")

## <a name="next-steps"></a>Sonraki Adımlar

Örnek, varsayılan web kamerasından teker teker nasıl fotoğraf çekilir gösterir. [Ortam uzantıları örneği](https://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096) daha fazlasını yapar. Web kamerası aygıtlarını nasıl sayısala gösterip yerel şema işleyicileriyle nasıl çalışacağını gösterir ve hem tek tek fotoğraflarda hem de video akışlarında çalışan ek ortam efektlerini gösterir.

## <a name="see-also"></a>Ayrıca bkz.

[Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](windows-runtime-cpp-template-library-wrl.md)<br/>
[Microsoft Media Foundation](/windows/win32/medfound/microsoft-media-foundation-sdk)<br/>
[Ortam uzantıları örneği](https://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)
