---
title: C/C++ Yalıtılmış Uygulamalar ve Yan Yana Derlemeler ile İlgili Sorunları Giderme
ms.date: 11/04/2016
helpviewer_keywords:
- troubleshooting side-by-side assemblies
- troubleshooting isolated applications
- troubleshooting Visual C++
ms.assetid: 3257257a-1f0b-4ede-8564-9277a7113a35
ms.openlocfilehash: 0dc8488acc90f1a38a4c0de0f052590ef4f398af
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335447"
---
# <a name="troubleshooting-cc-isolated-applications-and-side-by-side-assemblies"></a>C/C++ Yalıtılmış Uygulamalar ve Yan Yana Derlemeler ile İlgili Sorunları Giderme

Bağımlı kitaplıklar bulunamıyorsa C/C++ uygulaması yüklenmesi başarısız olabilir. Bu makalede, C/C++ uygulamasının yüklenememesinin bazı yaygın nedenleri açıklanır ve sorunları gidermek için adımlar önerir.

Bir uygulama, yan yana montajda bir bağımlılık belirten bir bildirime sahip olduğu için yüklenmezse ve derleme yürütülebilir klasörde veya %WINDIR%\WinSxS\ klasöründeki yerel derleme önbelleğinde özel derleme olarak yüklenmezse, uygulamayı çalıştırmayı denediğiniz Windows sürümüne bağlı olarak aşağıdaki hata iletilerinden biri görüntülenebilir.

- Uygulama düzgün (0xc0000135) başlatılması başarısız oldu.

- Uygulama yapılandırması yanlış olduğundan bu uygulama başlatılamamış. Uygulamayı yeniden yüklemek bu sorunu çözebilir.

- Sistem belirtilen programı yürütemez.

Uygulamanızın bir bildirimi yoksa ve Windows'un tipik arama konumlarında bulamadığı bir DLL'ye bağlıysa, buna benzeyen bir hata iletisi görüntülenebilir:

- *Gerekli bir DLL* bulunamadı çünkü bu uygulama başlatılamamıştır. Uygulamayı yeniden yüklemek bu sorunu çözebilir.

Uygulamanız Visual Studio'su olmayan bir bilgisayarda dağıtılırsa ve öncekilere benzeyen hata iletileriyle çöküyorsa, aşağıdakileri denetleyin:

1. [Görsel C++ Uygulamasının Bağımlılıklarını Anlama'da](../windows/understanding-the-dependencies-of-a-visual-cpp-application.md)açıklanan adımları izleyin. Bağımlılık yürütücüsü, bir uygulama veya DLL için en bağımlılıkları gösterebilir. Bazı DL'lerin eksik olduğunu gözlemlerseniz, bunları uygulamanızı çalıştırmaya çalıştığınız bilgisayara yükleyin.

1. İşletim sistemi yükleyici, uygulamanın bağlı olduğu derlemeleri yüklemek için uygulama bildirimini kullanır. Bildirim, kaynak olarak ikiliye katıştırılabilir veya uygulama klasörüne ayrı bir dosya olarak yüklenebilir. Bildirimin ikiliye katıştırılmış olup olmadığını kontrol etmek için, Visual Studio'da ikiliyi açın ve kaynak listesinde RT_MANIFEST arayın. Katışdırılmış bir bildirim bulamıyorsanız,> binary_name <gibi bir dosyanın uygulama klasörüne bakın. \<uzantısı>.manifest.

1. Uygulamanız yan yana derlemelere bağlıysa ve bir manifesto yoksa, bağlantı nın projeniz için bir bildirim oluşturduğundan emin olun. Bağlayıcı seçeneğini, proje için **Proje Özellikleri** iletişim kutusunda **manifesto oluştur** seçeneğini işaretleyin.

1. Bildirim ikiliye gömülüyse, RT_MANIFEST kimliğinin bu tür ikili için doğru olduğundan emin olun. Hangi kaynak kimliğinin kullanılacağı hakkında daha fazla bilgi için [bkz.](/windows/win32/SbsCs/using-side-by-side-assemblies-as-a-resource) Bildirim ayrı bir dosyadaysa, bir XML düzenleyicisinde veya metin düzenleyicisinde açın. Dağıtım bildirimleri ve kuralları hakkında daha fazla bilgi için [Bkz.](/windows/win32/sbscs/manifests)

   > [!NOTE]
   > Hem katışılmış bir bildirim hem de ayrı bir bildirim dosyası varsa, işletim sistemi yükleyicisi katıştirilen bildirimi kullanır ve ayrı dosyayı yok sayar. Ancak, Windows XP'de tam tersi doğrudur—ayrı bir bildirim dosyası kullanılır ve katıştırılmış bildirim yoksayılır.

1. Bir `LoadLibrary` çağrı olsa dll yüklendiğinde dış bildirimler isayetmediği için her DLL'ye bir manifesto yerleştirmenizi öneririz. Daha fazla bilgi için [Bkz. Derleme bildirimleri.](/windows/win32/SbsCs/assembly-manifests)

1. Bildirimde numaralandırılmış tüm derlemelerin bilgisayara doğru şekilde yüklendiğinden denetleyin. Her derleme, bildirimde adı, sürüm numarası ve işlemci mimarisi ile belirtilir. Uygulamanız yan yana derlemelere bağlıysa, bu derlemelerin bilgisayara doğru şekilde yüklendiğinden kontrol edin, böylece işletim sistemi yükleyicisi Bunları bulabilsin, [Derleme Arama Sırası'nda](/windows/win32/SbsCs/assembly-searching-sequence)açıklandığı gibi. 64 bit montajların 32 bit işlemlere yüklenemeyeceğini ve 32 bit işletim sistemlerinde yürütülemeyeceğini unutmayın.

## <a name="example"></a>Örnek

Visual C++'ı kullanarak oluşturulmuş bir uygulamamız olduğunu varsayalım, appl.exe. Uygulama bildirimi, 1'e eşit bir kimliği olan veya ayrı bir dosya appl.exe.manifest olarak depolanan ikili kaynak RT_MANIFEST olarak appl.exe'ye katıştırılmıştır. Bu bildirimin içeriği buna benzer:

```
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">
  <dependency>
    <dependentAssembly>
      <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"></assemblyIdentity>
    </dependentAssembly>
  </dependency>
</assembly>
```

İşletim sistemi yükleyicisine göre, bu bildirim appl.exe'nin Fabrikam.SxS.Library adlı bir derlemeye, sürüm 2.0.20121.0'a bağlı olduğunu ve 32 bit x86 işlemci mimarisi için üretilmiştir. Bağımlı yan yana montaj, paylaşılan derleme olarak veya özel derleme olarak yüklenebilir.

Paylaşılan bir derlemenin montaj bildirimi %WINDIR%\WinSxS\Manifests\ klasörüne yüklenir. Derlemeyi tanımlar ve içeriğini listeler,yani derlemenin bir parçası olan DL'leri listeler:

```
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">
   <noInheritable/>
   <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"/>
   <file name="Fabrikam.Main.dll" hash="3ca5156e8212449db6c622c3d10f37d9adb1ab12" hashalg="SHA1"/>
   <file name="Fabrikam.Helper.dll" hash="92cf8a9bb066aea821d324ca4695c69e55b2d1c2" hashalg="SHA1"/>
</assembly>
```

Yan yana derlemeler, uygulamaları ve derlemeleri aynı derlemenin başka bir sürümü yerine yan yana derlemenin bir sürümünü kullanmak üzere genel olarak yeniden yönlendirmek için [yayımcı yapılandırma dosyalarını](/windows/win32/SbsCs/publisher-configuration-files)(ilke dosyaları olarak da bilinir) de kullanabilir. %WINDIR%\WinSxS\Policies\ klasöründe paylaşılan bir derlemeiçin ilkeleri denetleyebilirsiniz. Aşağıda bir örnek ilke dosyası verilmiştir:

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

Bu ilke dosyası, bu derlemenin 2.0.10000.0 sürümünü soran herhangi bir uygulama nın veya derlemenin bunun yerine sistemde yüklenen geçerli sürüm olan 2.0.20121.0 sürümünü kullanmasını belirtir. Uygulama bildiriminde belirtilen derlemenin bir sürümü ilke dosyasında belirtilirse, yükleyici bu derlemenin %WINDIR%\WinSxS\ klasöründe belirtilen bir sürümünü arar ve bu sürüm yüklenmezse yük başarısız olur. Ve montaj sürümü 2.0.20121.0 yüklü değilse, montaj sürümü 2.0.10000.0 için soran uygulamalar için yük başarısız olur.

Ancak, montaj, yüklenen uygulama klasöründe yan yana özel bir derleme olarak da yüklenebilir. İşletim sistemi derlemeyi paylaşılan bir derleme olarak bulamazsa, aşağıdaki sırayla özel bir derleme olarak arar:

1. Ad \<assemblyname>.manifest olan bir bildirim dosyası için uygulama klasörünü denetleyin. Bu örnekte, yükleyici appl.exe içeren klasörde Fabrikam.SxS.Library.manifest bulmaya çalışır. Bildirimi bulursa, yükleyici derlemeyi uygulama klasöründen yükler. Montaj bulunmazsa, yük başarısız olur.

1. appl.exe \\ içeren\>klasörde<assemblyName \ klasörünü açmaya \\ çalışın\>ve<assemblyName \ varsa, bu \<klasörden assemblyName>.manifest adını içeren bir manifesto dosyası yüklemeyi deneyin. Bildirim bulunursa, yükleyici derlemeyi \\<assemblyName\>\ klasöründen yükler. Montaj bulunmazsa, yük başarısız olur.

Yükleyicinin bağımlı derlemeleri nasıl aradığı hakkında daha fazla bilgi için [Montaj Arama Sırası'na](/windows/win32/SbsCs/assembly-searching-sequence)bakın. Yükleyici özel bir derleme olarak bağımlı bir derleme bulamazsa, yük başarısız olur ve "Sistem belirtilen programı yürütemez" iletisi görüntülenir. Bu hatayı gidermek için, bağımlı derlemelerin ve bunların bir parçası olan DL'lerin bilgisayara özel veya paylaşılan derlemeler olarak yüklendiğinden emin olun.

## <a name="see-also"></a>Ayrıca bkz.

[İzole Uygulamalar ve Yan Yana Derlemeler Kavramları](concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
