---
title: 'İzlenecek yol: WRL ve medya altyapısı kullanarak UWP uygulaması oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 0336c550-fbeb-4dc4-aa9b-660f9fc45382
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 480baaf12c332f0a293374fe2317110eb186cbdf
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39648990"
---
# <a name="walkthrough-creating-a-uwp-app-using-wrl-and-media-foundation"></a>İzlenecek yol: WRL ve medya altyapısı kullanarak UWP uygulaması oluşturma
Windows çalışma zamanı C++ Şablon kitaplığı (WRL) kullanan bir evrensel Windows Platformu (UWP) uygulaması oluşturmak için kullanmayı öğrenin [Microsoft Media Foundation](http://msdn.microsoft.com/library/windows/apps/ms694197).  
  
 Bu örnek, bir Web kamerası yakalanır görüntü gri tonlamalı etkisi uygulanacağı özel Media Foundation dönüşüm oluşturur. Uygulama, C++ özel dönüştürme ve yakalanan görüntülerin dönüştürmek için bileşeni kullanmak için C# tanımlamak için kullanır.  
  
> [!NOTE]
>  C# yerine, JavaScript, Visual Basic veya C++ özel dönüştürme bileşeni kullanmak için kullanabilirsiniz.  
  
 Çoğu durumda, C + kullanabileceğiniz +/ CX Windows çalışma zamanı oluşturma). Ancak, bazen WRL kullanmak zorunda. Örneğin, Microsoft Media Foundation için bir ortam uzantısı oluşturduğunuzda hem Windows çalışma zamanı, hem de COM arabirimleri uygulayan bir bileşen oluşturmanız gerekir. Çünkü C + +/ CX yalnızca Windows çalışma zamanı nesneleri oluşturma hem Windows çalışma zamanı, hem de COM arabirimleri uygulamasını sağladığından medya uzantısı oluşturmak için WRL kullanmalısınız.  

> [!NOTE]
>  Bu kod örneği uzun olmasına rağmen kullanışlı Media Foundation dönüşüm oluşturmak için gereken en düşük gösterir. Bunu kendi özel dönüştürme için bir başlangıç noktası olarak kullanabilirsiniz. Bu örnekte gelen uyarlanmış, [medya uzantılar örneği](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)uygulamak için hangi kullanan media uzantıları video efektleri video kod çözme ve medya akışlarının üreten düzeni işleyicileri oluşturun.  
  
## <a name="prerequisites"></a>Önkoşullar  
  
-   Deneyimini [Windows çalışma zamanı](http://msdn.microsoft.com/library/windows/apps/br211377.aspx).  
  
-   Com ile deneyimi  
  
-   Bir Web kamerası.  
  
## <a name="key-points"></a>Önemli noktalar  
  
-   Özel bir Media Foundation bileşeni oluşturmak için bir arabirim tanımlayın, bu arabirimi uygulayın ve ardından diğer bileşenlerden etkinleştirilebilir yapmak için bir Microsoft arabirim tanımı dili (MIDL) tanım dosyasını kullanın.  
  
-   `namespace` Ve `runtimeclass` öznitelikleri ve `NTDDI_WIN8` [sürüm](http://msdn.microsoft.com/66ac5cf3-2230-44fd-aaf6-8013e4a4ae81) öznitelik değeri olan önemli bölümleri WRL kullanan Media Foundation bileşen MIDL tanımı.  
  
-   [Microsoft::WRL::RuntimeClass](../windows/runtimeclass-class.md) özel Media Foundation bileşeni için temel sınıftır. [Microsoft::WRL::RuntimeClassType::WinRtClassicComMix](../windows/runtimeclasstype-enumeration.md) şablon bağımsız değişken sağlanan enum değeri, bir Windows çalışma zamanı sınıf hem klasik COM çalışma zamanı sınıf olarak kullanılacak olan sınıfını işaretler.  
  
-   [Inspectableclass](../windows/inspectableclass-macro.md) makrosu başvuru sayımı gibi temel COM işlevselliğini uygular ve `QueryInterface` yöntemi ve çalışma zamanı sınıf adı ve güven düzeyini ayarlar.  
  
-   Kullanma Microsoft::WRL::[modül sınıfı](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/b4acf5de-2f4c-4c8b-b5ff-9140d023ecbe) DLL giriş noktası işlevleri gibi uygulamak [DllGetActivationFactory](http://msdn.microsoft.com/library/br205771.aspx), [DllCanUnloadNow](http://msdn.microsoft.com/library/windows/desktop/ms690368\(v=vs.85\).aspx), ve [ DllGetClassObject](http://msdn.microsoft.com/library/windows/desktop/ms680760\(v=vs.85\).aspx).  
  
-   Bileşeniniz DLL için runtimeobject.lib bağlayın. Ayrıca belirtin [/WINMD](../cppcx/compiler-and-linker-options-c-cx.md) bağlayıcı satırında Windows meta verileri oluşturun.  
  
-   WRL bileşenlerinin UWP uygulamaları için erişilebilir hale getirmek için proje başvuruları kullanın.  
  
### <a name="to-use-the-wrl-to-create-the-media-foundation-grayscale-transform-component"></a>WRL Media Foundation gri tonlamalı oluşturmak için kullanılacak bileşen dönüştürme  
  
1.  Visual Studio'da oluşturma bir **boş çözüm** proje. Örneğin, proje adını `MediaCapture`.  
  
2.  Ekleme bir **DLL (Evrensel Windows)** çözüme bir proje. Örneğin, proje adını `GrayscaleTransform`.  
  
3.  Ekleme bir **Midl dosyası (.idl)** projeye dosya. Örneğin, dosya adını `GrayscaleTransform.idl`.  
  
4.  Bu kod için GrayscaleTransform.idl ekleyin.  
  
     [!code-cpp[wrl-media-capture#1](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_1.idl)]  
  
5.  Pch.h içeriğini değiştirmek için aşağıdaki kodu kullanın.  
  
     [!code-cpp[wrl-media-capture#2](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_2.h)]  
  
6.  Projeye yeni bir üst bilgi dosyası ekleyin, adlandırın `BufferLock.h`ve ardından bu kodu ekleyin:  
  
     [!code-cpp[wrl-media-capture#3](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_3.h)]  
  
7.  Bu örnekte GrayscaleTransform.h kullanılmaz. İsterseniz projeden kaldırın.  
  
8.  GrayscaleTransform.cpp içeriğini değiştirmek için aşağıdaki kodu kullanın.  
  
     [!code-cpp[wrl-media-capture#4](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_4.cpp)]  
  
9. Projeye yeni bir modül tanım dosyası ekleyin, adlandırın `GrayscaleTransform.def`ve ardından bu kodu ekleyin:  
  
   ```
   EXPORTS
       DllCanUnloadNow                     PRIVATE
       DllGetActivationFactory             PRIVATE
       DllGetClassObject                   PRIVATE
   ```   
  
10. Dllmain.cpp içeriğini değiştirmek için aşağıdaki kodu kullanın.  
  
     [!code-cpp[wrl-media-capture#6](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_6.cpp)]  
  
11. Projenin **özellik sayfaları** iletişim kutusunda, aşağıdakileri ayarlayın **bağlayıcı** özellikleri.  
  
    1.  Altında **giriş**, için **modül tanım dosyası**, belirtin `GrayScaleTransform.def`.  
  
    2.  Ayrıca altında **giriş**, ekleme `runtimeobject.lib`, `mfuuid.lib`, ve `mfplatf.lib` için **ek bağımlılıklar** özelliği.  
  
    3.  Altında **Windows meta verileri**ayarlayın **Windows meta verileri oluşturma** için **Evet (/ WINMD)**.  
  
### <a name="to-use-the-wrl-the-custom-media-foundation-component-from-a-c-app"></a>Bir C# uygulamasından özel Media Foundation bileşen WRL kullanmak için  
  
1.  Yeni bir **C# boş uygulama (XAML)** için proje `MediaCapture` çözüm. Örneğin, proje adını `MediaCapture`.  
  
2.  İçinde **MediaCapture** projesi, bir başvuru ekleyin `GrayscaleTransform` proje. Bilgi edinmek için bkz. nasıl [nasıl yapılır: başvurular ekleme veya kaldırma başvuru Yöneticisi'ni kullanarak](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager).  
  
3.  Package.appxmanifest, üzerinde **özellikleri** sekmesinde **mikrofon** ve **Web kamerası**. Her iki özelliği, Web kamerası gelen fotoğraf yakalamak için gereklidir.  
  
4.  MainPage.xaml içinde kök bu kodu ekleyin [kılavuz](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.grid.aspx) öğesi:  
  
     [!code-xml[wrl-media-capture#7](../windows/codesnippet/Xaml/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_7.xaml)]  
  
5.  MainPage.xaml.cs içeriğini değiştirmek için aşağıdaki kodu kullanın.  
  
     [!code-cs[wrl-media-capture#8](../windows/codesnippet/CSharp/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_8.cs)]  
  
 Aşağıdaki çizim MediaCapture uygulamayı gösterir.  
  
 ![Fotoğraf yakalama MediaCapture uygulama](../windows/media/wrl_media_capture.png "WRL_Media_Capture")  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Örnekte, varsayılan Web kamerası bir gelen fotoğrafları aynı anda yakalama gösterilmektedir. [Medya uzantılar örneği](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096) daha fazlasını yapar. Web kamerası cihazları listeleme ve yerel düzeni işleyicilerle iş yapmayı gösteren ve bireysel fotoğraf ve video akışları çalışma ek medya efektleri gösterir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)   
 [Microsoft Media Foundation](http://msdn.microsoft.com/library/windows/apps/ms694197)   
 [Medya uzantılar örneği](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)