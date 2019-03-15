---
title: C/C++ Yalıtılmış Uygulamalar ve Yan Yana Derlemeler ile İlgili Sorunları Giderme
ms.date: 11/04/2016
helpviewer_keywords:
- troubleshooting side-by-side assemblies
- troubleshooting isolated applications
- troubleshooting Visual C++
ms.assetid: 3257257a-1f0b-4ede-8564-9277a7113a35
ms.openlocfilehash: d23662d6dd6d2f241c48e0c83f2fa5ed9532c3f7
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807955"
---
# <a name="troubleshooting-cc-isolated-applications-and-side-by-side-assemblies"></a>C/C++ Yalıtılmış Uygulamalar ve Yan Yana Derlemeler ile İlgili Sorunları Giderme

C/C++ uygulamasına yükleme başarısız olabilir bağımlı kitaplıkları bulunamazsa. Bu makalede, C/C++ uygulamasına neden başarısız yüklemek için bazı yaygın nedenleri açıklanır ve sorunları gidermek için adımları önerir.

Bir uygulamanın yüklenmemesi bir yan yana derlemeye bağımlılık belirten bir bildirimi sahip olduğundan ve derleme yürütülebilir dosya ile aynı klasörde %WINDIR%\WinSxS\ klasöründeki yerel derleme önbelleğindeki ya da özel bir derleme olarak yüklü değil , aşağıdaki hata iletilerinden birini görüntülenebilir, üzerinde aşağıdakileri uygulamayı çalıştırmak Windows sürümüne bağlı olarak.

- Uygulama düzgün şekilde başlatılamadı (0xc0000135).

- Bu uygulama, uygulama yapılandırması yanlış olduğundan dolayı başarısız oldu. Uygulamayı tekrar yüklemek bu sorunu çözebilir.

- Sistem, belirtilen program yürütülemiyor.

Buna benzer bir hata iletisi görüntülenebilir, uygulamanızı hiçbir bildirim varsa, ve Windows tipik arama konumlarda bulunamıyor bir DLL bağlıdır:

- Bu uygulama başlatılamadı çünkü başaramadı *gerekli bir DLL* bulunamadı. Uygulamanın yeniden yüklenmesi bu sorunu çözebilir.

Uygulamanızı Visual Studio'su olmayan bir bilgisayarda dağıtılır ve öncekinin benzer hata iletileri ile çöküyor, bunları denetleyin:

1. Açıklanan adımları [Visual C++ uygulaması bağımlılıklarını anlama](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md). Bir uygulama veya DLL için çoğu bağımlılıkları bağımlılık Denetçisi'ni gösterebilirsiniz. Bazı DLL'lerin eksik olduğunu gözlemlerseniz, uygulamanızı çalıştırmak çalıştığınız bilgisayarda yükleyin.

1. İşletim sistemi yükleyicisi uygulama bağımlı derlemeler yüklemek için uygulama bildirimini kullanır. Bildirim ikili bir kaynak olarak gömülü, veya ayrı bir dosya uygulama klasöründe olarak yüklenir. Bildirim ikili dosyada gömülü olup olmadığını denetlemek için ikili Visual Studio'da açın ve rt_manıfest için kaynakları listesinde arayın. < Binary_name > gibi bir şey adlı bir dosya için uygulama klasöründe bir gömülü bildirim bulamazsa, bakın. \<uzantısı > .manifest.

1. Yan yana derlemelerini uygulamanızın bağımlı ve bir bildirim mevcut değilse, bağlayıcı projeniz için bir bildirim üretir emin olmak sahip. Bağlayıcı seçeneği işaretleyin **oluşturma bildirimi** içinde **proje özellikleri** iletişim kutusu için proje.

1. İkili dosyada bildirim katıştırılır, kimliği rt_manıfest, bu ikili türü için doğru olduğundan emin olun. Hangi kaynak Kimliğinde kullanılacak hakkında daha fazla bilgi için bkz: [bir kaynak (Windows) kullanarak yan yana derlemeler](/windows/desktop/SbsCs/using-side-by-side-assemblies-as-a-resource). Ayrı bir dosyada bildirime ise bir XML Düzenleyicisi'ni veya metin düzenleyicide açın. Bildirimler ve dağıtım için kuralları hakkında daha fazla bilgi için bkz. [bildirimlerini](/windows/desktop/sbscs/manifests).

   > [!NOTE]
   > Gömülü bir bildirim hem de ayrı bir bildirim dosyası varsa, işletim sistemi yükleyicisi gömülü bildirimi kullanır ve ayrı bir dosya yok sayar. Ancak, Windows XP'de, bunun tersini geçerlidir — ayrı bildirim dosyası kullanılır ve katıştırılmış bildirime göz ardı edilir.

1. Dış bildirimler, ancak bir DLL yüklendiğinde göz ardı edilir çünkü her DLL içinde bildirim katıştırma öneririz bir `LoadLibrary` çağırın. Daha fazla bilgi için [derleme bildirimleri](/windows/desktop/SbsCs/assembly-manifests).

1. Bildirimde numaralandırılır tüm derlemelerin bilgisayarda düzgün yüklendiğini kontrol edin. Her derleme bildiriminde adı, sürüm numarasını ve işlemci mimarisi tarafından belirtilir. Yan yana derlemelerini, uygulamanızın bağlı olduğu durumlarda işletim sistemi yükleyicisi bunları bulabilmesi için bu bütünleştirilmiş kodları doğru bilgisayarda açıklandığı gibi yüklü olup olmadığını denetleyin [derleme arama sırası](/windows/desktop/SbsCs/assembly-searching-sequence). 64 bit derlemelerin 32-bit işlemde yüklenemez ve 32-bit işletim sistemlerinde yürütülemez unutmayın.

## <a name="example"></a>Örnek

Bir uygulama, Visual C++ kullanılarak oluşturulan appl.exe, sahip olduğumuz varsayılır. Uygulama bildirimini ya da ikili kaynak 1'e bir kimliği eşit olan veya ayrı bir dosya appl.exe.manifest depolanan rt_manıfest olarak appl.exe eklenir. Bu bildirim içeriğini bunu yeniden birleştirir:

```
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">
  <dependency>
    <dependentAssembly>
      <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"></assemblyIdentity>
    </dependentAssembly>
  </dependency>
</assembly>
```

İşletim sistemi yükleyicisi için bu bildirimi bir 32-bit x86 için yerleşik Fabrikam.SxS.Library, sürüm 2.0.20121.0, adında bir derleme söz konusu appl.exe bağlıdır diyor İşlemci mimarisi. Bağımlı yan yana derleme, paylaşılan bir derleme veya özel bir derleme olarak yüklenebilir.

Paylaşılan bir derleme için derleme bildirimi %WINDIR%\WinSxS\Manifests\ klasörüne yüklenir. Derleme tanımlar ve içeriğini listeler — diğer bir deyişle, derlemenin parçası olan DLL'leri:

```
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">
   <noInheritable/>
   <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"/>
   <file name="Fabrikam.Main.dll" hash="3ca5156e8212449db6c622c3d10f37d9adb1ab12" hashalg="SHA1"/>
   <file name="Fabrikam.Helper.dll" hash="92cf8a9bb066aea821d324ca4695c69e55b2d1c2" hashalg="SHA1"/>
</assembly>
```

Yan yana derlemeler de kullanabilir [yayımcı yapılandırma dosyaları](/windows/desktop/SbsCs/publisher-configuration-files)— ilkesi dosyaları olarak da bilinir — uygulamaları ve derlemeleri aynı başka bir sürümü yerine bir yan yana derlemenin bir sürümünü kullanmak için genel olarak yönlendirmek için derleme. Paylaşılan bir derleme %WINDIR%\WinSxS\Policies\ klasöründe ilkelerini denetleyebilirsiniz. Bir ilke dosyası örneği aşağıdadır:

```
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">

   <assemblyIdentity type="win32-policy" name="policy.2.0.Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"/>
   <dependency>
      <dependentAssembly>
         <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"/>
         <bindingRedirect oldVersion="2.0.10000.0-2.0.20120.99" newVersion="2.0.20121.0"/>
      </dependentAssembly>
   </dependency>
</assembly>
```

Bu ilke dosyası herhangi bir uygulama veya bu derlemeye 2.0.10000.0 sürümünü ister derleme yerine sürüm 2.0.20121.0, sistemde yüklü geçerli sürüm olduğu kullanması gerektiğini belirtir. Uygulama bildiriminde belirtilen derlemenin bir sürümünü ilke dosyasında belirtilmediği takdirde, yükleyici %WINDIR%\WinSxS\ klasöründe bildiriminde belirtilen Bu derlemenin bir sürümünü arar ve bu sürüm yüklü değilse, yükleme başarısız olur. Ve derleme sürümü 2.0.20121.0 yüklü değilse, yükleme için derleme sürümünü 2.0.10000.0 isteyen uygulamalar için başarısız olur.

Ancak, derleme yüklü uygulama klasöründe özel bir yan yana derleme olarak da yüklenebilir. Paylaşılan bir derleme olarak derlemeyi bulmak işletim sisteminin başarısız olursa, bunun için aşağıdaki sırayla özel bir derleme olarak görünüyor:

1. Denetleyin ada sahip bir bildirim dosyası için uygulama klasörü \<assemblyName > .manifest. Bu örnekte, yükleyici appl.exe içeren klasöre Fabrikam.SxS.Library.manifest bulmayı dener. Bildirim bulursa, yükleyici uygulama klasöründen derlemeyi yükler. Derleme bulunmazsa yükleme başarısız olur.

1. Açmaya \\< assemblyName\>\ appl.exe, içeren klasörü klasöründe ve \\< assemblyName\>\ var, ada sahip bir bildirim dosyası yüklemeye \<assemblyName >. Bu klasörden bildirimi. Bildirim bulunursa, yükleyici bütünleştirilmiş koddan yükler \\< assemblyName\>\ klasör. Derleme bulunmazsa yükleme başarısız olur.

Yükleyici bağımlı derlemeleri nasıl arama hakkında daha fazla bilgi için bkz. [derleme arama sırası](/windows/desktop/SbsCs/assembly-searching-sequence). Bağımlı bir derleme özel bir derleme olarak bulmak yükleyici başarısız olursa, yükleme başarısız olur ve "Sistem belirtilen program yürütülemiyor" iletisi görüntülenir. Bu hatayı gidermek için emin bağımlı derlemeleri — ve bunları bir parçası olan DLL'ler — bilgisayarda özel veya paylaşılan derlemeler yüklenir.

## <a name="see-also"></a>Ayrıca bkz.

[Yalıtılmış Uygulama ve Yan Yana Derleme Kavramları](concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
