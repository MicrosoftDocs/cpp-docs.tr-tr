---
title: 'İzlenecek yol: WRL ve Medya Altyapısı kullanarak UWP uygulaması oluşturma'
ms.date: 04/23/2019
ms.topic: reference
ms.assetid: 0336c550-fbeb-4dc4-aa9b-660f9fc45382
ms.openlocfilehash: 5c6fd2613c34fdecdf9128ed6a5d22d563961939
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079883"
---
# <a name="walkthrough-creating-a-uwp-app-using-wrl-and-media-foundation"></a>İzlenecek yol: WRL ve Medya Altyapısı kullanarak UWP uygulaması oluşturma

> [!NOTE]
> Yeni UWP uygulamaları ve bileşenleri için, Windows çalışma zamanı API 'leri için yeni bir Standart c++ 17 dil projeksiyonu olan [ C++/wınrt](/windows/uwp/cpp-and-winrt-apis/)kullanmanızı öneririz. C++/Wınrt, sürüm 1803 ' den Windows 10 SDK ' da kullanılabilir. C++/Wınrt tamamen başlık dosyalarında uygulanır ve modern Windows API 'sine ilk sınıf erişim sağlayacak şekilde tasarlanmıştır.

Bu öğreticide, [Microsoft medya altyapısı](/windows/win32/medfound/microsoft-media-foundation-sdk)kullanan bir evrensel WINDOWS platformu (UWP) uygulaması C++ oluşturmak için Windows çalışma zamanı Şablon kitaplığı (WRL) kullanmayı öğreneceksiniz.

Bu örnekte, bir Web kamerasından yakalanan görüntülere gri tonlamalı bir efekt uygulayan özel bir Medya Altyapısı dönüşümü oluşturulur. Uygulama, özel C++ dönüşümü tanımlamak ve C# yakalanan görüntüleri dönüştürmek üzere bileşeni kullanmak için kullanır.

> [!NOTE]
> C#Yerine JavaScript, Visual Basic veya C++ özel dönüşüm bileşenini kullanmak için de kullanabilirsiniz.

Çoğu durumda, Windows Çalışma Zamanı oluşturmak için/CX C++kullanabilirsiniz. Ancak, bazen WRL 'yi kullanmanız gerekir. Örneğin, Microsoft Medya Altyapısı için bir medya uzantısı oluşturduğunuzda hem COM hem de Windows Çalışma Zamanı arabirimlerini uygulayan bir bileşen oluşturmanız gerekir. /CX C++yalnızca Windows çalışma zamanı nesneler oluşturabileceğinden, bir medya uzantısı oluşturmak için, hem com hem de Windows çalışma zamanı arabirimlerinin uygulanmasını sağladığından WRL 'yi kullanmanız gerekir.

> [!NOTE]
> Bu kod örneği uzun olsa da, faydalı bir Medya Altyapısı dönüşümü oluşturmak için gereken en düşük değeri gösterir. Kendi özel dönüştürüyorsunuz için bir başlangıç noktası olarak kullanabilirsiniz. Bu örnek Medya Uzantıları [örneğinden](https://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)uyarlanmıştır, bu, video için etkileri uygulamak, video kodunu çözmek ve medya akışları üreten düzen işleyicileri oluşturmak için medya uzantıları 'nı kullanır.

## <a name="prerequisites"></a>Önkoşullar

- Visual Studio 2017 ve üzeri sürümlerde UWP desteği isteğe bağlı bir bileşendir. Yüklemek için, Windows Başlat menüsünden Visual Studio Yükleyicisi açın ve Visual Studio sürümünüzü bulun. **Değiştir** ' i seçin ve ardından **Evrensel Windows platformu geliştirme** kutucuğunun işaretli olduğundan emin olun. **İsteğe bağlı bileşenler** altında, Visual Studio 2017 için  **C++ UWP (v141) için Araçlar** veya  **C++ Visual Studio 2019 için UWP (v142) araçları** ' na bakın. Ardından, kullanmak istediğiniz Windows SDK sürümünü denetleyin.

- [Windows çalışma zamanı](/uwp/api/)deneyim.

- COM ile deneyim.

- Bir Web kamerası.

## <a name="key-points"></a>Önemli noktalar

- Özel bir Medya Altyapısı bileşeni oluşturmak için bir arabirim tanımlamak için bir Microsoft Arabirim Tanımlama Dili (MıDL) tanım dosyası kullanın, bu arabirimi uygulayın ve ardından diğer bileşenlerden etkinleştirilebilir yapın.

- `namespace` ve `runtimeclass` öznitelikleri ve `NTDDI_WIN8`[Version](/windows/win32/Midl/version) özniteliği değeri, WRL kullanan bir medya Altyapısı bileşeni için MIDL tanımının önemli bölümlerinden oluşur.

- [Microsoft:: WRL:: RuntimeClass](runtimeclass-class.md) , özel medya Altyapısı bileşeni için temel sınıftır. Şablon bağımsız değişkeni olarak sunulan [Microsoft:: WRL:: RuntimeClassType:: WinRtClassicComMix](runtimeclasstype-enumeration.md) Enum değeri, hem Windows çalışma zamanı sınıfı hem de klasik com çalışma zamanı sınıfı olarak kullanılacak sınıfı işaretler.

- [InspectableClass](inspectableclass-macro.md) makrosu, başvuru sayma ve `QueryInterface` yöntemi gıbı temel com işlevlerini uygular ve çalışma zamanı sınıf adını ve güven düzeyini ayarlar.

- [DllGetActivationFactory](/windows/win32/winrt/functions), [DllCanUnloadNow](/windows/win32/api/combaseapi/nf-combaseapi-dllcanunloadnow)ve [DllGetClassObject](/windows/win32/api/combaseapi/nf-combaseapi-dllgetclassobject)gibi DLL giriş noktası işlevleri uygulamak için Microsoft:: WRL::[module sınıfını](module-class.md) kullanın.

- Component DLL 'nizi Runtimeobject. lib öğesine bağlayın. Windows meta verileri oluşturmak için bağlayıcı satırında [/winmd](../../cppcx/compiler-and-linker-options-c-cx.md) de belirtin.

- WRL bileşenlerini UWP uygulamaları için erişilebilir hale getirmek için proje başvurularını kullanın.

### <a name="to-use-the-wrl-to-create-the-media-foundation-grayscale-transform-component"></a>Medya Altyapısı gri tonlamalı dönüştürme bileşeni oluşturmak için WRL 'yi kullanmak için

1. Visual Studio 'da **boş bir çözüm** projesi oluşturun. Projeyi, örneğin, *MediaCapture*gibi adlandırın.

1. Çözüme bir **dll (Evrensel Windows)** projesi ekleyin. Projeyi, örneğin, *Griscaletransform*gibi adlandırın.

1. Projeye bir **MIDL dosya (. IDL)** dosyası ekleyin. Dosyayı adlandırın, örneğin, *Griscaletransform. IDL*.

1. Bu kodu Griscaletransform. IDL öğesine ekleyin:

   [!code-cpp[wrl-media-capture#1](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_1.idl)]

1. `pch.h`içeriğini değiştirmek için aşağıdaki kodu kullanın:

   [!code-cpp[wrl-media-capture#2](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_2.h)]

1. Projeye yeni bir üst bilgi dosyası ekleyin, `BufferLock.h`adlandırın ve ardından içeriği şu kodla değiştirin:

   [!code-cpp[wrl-media-capture#3](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_3.h)]

1. Bu örnekte `GrayscaleTransform.h` kullanılmıyor. İsterseniz bunu projeden kaldırabilirsiniz.

1. `GrayscaleTransform.cpp`içeriğini değiştirmek için aşağıdaki kodu kullanın:

   [!code-cpp[wrl-media-capture#4](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_4.cpp)]

1. Projeye yeni bir modül tanımı dosyası ekleyin, `GrayscaleTransform.def`adlandırın ve ardından şu kodu ekleyin:

   ```
   EXPORTS
       DllCanUnloadNow                     PRIVATE
       DllGetActivationFactory             PRIVATE
       DllGetClassObject                   PRIVATE
   ```

1. `dllmain.cpp`içeriğini değiştirmek için aşağıdaki kodu kullanın:

   [!code-cpp[wrl-media-capture#6](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_6.cpp)]

1. Projenin **Özellik sayfaları** iletişim kutusunda, aşağıdaki **bağlayıcı** özelliklerini ayarlayın.

   1. **Giriş**altında, **modül tanım dosyası**için `GrayScaleTransform.def`belirtin.

   1. Ayrıca **giriş**altında, **ek bağımlılıklar** özelliğine `runtimeobject.lib`, `mfuuid.lib`ve `mfplat.lib` ekleyin.

   1. **Windows meta verileri**altında, **Windows meta verilerini oluştur** seçeneğini **Evet (/WinMD)** olarak ayarlayın.

### <a name="to-use-the-wrl-the-custom-media-foundation-component-from-a-c-app"></a>C# Uygulamadan özel medya altyapısı bileşenini kullanmak için

1. `MediaCapture` çözümüne yeni  **C# bir boş uygulama (Evrensel Windows)** projesi ekleyin. Projeyi, örneğin, *MediaCapture*gibi adlandırın.

1. **MediaCapture** projesinde `GrayscaleTransform` projesine bir başvuru ekleyin. Nasıl yapılacağını öğrenmek için bkz. [nasıl yapılır: başvuru Yöneticisi 'Ni kullanarak başvuru ekleme veya kaldırma](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager).

1. `Package.appxmanifest`, **yetenekler** sekmesinde **mikrofon** ve **Web Kamerası**' ı seçin. Web kamerasından fotoğraf yakalamak için her iki özellik de gereklidir.

1. `MainPage.xaml`, bu kodu kök [kılavuz](/uwp/api/Windows.UI.Xaml.Controls.Grid) öğesine ekleyin:

   [!code-xml[wrl-media-capture#7](../codesnippet/Xaml/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_7.xaml)]

1. `MainPage.xaml.cs`içeriğini değiştirmek için aşağıdaki kodu kullanın:

   [!code-cs[wrl-media-capture#8](../codesnippet/CSharp/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_8.cs)]

Aşağıdaki çizimde `MediaCapture app`gösterilmektedir.

![Bir fotoğrafı yakalayan MediaCapture uygulaması](../media/wrl_media_capture.png "WRL_Media_Capture")

## <a name="next-steps"></a>Sonraki Adımlar

Örnek, tek seferde varsayılan Web kamerasından fotoğrafların nasıl yakalanacağını göstermektedir. [Medya Uzantıları örneği](https://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096) daha fazlasını yapar. Web Kamerası cihazlarının nasıl numaralandırılacağını ve yerel düzen işleyicileriyle nasıl çalışabileceğinizi ve hem tek tek fotoğraflarda hem de video akışında çalışan ek medya efektlerini gösterir.

## <a name="see-also"></a>Ayrıca bkz.

[Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](windows-runtime-cpp-template-library-wrl.md)<br/>
[Microsoft Medya Altyapısı](/windows/win32/medfound/microsoft-media-foundation-sdk)<br/>
[Medya Uzantıları örneği](https://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)
