---
title: 'İzlenecek yol: WRL ve medya altyapısı kullanarak UWP uygulaması oluşturma'
ms.date: 09/17/2018
ms.topic: reference
ms.assetid: 0336c550-fbeb-4dc4-aa9b-660f9fc45382
ms.openlocfilehash: e0254be8c6fa185f75c46898d4da51742195550a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59036042"
---
# <a name="walkthrough-creating-a-uwp-app-using-wrl-and-media-foundation"></a>İzlenecek yol: WRL ve medya altyapısı kullanarak UWP uygulaması oluşturma

Windows çalışma zamanı C++ Şablon kitaplığı (WRL) kullanan bir evrensel Windows Platformu (UWP) uygulaması oluşturmak için kullanmayı öğrenin [Microsoft Media Foundation](/windows/desktop/medfound/microsoft-media-foundation-sdk).

Bu örnek, bir Web kamerası yakalanır görüntü gri tonlamalı etkisi uygulanacağı özel Media Foundation dönüşüm oluşturur. Uygulama, C++ özel dönüştürme ve yakalanan görüntülerin dönüştürmek için bileşeni kullanmak için C# tanımlamak için kullanır.

> [!NOTE]
> C# yerine, JavaScript, Visual Basic veya C++ özel dönüştürme bileşeni kullanmak için kullanabilirsiniz.

Çoğu durumda, C + kullanabileceğiniz +/ CX Windows çalışma zamanı oluşturma. Ancak, bazen WRL kullanmak zorunda. Örneğin, Microsoft Media Foundation için bir ortam uzantısı oluşturduğunuzda hem Windows çalışma zamanı, hem de COM arabirimleri uygulayan bir bileşen oluşturmanız gerekir. Çünkü C + +/ CX yalnızca Windows çalışma zamanı nesneleri oluşturma hem Windows çalışma zamanı, hem de COM arabirimleri uygulamasını sağladığından medya uzantısı oluşturmak için WRL kullanmalısınız.

> [!NOTE]
> Bu kod örneği uzun olmasına rağmen kullanışlı Media Foundation dönüşüm oluşturmak için gereken en düşük gösterir. Bunu kendi özel dönüştürme için bir başlangıç noktası olarak kullanabilirsiniz. Bu örnekte gelen uyarlanmış, [medya uzantılar örneği](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)uygulamak için hangi kullanan media uzantıları video efektleri video kod çözme ve medya akışlarının üreten düzeni işleyicileri oluşturun.

## <a name="prerequisites"></a>Önkoşullar

- Deneyimini [Windows çalışma zamanı](https://msdn.microsoft.com/library/windows/apps/br211377.aspx).

- Com ile deneyimi

- Bir Web kamerası.

## <a name="key-points"></a>Önemli noktalar

- Özel bir Media Foundation bileşeni oluşturmak için bir arabirim tanımlayın, bu arabirimi uygulayın ve ardından diğer bileşenlerden etkinleştirilebilir yapmak için bir Microsoft arabirim tanımı dili (MIDL) tanım dosyasını kullanın.

- `namespace` Ve `runtimeclass` öznitelikleri ve `NTDDI_WIN8` [sürüm](/windows/desktop/Midl/version) öznitelik değeri olan önemli bölümleri WRL kullanan Media Foundation bileşen MIDL tanımı.

- [Microsoft::WRL::RuntimeClass](runtimeclass-class.md) özel Media Foundation bileşeni için temel sınıftır. [Microsoft::WRL::RuntimeClassType::WinRtClassicComMix](runtimeclasstype-enumeration.md) şablon bağımsız değişken sağlanan enum değeri, bir Windows çalışma zamanı sınıf hem klasik COM çalışma zamanı sınıf olarak kullanılacak olan sınıfını işaretler.

- [Inspectableclass](inspectableclass-macro.md) makrosu başvuru sayımı gibi temel COM işlevselliğini uygular ve `QueryInterface` yöntemi ve çalışma zamanı sınıf adı ve güven düzeyini ayarlar.

- Kullanma Microsoft::WRL::[modül sınıfı](module-class.md) DLL giriş noktası işlevleri gibi uygulamak [DllGetActivationFactory](https://msdn.microsoft.com/library/br205771.aspx), [DllCanUnloadNow](/windows/desktop/api/combaseapi/nf-combaseapi-dllcanunloadnow), ve [ DllGetClassObject](/windows/desktop/api/combaseapi/nf-combaseapi-dllgetclassobject).

- Bileşeniniz DLL için runtimeobject.lib bağlayın. Ayrıca belirtin [/WINMD](../../cppcx/compiler-and-linker-options-c-cx.md) bağlayıcı satırında Windows meta verileri oluşturun.

- WRL bileşenlerinin UWP uygulamaları için erişilebilir hale getirmek için proje başvuruları kullanın.

### <a name="to-use-the-wrl-to-create-the-media-foundation-grayscale-transform-component"></a>WRL Media Foundation gri tonlamalı oluşturmak için kullanılacak bileşen dönüştürme

1. Visual Studio'da oluşturma bir **boş çözüm** proje. Örneğin, proje adını *MediaCapture*.

1. Ekleme bir **DLL (Evrensel Windows)** çözüme bir proje. Örneğin, proje adını *GrayscaleTransform*.

1. Ekleme bir **Midl dosyası (.idl)** projeye dosya. Örneğin, dosya adını *GrayscaleTransform.idl*.

1. GrayscaleTransform.idl için şu kodu ekleyin:

   [!code-cpp[wrl-media-capture#1](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_1.idl)]

1. İçeriğini değiştirmek için aşağıdaki kodu kullanın `pch.h`:

   [!code-cpp[wrl-media-capture#2](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_2.h)]

1. Projeye yeni bir üst bilgi dosyası ekleyin, adlandırın `BufferLock.h`ve ardından içerikleri şu kodla değiştirin:

   [!code-cpp[wrl-media-capture#3](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_3.h)]

1. `GrayscaleTransform.h` Bu örnekte kullanılmaz. İsterseniz projeden kaldırın.

1. İçeriğini değiştirmek için aşağıdaki kodu kullanın `GrayscaleTransform.cpp`:

   [!code-cpp[wrl-media-capture#4](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_4.cpp)]

1. Projeye yeni bir modül tanım dosyası ekleyin, adlandırın `GrayscaleTransform.def`ve ardından bu kodu ekleyin:

   ```
   EXPORTS
       DllCanUnloadNow                     PRIVATE
       DllGetActivationFactory             PRIVATE
       DllGetClassObject                   PRIVATE
   ```

1. İçeriğini değiştirmek için aşağıdaki kodu kullanın `dllmain.cpp`:

   [!code-cpp[wrl-media-capture#6](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_6.cpp)]

1. Projenin **özellik sayfaları** iletişim kutusunda, aşağıdakileri ayarlayın **bağlayıcı** özellikleri.

   1. Altında **giriş**, için **modül tanım dosyası**, belirtin `GrayScaleTransform.def`.

   1. Ayrıca altında **giriş**, ekleme `runtimeobject.lib`, `mfuuid.lib`, ve `mfplat.lib` için **ek bağımlılıklar** özelliği.

   1. Altında **Windows meta verileri**ayarlayın **Windows meta verileri oluşturma** için **Evet (/ WINMD)**.

### <a name="to-use-the-wrl-the-custom-media-foundation-component-from-a-c-app"></a>Bir C# uygulamasından özel Media Foundation bileşen WRL kullanmak için

1. Yeni bir **C# boş uygulama (Evrensel Windows)** için proje `MediaCapture` çözüm. Örneğin, proje adını *MediaCapture*.

1. İçinde **MediaCapture** projesi, bir başvuru ekleyin `GrayscaleTransform` proje. Bilgi edinmek için bkz. nasıl [nasıl yapılır: Başvurular ekleme veya kaldırma başvuru Yöneticisi'ni kullanarak](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager).

1. İçinde `Package.appxmanifest`, **özellikleri** sekmesinde **mikrofon** ve **Web kamerası**. Her iki özelliği, Web kamerası gelen fotoğraf yakalamak için gereklidir.

1. İçinde `MainPage.xaml`, kök bu kodu ekleyin [kılavuz](https://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.grid.aspx) öğesi:

   [!code-xml[wrl-media-capture#7](../codesnippet/Xaml/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_7.xaml)]

1. İçeriğini değiştirmek için aşağıdaki kodu kullanın `MainPage.xaml.cs`:

   [!code-cs[wrl-media-capture#8](../codesnippet/CSharp/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_8.cs)]

Aşağıdaki çizimde gösterildiği `MediaCapture app`.

![Fotoğraf yakalama MediaCapture uygulama](../media/wrl_media_capture.png "WRL_Media_Capture")

## <a name="next-steps"></a>Sonraki Adımlar

Örnekte, varsayılan Web kamerası bir gelen fotoğrafları aynı anda yakalama gösterilmektedir. [Medya uzantılar örneği](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096) daha fazlasını yapar. Web kamerası cihazları listeleme ve yerel düzeni işleyicilerle iş yapmayı gösteren ve bireysel fotoğraf ve video akışları çalışma ek medya efektleri gösterir.

## <a name="see-also"></a>Ayrıca bkz.

[Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](windows-runtime-cpp-template-library-wrl.md)<br/>
[Microsoft Media Foundation](/windows/desktop/medfound/microsoft-media-foundation-sdk)<br/>
[Medya uzantılar örneği](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)