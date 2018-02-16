---
title: "Evrensel Windows Platformu (C++) için bağlantı noktası oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: f662d2e4-8940-418d-8109-cb76cb8f8569
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2ece050614481bdc0adbe417448711376666b2b9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="porting-to-the-universal-windows-platform-c"></a>Evrensel Windows Platformu’na bağlantı noktası oluşturma (C++)
Bu konuda, mevcut C++ kodunu Evrensel Windows platformu Windows 10 uygulaması platformunuz için bağlantı noktası hakkında bilgi bulabilirsiniz. Terim tarafından anlamına gelir *Evrensel* kodunuzu herhangi bir Windows 10 Masaüstü, telefon, Tablet ve Windows 10 çalıştıran gelecekteki cihazlar dahil olmak üzere, çalıştıran aygıtlar üzerinde çalıştırılabilir. Tek bir proje ve Windows 10 çalıştıran iyi herhangi bir cihazda çalışan tek bir XAML tabanlı kullanıcı arabirimi oluşturun. Farklı ekran boyutlarına uyarlamak uygulamanın UI izin vermek için XAML içinde dinamik düzen özelliklerini kullanabilirsiniz.  
  
 Windows Geliştirme Merkezi belgeler, Windows 8.1 uygulamaları Evrensel Windows platformu için taşıma için kılavuz içerir. Bkz: [UWP'ye Windows çalışma zamanı 8 ' Taşı](https://msdn.microsoft.com/windows/uwp/porting/w8x-to-uwp-root). Kılavuzu genellikle C# kodu odaklanmış Kılavuzu çoğunu olsa da C++ için uygulanabilir. Aşağıdaki yordamlar daha ayrıntılı bilgiler içerir.  
  
 Bu konu, UWP kodu bağlantı noktası oluşturma için aşağıdaki yordamları içerir.  
  
1.  [Bir Windows 8.1 mağazası uygulaması UWP için bağlantı noktası oluşturma](#BK_81StoreApp)  
  
2.  [Bir Windows 8.1 çalışma zamanı bileşeni UWP için bağlantı noktası oluşturma](#BK_81Component)  
  
 Klasik Masaüstü Win32 DLL varsa ve bir UWP uygulamasından aramak istediğiniz, bu da yapabilirsiniz. Bu yordamları kullanarak, varolan Klasik Windows Masaüstü C++ uygulaması için bir UWP kullanıcı arabirimi katman ya da platformlar arası standart C++ kodunuzu oluşturabilirsiniz. Bkz: [nasıl yapılır: mevcut C++ kodunu Evrensel Windows platformu uygulamasında kullanma](../porting/how-to-use-existing-cpp-code-in-a-universal-windows-platform-app.md).  
  
##  <a name="BK_81StoreApp">Bir Windows 8.1 mağazası uygulaması UWP için bağlantı noktası oluşturma</a>  
 Windows 8.1 mağazası uygulaması varsa, bunu UWP ve Windows 10 çalıştıran herhangi bir aygıt üzerinde çalıştırmak için bu yordamı kullanabilirsiniz.  İlk derleyici ve kitaplıkları yapılan değişiklikleri ortaya çıkabilecek sorunları ortadan kaldırmak için bir Windows 8.1 proje ilk yapı Visual Studio 2017 projeyle için iyi bir fikir gibidir. Bunu yaptıktan sonra bu bir Windows 10 UWP projesi dönüştürmek için iki yolu vardır. (Aşağıdaki yordamda açıklandığı gibi) en kolay yolu, bir evrensel Windows projesi oluşturun ve mevcut kodunuzu buraya kopyalayın olmaktır. Windows 8.1 Masaüstü ve Windows 8.1 Phone için evrensel projesi kullanıyorsanız, projeniz için görüntü boyutu ayarlar tek bir dinamik düzen XAML ancak son iki farklı düzenlerle ile başlar.  
  
#### <a name="to-port-a-windows-81-store-app-to-the-uwp"></a>Bir Windows 8.1 mağazası uygulaması UWP için bağlantı noktası  
  
1.  Zaten yapmadıysanız, Visual Studio 2017 Windows 8.1 uygulamasını projenizi açın ve proje dosyası yükseltmek için yönergeleri izleyin.  
  
     Windows 8.1 araçları Visual Studio kurulumunda yüklü gerekir. Bu araçları yüklü yoksa, Visual Studio Kurulumu programlar ve Özellikler penceresinden başlatmak, Visual Studio 2017'ı seçin ve Kurulumu penceresinde seçin **Değiştir**. Windows 8.1 araçları bulun, seçili olduğundan emin olun ve Tamam'ı seçin.  
  
2.  Proje Özellikleri penceresini açın ve C++ altında genel, Visual Studio 2017 derleme araçları v141 için Platform araç takımı ayarlayın.  
  
3.  Windows 8.1 projesi olarak proje derleme ve yapı hataları çözün. Bu aşamada herhangi bir hata nedeniyle yeni kitaplıkları ve derleme Araçları'ndaki değişiklikler olabilirsiniz. Bkz: [Visual C++ değişiklik geçmişini 2003 2015](../porting/visual-cpp-change-history-2003-2015.md) kodunuzu etkileyebilecek değişiklikler ayrıntılı bir açıklaması için.  
  
     Projenizi düzgün bir şekilde oluşturur sonra Evrensel Windows (Windows 10) için bağlantı noktası için hazır olursunuz.  
  
4.  Boş şablon kullanarak yeni bir evrensel Windows uygulaması projesi oluşturun. Projeleri Bunu yapmak için farklı dizinlerde olması gerekse de mevcut projenizi aynı adı vermek isteyebilirsiniz.  
  
5.  Kapat çözüm ve ardından Windows Gezgini veya komut satırı kullanarak (uzantıları .cpp, .h ve .xaml) birlikte kod dosyaları Windows 8.1 projenizden 1. adımda oluşturduğunuz proje için proje dosyası (.vcxproj) aynı klasöre kopyalayın. Değil Package.appxmanifest dosyasını kopyalayın ve Windows 8.1 Masaüstü ve telefon ayrı kodu varsa, bağlantı noktası için bunlardan birini seçin (olması daha sonra diğer uyarlamak için biraz çalışmanız) ilk. Kopyalama ve alt klasörleri ve içeriklerini emin olun. İstenirse, yinelenen adları olan tüm dosyaları değiştirmek seçin.  
  
6.  Çözümü yeniden açın ve seçin **Ekle, var olan öğeyi** proje düğümünün kısayol menüsünden. Zaten projenin bir parçası olan tüm dışında kopyaladığınız tüm dosyalar'ı seçin.  
  
     Tüm alt denetleyin ve dosyaları bunları da eklediğinizden emin olun.  
  
7.  Eski projesi olarak aynı proje adı kullanmıyorsanız Package.appxmanifest dosyasını açın ve giriş noktası uygulama sınıfı için ad alanı adı yansıtacak şekilde güncelleştirin.  
  
     **Giriş noktası** Package.appxmanifest dosyasını alanında, uygulama sınıfı içeren ad içeren uygulama sınıfı için kapsamlı bir adı içeriyor. Evrensel Windows projesi oluşturduğunuzda, ad alanı proje adına ayarlanır. Bu, eski projenizden kopyaladığınız dosyalar nedir öğesinden farklı ise, aşağıdakilerden birini veya bunların eşleşen sağlamak için diğer güncelleştirmeniz gerekir.  
  
8.  Projeyi oluşturmak ve Windows SDK'sı farklı sürümleri arasında önemli değişiklikler nedeniyle derleme hataları çözün.  
  
9. Projeyi yerel masaüstü bilgisayarlarda çalıştırın. Hiçbir dağıtım hataları vardır ve uygulama yerleşimini mantıklı arar ve, doğru masaüstünde çalıştığından doğrulayın.  
  
10. Ayrı kod dosyaları ve Windows Phone 8.1 gibi başka bir aygıt için .xaml sahipse, bu kod inceleyin ve burada standart aygıttan farklı tanımlayın. Fark yalnızca düzende ise, bir görsel durum Yöneticisi ekran boyutuna bağlı olarak görüntüsünü özelleştirmek için XAML'de kullanabilmek için olabilir. Diğer farklar için aşağıdaki #if bildirimleri kullanan kodunuzda koşullar bölümleri kullanabilirsiniz.  
  
    ```  
    #if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PC_APP)  
    #if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PHONE_APP)  
    #if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_APP)  
    #if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_DESKTOP)  
    ```  
  
     Bu deyimler sırasıyla UWP uygulamaları, Windows Phone mağazası uygulamaları, hem veya hiçbiri (Klasik Win32 yalnızca Masaüstü) geçerli. Bu makroları yalnızca Windows 8.1 SDK ve daha sonra de durum, bunların hiçbiri dikkate almalısınız sonra Windows SDK veya diğer platformlar yanı sıra Windows, önceki sürümleriyle derlemek kodunuzu gerekiyorsa tanımlanan şekilde kullanılabilir.  
  
11. Bir öykünücü veya uygulamanızın destekleyen aygıt her tür için fiziksel cihaz üzerindeki uygulama hata ayıklama ve çalıştırın. Bir öykünücü çalıştırmak için Visual Studio fiziksel bir bilgisayarda, sanal makine çalıştırmanız gerekir.  
  
##  <a name="BK_81Component">Bir Windows 8.1 çalışma zamanı bileşeni UWP için bağlantı noktası oluşturma</a>  
 DLL ya da Windows 8.1 mağazası uygulamaları ile zaten çalışan bir Windows çalışma zamanı bileşeni varsa, bileşen veya UWP ve Windows 10 Çalışma DLL almak için bu yordamı kullanabilirsiniz. Temel yordam, yeni bir proje oluşturun ve kodunuzu içine kopyalamak için kullanılır.  
  
#### <a name="to-port-a-windows-81-runtime-component-to-the-uwp"></a>Bir Windows 8.1 çalışma zamanı bileşeni UWP için bağlantı noktası  
  
1.  İçinde **yeni proje** iletişim Visual Studio 2017 içinde bulun **Windows Evrensel** düğümü. Bu düğüm görmüyorsanız, yüklemek [Windows 10 için Araçlar](http://go.microsoft.com/fwlink/p/?LinkID=617903) ilk. Seçin **Windows çalışma zamanı bileşeni** şablonu, bileşeniniz için bir ad verin ve seçin **Tamam** düğmesi. Eski projelerinizi ad alanı olarak aynı adı kullanmak isteyebilirsiniz şekilde bileşen adı ad alanı adı olarak kullanılacaktır. Bu, eski olandan farklı bir klasörde projeyi oluşturmanızı gerektirir. Farklı bir ad seçin, oluşturulan kodda ad alanı adı güncelleştirebilirsiniz.  
  
2.  Projeyi kapatın.  
  
3.  Tüm kod dosyaları (.cpp, .h, .xaml, vb.), Windows 8.1 bileşeninden yeni oluşturulan projenize kopyalayın. Package.appxmanifest dosyasını kopyalamayın.  
  
4.  Derleme ve Windows SDK'sı farklı sürümleri arasında önemli değişiklikler nedeniyle varsa hataları çözümleyin.  
  
## <a name="troubleshooting"></a>Sorun giderme  
 UWP kodu bağlantı noktası oluşturma işlemi sırasında çeşitli hatalarla karşılaşabilirsiniz. Karşılaşabileceğiniz olası sorunlar bazıları aşağıda verilmiştir.  
  
 **Proje yapılandırma sorunları**  
  
 Hatayı alabilirsiniz:  
  
```Output  
could not find assembly 'platform.winmd': please specify the assembly search path using /AI or by setting the LIBPATH environment variable  
```  
  
 Bu durumda, bir evrensel Windows projesi olarak proje derleme değil. Proje dosyasını denetleyin ve proje Evrensel Windows projesi olarak tanımlamak doğru XML öğeleri olduğundan emin olun. Aşağıdaki öğeler mevcut olması (hedef platformu sürüm numarasını farklı olabilir):  
  
```xml  
<AppContainerApplication>true</AppContainerApplication>  
<ApplicationType>Windows Store</ApplicationType>  
<WindowsTargetPlatformVersion>10.0.10156.0</WindowsTargetPlatformVersion>  
<WindowsTargetPlatformMinVersion>10.0.10156.0</WindowsTargetPlatformMinVersion>  
<ApplicationTypeRevision>10.0</ApplicationTypeRevision>  
```  
  
 Visual Studio kullanarak yeni bir UWP projesini oluşturduysanız, bu hata görülmemelidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ Taşıma Kılavuzu](../porting/porting-to-the-universal-windows-platform-cpp.md)   
 [Evrensel Windows Platformu (UWP) için uygulama geliştirme](/visualstudio/cross-platform/develop-apps-for-the-universal-windows-platform-uwp)
