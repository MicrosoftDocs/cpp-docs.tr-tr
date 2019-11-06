---
title: Evrensel Windows Platformu’na bağlantı noktası oluşturma (C++)
ms.date: 10/23/2019
ms.assetid: f662d2e4-8940-418d-8109-cb76cb8f8569
ms.openlocfilehash: 9314cb564e792a7d4949d422a3942e9d46a23cb2
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627201"
---
# <a name="porting-to-the-universal-windows-platform-c"></a>Evrensel Windows Platformu’na bağlantı noktası oluşturma (C++)

Bu konuda, var olan C++ kodun Windows 10 uygulama platformunda bağlantı noktası oluşturma hakkında bilgi edinebilirsiniz Evrensel Windows platformu. *Evrensel* terimi, kodunuzun Windows 10 çalıştıran cihazlarda çalıştırılabileceği anlamına gelir. Windows 10 çalıştıran tüm cihazlarda iyi çalışan tek bir proje ve tek bir XAML temel kullanıcı arabirimi oluşturursunuz. Uygulamanın kullanıcı arabiriminin farklı görüntü boyutlarına uyum sağlamasına izin vermek için XAML 'deki dinamik düzen özelliklerini kullanabilirsiniz.

Windows Geliştirme Merkezi belgeleri, Evrensel Windows Platformu Windows 8.1 uygulamaları taşıma kılavuzunu içerir. Bkz. [Windows çalışma zamanı 8 ' den UWP 'e taşıma](/windows/uwp/porting/w8x-to-uwp-root). Kılavuz genellikle C# koda odaklansa da, kılavuzun çoğu için C++geçerlidir. Aşağıdaki yordamlar daha ayrıntılı bilgiler içerir. Ayrıca bkz. [bir masaüstü UYGULAMASıNDAN UWP 'ye geçme](/windows/uwp/porting/desktop-to-uwp-migrate).

Bu konu, kodu UWP 'ye taşıma için aşağıdaki yordamları içerir.

- [Windows 8.1 Mağazası uygulamasını UWP 'e taşıma](#BK_81StoreApp)

- [Windows 8.1 çalışma zamanı bileşenini UWP 'e taşıma](#BK_81Component)

Klasik bir Masaüstü Win32 DLL 'SI varsa ve bunu bir UWP uygulamasından çağırmak istiyorsanız, bunu da yapabilirsiniz. Bu tür yordamları kullanarak, mevcut bir klasik Windows Masaüstü C++ uygulaması veya platformlar arası standart C++ kodunuz için UWP Kullanıcı arabirimi katmanı oluşturabilirsiniz. Bkz. [nasıl yapılır: mevcut C++ kodu bir Evrensel Windows platformu uygulamasında kullanma](../porting/how-to-use-existing-cpp-code-in-a-universal-windows-platform-app.md). 

## <a name="BK_81StoreApp"></a>Windows 8.1 Mağazası uygulamasını UWP 'e taşıma

Bir Windows 8.1 mağazası uygulamanız varsa, bu yordamı kullanarak UWP üzerinde ve Windows 10 çalıştıran herhangi bir cihazda çalışır hale getirebilirsiniz.  İlk olarak, derleyici ve kitaplıklardaki değişikliklerden kaynaklanan sorunları ortadan kaldırmak için Visual Studio 2019 ile projeyi bir Windows 8.1 projesi olarak derlemek iyi bir fikirdir. Bunu yaptıktan sonra, bunu bir Windows 10 UWP projesine dönüştürmenin iki yolu vardır. En kolay yol (aşağıdaki yordamda açıklandığı gibi), bir Evrensel Windows projesi oluşturmak ve var olan kodunuzu buna kopyalamak için kullanılır. Windows 8.1 Masaüstü ve Windows 8.1 telefon için evrensel bir proje kullanıyorsanız, projeniz XAML 'de iki farklı düzen ile başlar, ancak görüntüleme boyutuna göre ayarlayan tek bir dinamik düzen ile biter.

### <a name="to-port-a-windows-81-store-app-to-the-uwp"></a>UWP 'ye bir Windows 8.1 Mağazası uygulaması için bağlantı noktası oluşturma

1. Daha önce yapmadıysanız, Visual Studio 2017 ' de Windows 8.1 uygulama projenizi açın ve proje dosyasını yükseltmek için yönergeleri izleyin.

   **Visual Studio kurulumunda Windows 8.1 araçları** 'nı yüklemeniz gerekir. Bu araçlar yüklü değilse, **Visual Studio** kurulumunu **Programlar ve Özellikler** penceresinden başlatın, **Visual Studio 2017**' i seçin ve kurulum penceresinde **Değiştir**' i seçin. **Windows 8.1 araçlarını**bulun, seçili olduğundan emin olun ve **Tamam**' ı seçin.

1. **Proje özellikleri** penceresini açın ve **genel** > altında **C++** , **platform araç takımını** , Visual Studio 2017 için araç takımını **v141**olarak ayarlayın.

1. Projeyi bir Windows 8.1 projesi olarak derleyin ve derleme hatalarını çözün. Bu aşamada oluşan tüm hatalar, büyük olasılıkla derleme araçlarındaki ve kitaplıklardaki önemli değişikliklerden kaynaklanır. Kodunuzu etkileyebilecek değişikliklerin ayrıntılı bir açıklaması için bkz. [görsel C++ değişiklik geçmişi 2003-2015](../porting/visual-cpp-change-history-2003-2015.md) .

   Projeniz düzgün bir şekilde oluşturulduktan sonra, Evrensel Windows (Windows 10) için bağlantı noktası oluşturmaya hazırlanın.

1. Boş şablonu kullanarak yeni bir Evrensel Windows uygulaması projesi oluşturun. Projenin farklı dizinlerde olması gerekir, ancak bu, mevcut projenizle aynı adı vermek isteyebilirsiniz.

1. Çözümü kapatın ve sonra **Windows Gezgini** 'ni veya komut satırını kullanarak, 1. adımda oluşturduğunuz projenin proje dosyası (. vcxproj) ile aynı klasöre kod dosyalarını (Extensions. cpp,. h ve. xaml Windows 8.1) kopyalayın. Package. appxmanifest dosyasını kopyalamayın ve Windows 8.1 Masaüstü ve telefon için ayrı bir kodunuz varsa, önce bunlardan birini bağlantı noktası olarak seçin (daha sonra başka bir iş yapmak için daha sonra başka bir iş yapmanız gerekir). Ve alt klasörleri ve bunların içeriğini kopyalamayı unutmayın. İstenirse, yinelenen adlara sahip tüm dosyaları değiştirmeyi seçin.

1. Çözümü yeniden açın ve proje düğümünün kısayol menüsünden > **var olan öğeyi** **Ekle** ' yi seçin. Zaten projenin parçası olan herhangi biri dışında kopyaladığınız tüm dosyaları seçin.

   Tüm alt klasörleri denetleyin ve dosyaları da bunlara eklediğinizden emin olun.

1. Eski projenizde aynı proje adını kullanmıyorsanız, Package. appxmanifest dosyasını açın ve **giriş noktasını** `App` sınıfının ad alanı adını yansıtacak şekilde güncelleştirin.

   Package. appxmanifest dosyasındaki **giriş noktası** alanı, `App` sınıfını içeren ad alanını içeren `App` sınıfı için kapsamlı bir ad içerir. Bir Evrensel Windows projesi oluşturduğunuzda, ad alanı projenin adına ayarlanır. Bu, eski projenizden kopyaladığınız dosyalardaki verilerden farklıysa, bunların eşleşmesini sağlamak için bir veya diğerini güncelleştirmeniz gerekir.

1. Windows SDK farklı sürümleri arasındaki son değişiklikler nedeniyle projeyi derleyin ve derleme hatalarını çözün.

1. Projeyi yerel masaüstünde çalıştırın. Dağıtım hatası olmadığını ve uygulamanın düzeninin masaüstüne doğru şekilde göründüğünü ve BT 'nin düzgün çalıştığını doğrulayın.

1. Windows Phone 8,1 gibi başka bir cihaz için ayrı kod dosyalarınız ve. xaml olsaydıysanız, bu kodu inceleyin ve standart cihazdan farklı olan yeri tespit edin. Fark yalnızca düzendeyise, ekranın boyutuna bağlı olarak ekranı özelleştirmek için XAML 'de bir **görsel durum Yöneticisi** kullanabilirsiniz. Diğer farklılıklar için aşağıdaki #if deyimlerini kullanarak kodunuzda koşullar bölümünü kullanabilirsiniz.

    ```cpp
    #if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PC_APP)
    #if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PHONE_APP)
    #if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_APP)
    #if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_DESKTOP)
    ```

   Bu deyimler sırasıyla UWP uygulamalarına, Windows Phone mağaza uygulamalarına, her ikisine de veya hiçbirine (yalnızca Klasik Win32 Masaüstü) uygulanır. Bu makrolar yalnızca Windows SDK 8,1 ve üzeri sürümlerde kullanılabilir. bu nedenle, kodunuzun önceki Windows SDK veya Windows 'un diğer platformları ile derlenmesi gerekiyorsa, bunların hiçbirinin tanımlanmaması durumunda da göz önünde bulundurmanız gerekir.

1. Uygulamanızın desteklediği her cihaz türü için bir öykünücü veya fiziksel cihazda uygulamayı çalıştırın ve hata ayıklayın. Bir öykünücü çalıştırmak için, Visual Studio 'Yu bir sanal makinede değil fiziksel bir bilgisayarda çalıştırmanız gerekir.

## <a name="BK_81Component"></a>Windows 8.1 çalışma zamanı bileşenini UWP 'e taşıma

Windows 8.1 Store uygulamalarıyla zaten çalışan bir DLL veya Windows Çalışma Zamanı bileşeni varsa, bu yordamı kullanarak bir bileşeni veya DLL 'yi UWP ve Windows 10 ' da çalışır durumda bulabilirsiniz. Temel yordam, yeni bir proje oluşturmak ve kodunuzu buna kopyalamak için kullanılır.

### <a name="to-port-a-windows-81-runtime-component-to-the-uwp"></a>Windows 8.1 çalışma zamanı bileşenini UWP 'e bağlamak için

1. Visual Studio 2017 ' deki **Yeni proje** Iletişim kutusunda **Windows Universal** düğümünü bulun. Bu düğümü görmüyorsanız, önce [Windows 10 SDK 'yı](https://developer.microsoft.com/windows/downloads/windows-10-sdk) yüklemeniz gerekir. **Windows çalışma zamanı bileşen** şablonunu seçin, bileşeniniz için bir ad verin ve **Tamam** düğmesini seçin. Bileşen adı ad alanı adı olarak kullanılır, bu nedenle eski projelerinizin ad alanıyla aynı adı kullanmak isteyebilirsiniz. Bu, projeyi eski bir klasörde farklı bir klasörde oluşturmanızı gerektirir. Farklı bir ad seçerseniz, oluşturulan kod dosyalarındaki ad alanı adını güncelleştirebilirsiniz.

1. Projeyi kapatın.

1. Tüm kod dosyalarını (. cpp,. h,. xaml, vb.) Windows 8.1 bileşeninizden yeni oluşturduğunuz projenize kopyalayın. Package. appxmanifest dosyasını kopyalamayın.

1. Windows SDK farklı sürümleri arasındaki son değişiklikler nedeniyle hataları derleyin ve çözün.

## <a name="troubleshooting"></a>Sorun giderme

UWP 'e kod taşıma işlemi sırasında çeşitli hatalarla karşılaşabilirsiniz. Karşılaşabileceğiniz olası sorunlardan bazıları aşağıda verilmiştir.

### <a name="project-configuration-issues"></a>Proje yapılandırma sorunları

Şu hatayı alabilirsiniz:

```Output
could not find assembly 'platform.winmd': please specify the assembly search path using /AI or by setting the LIBPATH environment variable
```

Bu durumda, proje bir Windows Evrensel projesi olarak oluşturulmamalıdır. Proje dosyasını denetleyin ve bir projeyi bir Windows Evrensel projesi olarak tanımlayan doğru XML öğelerine sahip olduğundan emin olun. Aşağıdaki öğeler bulunmalıdır (hedef platformun sürüm numarası farklı olabilir):

```xml
<AppContainerApplication>true</AppContainerApplication>
<ApplicationType>Windows Store</ApplicationType>
<WindowsTargetPlatformVersion>10.0.10156.0</WindowsTargetPlatformVersion>
<WindowsTargetPlatformMinVersion>10.0.10156.0</WindowsTargetPlatformMinVersion>
<ApplicationTypeRevision>10.0</ApplicationTypeRevision>
```

Visual Studio kullanarak yeni bir UWP projesi oluşturduysanız, bu hatayı görmezsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Görsel C++ taşıma Kılavuzu](../porting/porting-to-the-universal-windows-platform-cpp.md)<br/>
[Evrensel Windows Platformu (UWP) için uygulama geliştirme](/visualstudio/cross-platform/develop-apps-for-the-universal-windows-platform-uwp)