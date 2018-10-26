---
title: Evrensel Windows Platformu (C++) taşıma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f662d2e4-8940-418d-8109-cb76cb8f8569
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 16fe66e6ba8ea3f6e4f88f434b58c61d46ce1edb
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50080656"
---
# <a name="porting-to-the-universal-windows-platform-c"></a>Evrensel Windows Platformu’na bağlantı noktası oluşturma (C++)

Bu konuda, Windows 10 uygulama platformu, Evrensel Windows platformu için mevcut C++ kodunu bağlantı noktası hakkında bilgi bulabilirsiniz. Terime göre tutulmamıştır *Evrensel* kodunuzu herhangi bir masaüstü, telefon, Tablet ve gelecekteki Windows 10 çalıştıran cihazlar dahil olmak üzere Windows 10 çalıştıran cihazlar üzerinde çalıştırılabilir. Tek bir proje ve de Windows 10 çalıştıran tüm cihazlarda çalışan tek bir XAML tabanlı kullanıcı arabirimi oluşturun. Farklı ekran boyutlarına uyum sağlamak uygulamanın UI izin vermek için XAML içinde dinamik düzen özelliklerini kullanabilirsiniz.

Windows Geliştirme Merkezi belgelerini, Windows 8.1 Evrensel Windows platformu uygulamaları taşıma için kılavuz içerir. Bkz: [UWP için Windows 8 çalışma zamanını şuradan Taşı](/windows/uwp/porting/w8x-to-uwp-root). Kılavuzu genellikle C# kod üzerinde odaklanıyor olsa da, yönergeleri çoğu C++ için geçerlidir. Aşağıdaki yordamlar, daha ayrıntılı bilgiler içerir.

Bu konu, UWP için kod taşımak için aşağıdaki yordamları içerir.

- [UWP için Windows 8.1 bir Store uygulaması taşıma](#BK_81StoreApp)

- [UWP için Windows 8.1 bir çalışma zamanı bileşeni taşıma](#BK_81Component)

Klasik Masaüstü bir Win32 DLL varsa ve bir UWP uygulamasında aramak istediğiniz bunu da yapabilirsiniz. Bu yordamları kullanarak, varolan Klasik Windows Masaüstü C++ uygulaması için bir UWP kullanıcı arabirimi katman veya platformlar arası standart C++ kod oluşturabilirsiniz. Bkz: [nasıl yapılır: mevcut C++ kodunu Evrensel Windows platformu uygulamasında kullanma](../porting/how-to-use-existing-cpp-code-in-a-universal-windows-platform-app.md).

## <a name="BK_81StoreApp"></a> UWP için Windows 8.1 bir Store uygulaması taşıma

Bir Windows 8.1 Store uygulaması varsa, bunu UWP ve Windows 10 çalıştıran herhangi bir CİHAZDAN çalıştırmak için bu yordamı kullanabilirsiniz.  Öncelikle derleyici ve kitaplıkları değişiklikleri ortaya çıkabilecek sorunları ortadan kaldırmak için ek olarak, Windows 8.1 proje ilk derleme proje Visual Studio 2017 için iyi bir fikir gibidir. Bunu yaptıktan sonra bu bir Windows 10 UWP projesine dönüştürmek için iki yolu vardır. (Aşağıdaki yordamda açıklandığı gibi) en kolay yolu, bir evrensel Windows projesi oluşturun ve içine varolan kodunuzu kopyalayın sağlamaktır. Windows 8.1 Masaüstü ve Windows 8.1 Phone için evrensel bir proje kullanıyorsanız, projenize XAML ancak son iki farklı düzenleriyle görüntü boyutuna ayarlar tek bir dinamik düzeni ile birlikte başlar.

### <a name="to-port-a-windows-81-store-app-to-the-uwp"></a>UWP için Windows 8.1 bir Store uygulaması bağlantı noktası

1. Zaten yapmadıysanız, Visual Studio 2017'de, Windows 8.1 uygulama projenizi açın ve proje dosyası yükseltmek için yönergeleri izleyin.

   Yüklü gereken **Visual Studio'daki araçları Windows 8.1** kurulumu. Bu araçları yüklü yoksa, başlangıç **Visual Studio** Kurulumu'nu **programlar ve Özellikler** penceresinde seçin **Visual Studio 2017**, Kurulumu penceresinde seçin **Değiştirme**. Bulun **Windows 8.1 Araçları**seçildiğinden emin olun ve seçin **Tamam**.

2. Açık **proje özellikleri** penceresinin altında **C++** > **genel**ayarlayın **Platform araç takımını** için**v141**, Visual Studio 2017 için araç kümesi.

3. Windows 8.1 proje olarak projeyi oluşturun ve derleme hatalarını çözün. Bu aşamada herhangi bir hata derleme araçları ve kitaplıkları değişiklikler nedeniyle olabilirsiniz. Bkz: [Visual C++ değişiklik geçmişi 2003-2015](../porting/visual-cpp-change-history-2003-2015.md) kodunuzu etkileyebilecek değişikliklerin ayrıntılı bir açıklama.

   Projenizi düzgün bir şekilde oluşturur sonra bu bağlantı noktasına Evrensel Windows (Windows 10) hazır olursunuz.

4. Boş şablonu kullanarak yeni bir evrensel Windows uygulaması projesi oluşturun. Projeler bunu yapmanın farklı dizinlerde olması gerekse de mevcut projenizi aynı adı vermek isteyebilirsiniz.

5. Çözümü kapatın ve ardından kullanarak **Windows Explorer** veya komut satırı, kopyalama, Windows 8.1 (uzantıları .cpp, .h ve .xaml ile) kod dosyalarından proje için proje dosyasını (.vcxproj) ile aynı klasöre, proje 1. adımda oluşturduğunuz. Değil Package.appxmanifest dosyasını kopyalayın ve Windows 8.1 Masaüstü ve telefon için ayrı bir kod varsa, bağlantı noktası için bunlardan birini seçin (sahip olacaksınız daha sonra diğer uyarlamak için biraz çalışmanız gerekir) ilk. Kopyalama ve alt klasörler ve bunların içeriğini emin olun. İstenirse, yinelenen adları olan dosyaları değiştirmek seçin.

6. Çözümü yeniden açın ve seçin **Ekle** > **var olan öğe** proje düğümü için kısayol menüsünden. Projenin bir parçası olan tüm dışında kopyaladığınız tüm dosyaları seçin.

   Tüm alt klasörlerde denetleyin ve dosyaları bunları de eklediğinizden emin olun.

7. Aynı proje adı eski projenizi kullanmıyorsanız, Package.appx bildirim dosyasını güncelleştirme açıp **giriş noktası** ad alanı adını yansıtacak şekilde `App` sınıfı.

   **Giriş noktası** Package.appxmanifest dosyasını alanında için kapsamlı bir ad içeren `App` içeren ad uzayı içeren sınıf `App` sınıfı. Ad alanı, bir evrensel Windows projesi oluşturduğunuzda, proje adına ayarlanır. Bu, eski projenizden kopyalanan dosyaların nedir öğesinden farklı ise, birini veya diğerini aynı olacak şekilde güncelleştirmeniz gerekir.

8. Projeyi oluşturmak ve Windows SDK'sı farklı sürümleri arasında önemli değişiklikler nedeniyle derleme hatalarını çözün.

9. Projeyi yerel masaüstüne çalıştırın. Hiçbir dağıtım hata uygulama düzenini makul arar ve onu doğru masaüstünde işlevleri doğrulayın.

10. Ayrı kod dosyaları ve Windows Phone 8.1 gibi başka bir cihaz için .xaml tablonuz varsa bu kodu inceleyin ve standart CİHAZDAN farklılık belirleyin. Yalnızca düzende fark ise kullanmanız mümkün olabilir bir **görsel durum Yöneticisi** ekran boyutuna bağlı olarak görüntüsünü özelleştirmek için xaml içinde. Diğer farklılıklar için aşağıdaki #if ifadeleri kullanarak kodunuzda koşullar bölümleri kullanabilirsiniz.

    ```cpp
    #if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PC_APP)
    #if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PHONE_APP)
    #if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_APP)
    #if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_DESKTOP)
    ```

   Bu deyimler, uygulamalar, her iki ya da hiçbiri (Klasik Win32 yalnızca Masaüstü) UWP uygulamaları, Windows Phone Store sırasıyla uygulanır. Bu makrolar yalnızca Windows 8.1 SDK ve daha sonra durum, bunların hiçbiri göz önünde bulundurabileceğiniz sonra kodunuzu önceki sürümleriyle Windows SDK'yı veya Windows, yanı sıra diğer platformlar için derleme gerekiyorsa tanımlanan şekilde kullanılabilir.

11. Uygulamasında bir öykünücü veya cihaz uygulamanızın desteklediği her türü için fiziksel bir cihaz üzerinde hata ayıklama ve çalıştırın. Bir öykünücüyü çalıştırmak için bir sanal makineye bir fiziksel bilgisayar Visual Studio çalıştırmanız gerekir.

## <a name="BK_81Component"></a> UWP için Windows 8.1 bir çalışma zamanı bileşeni taşıma

Bir DLL veya Windows 8.1 Store uygulamaları ile zaten çalışan bir Windows çalışma zamanı bileşeni varsa, bileşen veya UWP ve Windows 10 ile çalışma DLL almak için bu yordamı kullanabilirsiniz. Yeni bir proje oluşturmak ve kodunuzun içine kopyalamak için temel yordam aynıdır.

### <a name="to-port-a-windows-81-runtime-component-to-the-uwp"></a>Bağlantı noktası bir UWP için Windows 8.1 çalışma zamanı bileşeni

1. İçinde **yeni proje** iletişim Visual Studio 2017'de bulun **Windows Evrensel** düğümü. Bu düğüm görmüyorsanız, yüklemek [Windows 10 için Araçları](http://go.microsoft.com/fwlink/p/?LinkID=617903) ilk. Seçin **Windows çalışma zamanı bileşeni** şablon bileşeniniz için bir ad verin ve seçin **Tamam** düğmesi. Aynı adı kullanın, eski projelerinizi ad alanı isteyebilirsiniz, bileşen adı ad alanı adı olarak kullanılacaktır. Bu, eski hesaptan farklı bir klasörde proje oluşturmanız gerekir. Farklı bir ad seçerseniz, oluşturulan kodda ad alanı adı güncelleştirebilirsiniz.

2. Projeyi kapatın.

3. Tüm kod dosyaları (.cpp, .h, .xaml, vb.), Windows 8.1 bileşeninden yeni oluşturulan projenize kopyalayın. Package.appxmanifest dosyasını kopyalamayın.

4. Derleme ve Windows SDK'sı farklı sürümleri arasında önemli değişiklikler nedeniyle hataları çözün.

## <a name="troubleshooting"></a>Sorun giderme

UWP için kod bağlantı noktası oluşturma işlemi sırasında çeşitli hatalar karşılaşabilirsiniz. Karşılaşabileceğiniz olası sorunlar bazıları aşağıda verilmiştir.

### <a name="project-configuration-issues"></a>Proje yapılandırma sorunları

Hatayı alabilirsiniz:

```Output
could not find assembly 'platform.winmd': please specify the assembly search path using /AI or by setting the LIBPATH environment variable
```

Proje Windows Evrensel bir proje olarak oluşturuyor böyle bir durumda değil. Proje dosyasını kontrol edin ve bir proje Windows Evrensel bir proje olarak tanımlayan XML öğeleri doğru olduğundan emin olun. Aşağıdaki öğeleri mevcut olmalıdır. (hedef platformu sürüm numarası farklı olabilir):

```xml
<AppContainerApplication>true</AppContainerApplication>
<ApplicationType>Windows Store</ApplicationType>
<WindowsTargetPlatformVersion>10.0.10156.0</WindowsTargetPlatformVersion>
<WindowsTargetPlatformMinVersion>10.0.10156.0</WindowsTargetPlatformMinVersion>
<ApplicationTypeRevision>10.0</ApplicationTypeRevision>
```

Visual Studio kullanarak yeni bir UWP projesi oluşturduysanız, bu hata görmemeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Taşıma Kılavuzu](../porting/porting-to-the-universal-windows-platform-cpp.md)<br/>
[Evrensel Windows Platformu (UWP) için uygulama geliştirme](/visualstudio/cross-platform/develop-apps-for-the-universal-windows-platform-uwp)