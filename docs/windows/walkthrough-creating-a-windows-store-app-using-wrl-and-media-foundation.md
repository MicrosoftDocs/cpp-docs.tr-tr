---
title: "İzlenecek yol: WRL ve medya altyapısı kullanarak bir Windows mağazası uygulaması oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: 0336c550-fbeb-4dc4-aa9b-660f9fc45382
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: eb26f38ece8c098e6f10ba2ec90738787cb20ff3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation"></a>İzlenecek yol: WRL ve Medya Altyapısı kullanarak Windows Mağazası uygulaması oluşturma
Windows çalışma zamanı C++ Şablon kitaplığı (WRL) kullanan bir evrensel Windows Platform uygulaması oluşturmak için nasıl kullanılacağını öğrenin [Microsoft Media Foundation](http://msdn.microsoft.com/library/windows/apps/ms694197).  
  
 Bu örnek bir Web kamerası yakalanan görüntüleri gri tonlamalı etkisi uygulandığı özel bir Media Foundation dönüştürme oluşturur. Uygulamanın C++ özel dönüştürme ve yakalanan görüntülerin dönüştürmek için bileşen kullanmak için C# tanımlamak için kullanır.  
  
> [!NOTE]
>  C# yerine, ayrıca JavaScript, Visual Basic ya da C++ özel dönüştürme bileşeni kullanmak için kullanabilirsiniz.  
  

 Çoğu durumda, C + kullanabileceğiniz +/ CX Windows çalışma zamanı oluşturmak için). Ancak, bazen WRL kullanmak zorunda. Örneğin, Microsoft Media Foundation için bir medya uzantısı oluşturduğunuzda, COM ve Windows Çalışma Zamanı Modülü arabirimler uygulayan bileşeni oluşturmanız gerekir. Çünkü C + +/ CX yalnızca Windows çalışma zamanı nesneleri oluşturma, COM ve Windows Çalışma Zamanı Modülü arabirimler uyarlamasını sağladığından medya uzantısı oluşturmak için WRL kullanmanız gerekir.  

  
> [!NOTE]
>  Bu kod örneği uzun olsa da, yararlı Media Foundation dönüşüm oluşturmak için gerekli olan minimum gösterir. Bu, kendi özel dönüştürme için bir başlangıç noktası olarak kullanabilirsiniz. Bu örnekte gelen uyarlanmış, [medya uzantılar örneği](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)uygulamak için hangi kullanımlar media uzantıları videoya etkiler, video kod çözme ve medya akışlar üretmesi düzeni işleyicileri oluşturun.  
  
## <a name="prerequisites"></a>Önkoşullar  
  
-   İle deneyimi [Windows çalışma zamanı](http://msdn.microsoft.com/library/windows/apps/br211377.aspx).  
  
-   COM deneyimi  
  
-   Bir Web kamerası.  
  
## <a name="key-points"></a>Önemli noktalar  
  
-   Özel bir Media Foundation bileşen oluşturmak için bir arabirim tanımlayın, o arabirimini uygulayan ve diğer bileşenler'den activatable yapın sonra Microsoft arabirimi tanım dili (MIDL) tanım dosyası kullanın.  
  
-   `namespace` Ve `runtimeclass` öznitelikleri ve `NTDDI_WIN8` [sürüm](http://msdn.microsoft.com/en-us/66ac5cf3-2230-44fd-aaf6-8013e4a4ae81) öznitelik değeri olan WRL kullanan bir Media Foundation bileşeni MIDL tanımı önemli kısımlarını.  
  
-   [Microsoft::WRL::RuntimeClass](../windows/runtimeclass-class.md) özel Media Foundation bileşeni için temel sınıftır. [Microsoft::WRL::RuntimeClassType::WinRtClassicComMix](../windows/runtimeclasstype-enumeration.md) şablon bağımsız değişken sağlanan enum değeri sınıfı kullanılmak üzere bir Windows çalışma zamanı sınıf hem klasik COM çalışma zamanı sınıf olarak işaretler.  
  
-   [Inspectableclass](../windows/inspectableclass-macro.md) makrosu başvuru sayımı gibi temel COM işlevlerini uygular ve `QueryInterface` yöntemi ve çalışma zamanı sınıf adı ve güven düzeyi ayarlar.  
  
-   Microsoft::WRL kullanmak::[modül sınıfı](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/b4acf5de-2f4c-4c8b-b5ff-9140d023ecbe/locales/en-US) DLL giriş noktası işlevleri gibi uygulamak için [DllGetActivationFactory](http://msdn.microsoft.com/library/br205771.aspx), [DllCanUnloadNow](http://msdn.microsoft.com/library/windows/desktop/ms690368\(v=vs.85\).aspx), ve [ DllGetClassObject](http://msdn.microsoft.com/library/windows/desktop/ms680760\(v=vs.85\).aspx).  
  
-   Bileşeniniz DLL için runtimeobject.lib bağlayın. Ayrıca belirtin [/WINMD](../cppcx/compiler-and-linker-options-c-cx.md) bağlayıcı satırındaki Windows meta verileri oluşturun.  
  
-   WRL bileşenlerinin Evrensel Windows platformu uygulamaları için erişilebilir hale getirmek için proje başvuruları kullanın.  
  
### <a name="to-use-the-wrl-to-create-the-media-foundation-grayscale-transform-component"></a>WRL Media Foundation gri tonlamalı oluşturmak için kullanılacak bileşen dönüştürme  
  
1.  Visual Studio'da oluşturma bir **boş çözüm** projesi. Örneğin, proje adı `MediaCapture`.  
  
2.  Ekleme bir **DLL (Windows mağazası uygulamaları)** çözüme proje. Örneğin, proje adı `GrayscaleTransform`.  
  
3.  Ekleme bir **MIDL dosya (.idl)** projesine dosyasını. Örneğin, dosya adı `GrayscaleTransform.idl`.  
  
4.  Bu kodu GrayscaleTransform.idl için ekleyin.  
  
     [!code-cpp[wrl-media-capture#1](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_1.idl)]  
  
5.  Pch.h içeriğini değiştirmek için aşağıdaki kodu kullanın.  
  
     [!code-cpp[wrl-media-capture#2](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_2.h)]  
  
6.  Yeni bir üstbilgi dosyası projeye ekleyin, adlandırın `BufferLock.h`ve ardından bu kodu ekleyin:  
  
     [!code-cpp[wrl-media-capture#3](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_3.h)]  
  
7.  Bu örnekte GrayscaleTransform.h kullanılmaz. İsterseniz, projeden kaldırabilirsiniz.  
  
8.  GrayscaleTransform.cpp içeriğini değiştirmek için aşağıdaki kodu kullanın.  
  
     [!code-cpp[wrl-media-capture#4](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_4.cpp)]  
  
9. Yeni bir modül tanım dosyası projeye ekleyin, adlandırın `GrayscaleTransform.def`ve ardından bu kodu ekleyin:  
  
   ```
   EXPORTS
       DllCanUnloadNow                     PRIVATE
       DllGetActivationFactory             PRIVATE
       DllGetClassObject                   PRIVATE
   ```   
  
10. DllMain.cpp'yi içeriğini değiştirmek için aşağıdaki kodu kullanın.  
  
     [!code-cpp[wrl-media-capture#6](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_6.cpp)]  
  
11. Projenin **özellik sayfaları** iletişim kutusunda, aşağıdakileri ayarlayın **bağlayıcı** özellikleri.  
  
    1.  Altında **giriş**, için **modül tanım dosyası**, belirtin `GrayScaleTransform.def`.  
  
    2.  Ayrıca altında **giriş**, ekleme `runtimeobject.lib`, `mfuuid.lib`, ve `mfplatf.lib` için **ek bağımlılıklar** özelliği.  
  
    3.  Altında **Windows meta verileri**ayarlayın **oluşturmak Windows Meta** için **Evet (/ WINMD)**.  
  
### <a name="to-use-the-wrl-the-custom-media-foundation-component-from-a-c-app"></a>C# uygulamasından özel Media Foundation bileşeni WRL kullanmak için  
  
1.  Yeni bir ekleme **C# boş uygulama (XAML)** için proje `MediaCapture` çözümü. Örneğin, proje adı `MediaCapture`.  
  
2.  İçinde **MediaCapture** proje, bir başvuru ekleyin `GrayscaleTransform` projesi. Bilgi edinmek için bkz [nasıl yapılır: başvuru ekleme veya kaldırma başvuru Yöneticisi'ni kullanarak](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager).  
  
3.  Package.appxmanifest içinde üzerinde **yetenekleri** sekmesine **mikrofon** ve **Web kamerası**. Her iki özelliği de Web kamerası gelen fotoğraf yakalamak için gereklidir.  
  
4.  MainPage.xaml içinde kök bu kodu ekleyin [kılavuz](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.grid.aspx) öğe:  
  
     [!code-xml[wrl-media-capture#7](../windows/codesnippet/Xaml/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_7.xaml)]  
  
5.  MainPage.xaml.cs içeriğini değiştirmek için aşağıdaki kodu kullanın.  
  
     [!code-cs[wrl-media-capture#8](../windows/codesnippet/CSharp/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_8.cs)]  
  
 Aşağıdaki çizimde MediaCapture uygulamayı gösterir.  
  
 ![Fotoğraf yakalama MediaCapture uygulama](../windows/media/wrl_media_capture.png "WRL_Media_Capture")  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Örnek, varsayılan Web kamerası bir gelen fotoğraf aynı anda yakalama gösterilmektedir. [Medya uzantılar örneği](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096) daha fazlasını yapar. Web kamerası aygıtları numaralandırmak ve yerel düzeni işleyicileri ile çalışmak nasıl gösterir ve tek tek fotoğrafları hem video akışları iş ek medya efektleri gösterir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)   
 [Microsoft Media Foundation](http://msdn.microsoft.com/library/windows/apps/ms694197)   
 [Medya uzantılar örneği](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)