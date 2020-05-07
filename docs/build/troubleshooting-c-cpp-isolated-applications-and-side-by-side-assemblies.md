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

Bir C/C++ uygulamasının yüklenmesi, bağımlı kitaplıkların bulunamaması durumunda başarısız olabilir. Bu makalede, bir C/C++ uygulamasının yüklenmesinin başarısız olduğu bazı yaygın nedenler açıklanmakta ve sorunları çözmek için gereken adımlar önerilmektedir.

Bir uygulama, yan yana derleme üzerinde bir bağımlılığı belirten bir bildirime sahip olduğundan yükleme başarısız olursa, derleme, yürütülebilir dosya veya%Windir%\wınsxs\ klasöründeki yerel derleme önbelleğinde özel bir derleme olarak yüklü değil, uygulamayı çalıştırmayı denediğinize Windows 'un sürümüne bağlı olarak aşağıdaki hata iletilerinden biri görüntülenebilir.

- Uygulama düzgün bir şekilde başlayamadı (0xc0000135).

- Uygulama yapılandırması yanlış olduğundan bu uygulama başlatılamadı. Uygulamayı yeniden yüklemek bu sorunu çözebilir.

- Sistem belirtilen programı yürütemiyor.

Uygulamanızda bildirim yoksa ve Windows 'un tipik arama konumlarında bulamadığı bir DLL 'ye bağlı değilse, aşağıdakine benzer bir hata iletisi görüntülenebilir:

- *Gerekli BIR DLL* bulunamadığı için bu uygulama başlatılamadı. Uygulamayı yeniden yüklemek bu sorunu çözebilir.

Uygulamanız, Visual Studio olmayan bir bilgisayara dağıtılmışsa ve önceki olanlara benzeyen hata iletileriyle çöküyor, şu işlemleri denetleyin:

1. [Visual C++ uygulamasının bağımlılıklarını anlama](../windows/understanding-the-dependencies-of-a-visual-cpp-application.md)bölümünde açıklanan adımları izleyin. Bağımlılık denetçisi, bir uygulama veya DLL için çoğu bağımlılığı gösterebilir. Bazı dll 'Lerin eksik olduğunu gözlemlerseniz, uygulamayı çalıştırmayı denediğiniz bilgisayara yükleyebilirsiniz.

1. İşletim sistemi yükleyicisi, uygulamanın bağımlı olduğu derlemeleri yüklemek için uygulama bildirimini kullanır. Bildirim, bir kaynak olarak ikiliye gömülebilir ya da uygulama klasörüne ayrı bir dosya olarak yüklenebilir. Bildirimin ikiliye gömülü olup olmadığını denetlemek için, ikili dosyasını Visual Studio 'da açın ve kaynak listesinde RT_MANIFEST bulun. Katıştırılmış bir bildirim bulamazsanız, <binary_name> gibi bir dosya adlı dosyanın uygulama klasörüne bakın. \<uzantı>. manifest.

1. Uygulamanız yan yana derlemelere bağımlıysa ve bir bildirim yoksa, bağlayıcının projeniz için bir bildirim üretmesine dikkat etmeniz gerekir. Projenin **Proje özellikleri** iletişim kutusunda **bildirim oluştur** bağlayıcı seçeneğini işaretleyin.

1. Bildirim ikiliye katıştırılmışsa, RT_MANIFEST KIMLIĞININ bu ikili türü için doğru olduğundan emin olun. Kullanılacak kaynak KIMLIĞI hakkında daha fazla bilgi için bkz. [yan yana derlemeleri kaynak olarak kullanma (Windows)](/windows/win32/SbsCs/using-side-by-side-assemblies-as-a-resource). Bildirim ayrı bir dosya içinde ise, bir XML düzenleyicisinde veya metin düzenleyicisinde açın. Dağıtım bildirimleri ve kuralları hakkında daha fazla bilgi için bkz. [Bildirimler](/windows/win32/sbscs/manifests).

   > [!NOTE]
   > Hem gömülü bir bildirim hem de ayrı bir bildirim dosyası varsa, işletim sistemi yükleyicisi katıştırılmış bildirimi kullanır ve ayrı dosyayı yoksayar. Bununla birlikte, Windows XP 'de, tersi doğru olur — ayrı bildirim dosyası kullanılır ve katıştırılmış bildirim yok sayılır.

1. Bir DLL bir `LoadLibrary` çağrı olsa da yüklendiğinde dış bildirimler yoksayıldığından, her dll 'ye bir bildirim katıştırmanız önerilir. Daha fazla bilgi için bkz. [derleme bildirimleri](/windows/win32/SbsCs/assembly-manifests).

1. Bildirimde numaralandırılan tüm derlemelerin bilgisayara doğru şekilde yüklendiğinden emin olun. Her derleme, bildirimde adı, sürüm numarası ve işlemci mimarisine göre belirtilir. Uygulamanız yan yana derlemelere bağımlıysa, işletim sistemi yükleyicisinin [Derleme arama dizisi](/windows/win32/SbsCs/assembly-searching-sequence)bölümünde açıklandığı gibi bunları bulabilmesi için bu derlemelerin bilgisayara doğru şekilde yüklendiğinden emin olun. 64 bitlik derlemelerin 32 bit işlemlere yükleneolamayacağını ve 32-bit işletim sistemlerinde yürütülebileceğini unutmayın.

## <a name="example"></a>Örnek

Visual C++ kullanılarak oluşturulan, Uyg. exe uygulamamız olduğunu varsayalım. Uygulama bildirimi, bir KIMLIĞI 1 ' e eşit olan veya ayrı dosya Uygula. exe. manifest olarak depolanan ikili kaynak RT_MANIFEST olarak uygulanacağı. exe ' ye katıştırılır. Bu bildirimin içeriği şuna benzer:

```
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">
  <dependency>
    <dependentAssembly>
      <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"></assemblyIdentity>
    </dependentAssembly>
  </dependency>
</assembly>
```

Bu bildirim, işletim sistemi yükleyicisi için, Uyg. exe ' nin 32 bitlik bir x86 işlemci mimarisi için tasarlanan fabrikam. SxS. Library, sürüm 2.0.20121.0 adlı bir derlemeye bağlı olduğunu söyler. Bağımlı yan yana derleme, paylaşılan bir derleme ya da özel bir derleme olarak yüklenebilir.

Paylaşılan derleme için derleme bildirimi%WINDIR%\WinSxS\Manifests\ klasörüne yüklenir. Derlemeyi tanımlar ve içeriğini listeler; Yani, derlemenin parçası olan DLL 'Ler:

```
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">
   <noInheritable/>
   <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"/>
   <file name="Fabrikam.Main.dll" hash="3ca5156e8212449db6c622c3d10f37d9adb1ab12" hashalg="SHA1"/>
   <file name="Fabrikam.Helper.dll" hash="92cf8a9bb066aea821d324ca4695c69e55b2d1c2" hashalg="SHA1"/>
</assembly>
```

Yan yana derlemeler Ayrıca, uygulamalar ve derlemeler için aynı derlemenin başka bir sürümü yerine yan yana derlemenin tek bir sürümünü kullanmak üzere, uygulama ve derlemeleri küresel olarak yeniden yönlendirmek için [Yayımcı yapılandırma dosyalarını](/windows/win32/SbsCs/publisher-configuration-files)(ilke dosyaları olarak da bilinir) de kullanabilir. Paylaşılan derleme için ilkeleri%windir%\wınsxs\policies \ klasöründe denetleyebilirsiniz. Aşağıda örnek bir ilke dosyası verilmiştir:

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

Bu ilke dosyası, bu derlemenin sürüm 2.0.10000.0 için soran herhangi bir uygulamanın veya derlemenin bunun yerine sistemde yüklü olan sürümü 2.0.20121.0 ' yi kullanması gerektiğini belirtir. İlke dosyasında uygulama bildiriminde bahsedilen bir derleme sürümü belirtilmişse, yükleyici bu derlemenin%windir%\wınsxs\ klasöründeki bildirimde belirtilen bir sürümünü arar ve bu sürüm yüklü değilse, yükleme başarısız olur. Derleme sürümü 2.0.20121.0 yüklü değilse, derleme sürümü 2.0.10000.0 için sorun veren uygulamalar için yükleme başarısız olur.

Ancak, derleme ayrıca yüklü uygulama klasörüne özel bir yan yana derleme olarak da yüklenebilir. İşletim sistemi derlemeyi paylaşılan bir derleme olarak bulamazsa, bu dosyayı özel bir derleme olarak, aşağıdaki sırayla arar:

1. AssemblyName>. manifest adlı \<bir bildirim dosyası için uygulama klasörünü kontrol edin. Bu örnekte, yükleyici, Uyg. exe dosyasını içeren klasörde Fabrikam. SxS. Library. manifest bulmayı dener. Bildirimi bulursa, yükleyici derlemeyi uygulama klasöründen yükler. Derleme bulunamazsa, yükleme başarısız olur.

1. \\<AssemblyName\>\ klasörünü uygulanacağı. exe içeren klasörde açmayı deneyin ve \\<AssemblyName\>\ varsa, bu klasörden AssemblyName>. manifest adlı \<bir bildirim dosyası yüklemeyi deneyin. Bildirim bulunursa, yükleyici derlemeyi \\<AssemblyName\>\ klasöründen yükler. Derleme bulunamazsa, yükleme başarısız olur.

Yükleyicinin bağımlı derlemeleri nasıl aradığı hakkında daha fazla bilgi için bkz. [Derleme arama sırası](/windows/win32/SbsCs/assembly-searching-sequence). Yükleyici özel bir derleme olarak bağımlı bir derlemeyi bulamazsa, yükleme başarısız olur ve "Sistem belirtilen programı yürütemiyor" iletisi görüntülenir. Bu hatayı çözmek için, bağımlı derlemelerin ve bunların parçası olan DLL 'Lerin bilgisayara özel veya paylaşılan derlemeler olarak yüklendiğinden emin olun.

## <a name="see-also"></a>Ayrıca bkz.

[Yalıtılmış uygulamalar ve yan yana derlemeler için kavramlar](concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
