---
title: Sorun giderme C/C++ yalıtılmış uygulamalar ve yan yana derlemeler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- troubleshooting side-by-side assemblies
- troubleshooting isolated applications
- troubleshooting Visual C++
ms.assetid: 3257257a-1f0b-4ede-8564-9277a7113a35
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f5645270cbc8fbb71dd841cb4f1affa6bef1295
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="troubleshooting-cc-isolated-applications-and-side-by-side-assemblies"></a>C/C++ Yalıtılmış Uygulamalar ve Yan Yana Derlemeler ile İlgili Sorunları Giderme
C/C++ uygulama yükleme başarısız olabilir bağımlı kitaplıkları bulunamazsa. Bu makalede bir C/C++ uygulaması neden başarısız yüklemek için bazı genel nedenleri ve sorunlarını gidermeye yönelik adımlar önerir.  
  
 Yan yana derleme üzerinde bir bağımlılık belirten bir bildirim içerdiğinden yüklemek bir uygulama başarısız olursa ve derleme yürütülebilir dosya ile aynı klasörde %WINDIR%\WinSxS\ klasöründeki yerel Derleme Önbelleği'ndeki ya da özel bir derleme olarak yüklü değil , aşağıdaki hata iletilerinden birini görüntülenebilir, üzerinde aşağıdakileri uygulamayı çalıştırmak Windows sürümüne bağlı olarak.  
  
-   Uygulama doğru şekilde başlatılamadı (0xc0000135).  
  
-   Bu uygulama, uygulama yapılandırması hatalı olduğu için başlatmak başarısız oldu. Uygulamayı yeniden yüklemeyi bu sorunu çözebilir.  
  
-   Sistem belirtilen programı çalıştıramıyor.  
  
 Uygulamanızı hiçbir bildirim varsa ve Windows tipik arama konumlarda bulamıyor DLL bağlıdır, buna benzer bir hata iletisi görüntülenebilir:  
  
-   Bu uygulama başarısız oldu *gerekli bir DLL* bulunamadı. Uygulamanın yeniden yüklenmesi, bu sorunu çözebilir.  
  
 Uygulamanızı Visual Studio sahip olmayan bir bilgisayarda dağıtılır ve öncekinin benzer hata iletileri ile çöküyor bunlardan kontrol edin:  
  
1.  Açıklanan adımları [bir Visual C++ uygulaması bağımlılıklarını anlama](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md). Bağımlılık bekçisi bir uygulama veya DLL çoğu bağımlılıkları gösterebilirsiniz. Bazı DLL'lerin eksik gözlemlerseniz, bunları uygulamanızı çalıştırmaya çalıştığınız bilgisayara yükleyin.  
  
2.  İşletim sistemi yükleyicisi uygulama bildirimi uygulamanın bağımlı derlemeleri yüklemek için kullanır. Bildirim ikili bir kaynak olarak katıştırılmış veya uygulama klasöründe ayrı bir dosya olarak yüklenir. Bildirim ikili ekli olup olmadığını denetlemek için ikili açmak [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] ve kaynak listesinde için RT_MANIFEST bakın. < Binary_name > şöyle adlandırılmış bir dosya için uygulama klasöründe gömülü bir bildirim bulamazsa, bakın. \<uzantısı > .manifest.  
  
3.  Yan yana derlemelerini uygulamanızı bağlıdır ve bir bildirim yok, bağlayıcı projeniz için bir bildirim oluşturur olmanız gerekir. Bağlayıcı seçeneği işaretleyin **Generate bildirimi** içinde **proje özelliklerini** projesi için iletişim kutusu.  
  
4.  Bildirim ikili eklendiyse, bu kimliği RT_MANIFEST bu ikili dosya türü için doğru olduğundan emin olun. Kullanmak için hangi kaynak kimliği hakkında daha fazla bilgi için bkz: [kullanarak yan yana derlemeler bir kaynak (Windows) olarak](http://msdn.microsoft.com/library/windows/desktop/aa376617.aspx). Bildirim ayrı bir dosyaya ise, bir XML Düzenleyicisi'ni veya metin düzenleyicide açın. Bildirimler ve dağıtım için kuralları hakkında daha fazla bilgi için bkz: [bildirimleri](http://msdn.microsoft.com/library/aa375365).  
  
    > [!NOTE]
    >  Gömülü bir bildirim ve ayrı bir bildirim dosyası varsa, işletim sistemi yükleyicisi katıştırılmış bildirimini kullanır ve ayrı bir dosya yok sayar. Ancak, Windows XP'de, bunun tersi geçerlidir — ayrı bildirim dosyası kullanılır ve katıştırılmış bildirimi göz ardı edilir.  
  
5.  Ancak bir DLL yüklendiğinde, dış bildirimleri göz ardı edilir çünkü her DLL'de bir bildirimi katıştırmak öneririz bir `LoadLibrary` çağırın. Daha fazla bilgi için bkz: [derleme bildirimleri](http://msdn.microsoft.com/library/aa374219).  
  
6.  Bildirimde numaralandırılır tüm derlemelerde bilgisayara düzgün yüklendiğini denetleyin. Her derleme bildiriminde ad, sürüm numarasını ve işlemci mimarisi tarafından belirtilir. Yan yana derlemelerini uygulamanızı bağımlı olması durumunda, işletim sistemi yükleyicisi bunları bulabilmesi için bu derlemeler doğru bilgisayarda açıklandığı gibi yüklü olup olmadığını denetleyin [derleme arama sırası](http://msdn.microsoft.com/library/aa374224). 64-bit derlemeleri 32 bit işlemde yüklenemiyor ve 32-bit işletim sistemlerinde yürütülemez unutmayın.  
  
## <a name="example"></a>Örnek  
 Bir uygulama, Visual C++ kullanarak yerleşik appl.exe sahibiz varsayalım. Uygulama bildirimini ikili kaynak 1 kimliği eşit olan veya ayrı bir dosya appl.exe.manifest depolanan RT_MANIFEST appl.exe içinde ya da katıştırılır. Bu bildirimi içeriğini bu benzer:  
  
```  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <dependency>  
    <dependentAssembly>  
      <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"></assemblyIdentity>  
    </dependentAssembly>  
  </dependency>  
</assembly>  
```  
  
 Bu appl.exe bağlı olan bir 32 bit x86 için yerleşik Fabrikam.SxS.Library, sürüm 2.0.20121.0, adlı bir derleme, işletim sistemi yükleyicisi için bu bildirimi diyor İşlemci mimarisi. Bağımlı yan yana derleme, paylaşılan bir derleme veya özel bir derleme olarak yüklenebilir.  
  
 Paylaşılan bir derleme için derleme bildirimi %WINDIR%\WinSxS\Manifests\ klasörüne yüklenir. Derleme tanımlar ve içeriğini listeler — diğer bir deyişle, derleme parçası olan DLL'leri:  
  
```  
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
   <noInheritable/>  
   <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"/>  
   <file name="Fabrikam.Main.dll" hash="3ca5156e8212449db6c622c3d10f37d9adb1ab12" hashalg="SHA1"/>  
   <file name="Fabrikam.Helper.dll" hash="92cf8a9bb066aea821d324ca4695c69e55b2d1c2" hashalg="SHA1"/>  
</assembly>  
```  
  
 Yan yana derlemeler de kullanabilir [yayımcı yapılandırma dosyalarını](http://msdn.microsoft.com/library/aa375682)— ilke dosyaları olarak da bilinir — genel olarak uygulamalar ve derlemeler başka bir sürümü aynı yerine bir yan yana derleme bir sürümünü kullanmak üzere yeniden yönlendirmek için derleme. Paylaşılan bir derleme %WINDIR%\WinSxS\Policies\ klasöründeki ilkeleri kontrol edebilirsiniz. Aşağıda, bir ilke dosyası örneği verilmiştir:  
  
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
  
 Bu ilke dosyası herhangi bir uygulama veya bu derleme 2.0.10000.0 sürümü ister derleme yerine sürüm 2.0.20121.0, sistemde yüklü geçerli sürümünün olduğu kullanması gerektiğini belirtir. Uygulama bildiriminde belirtilen derleme sürümü ilke dosyasında belirtilmediği takdirde, yükleyici %WINDIR%\WinSxS\ klasöründeki bildiriminde belirtilen bu derleme sürümü arar ve bu sürümü yüklü değilse, yükleme başarısız olur. Ve derleme sürümü 2.0.20121.0 yüklü değilse, yükleme derleme sürümü 2.0.10000.0 isteyin uygulamalar için başarısız olur.  
  
 Ancak, derleme yüklü uygulama klasöründe özel bir yan yana derleme olarak da yüklenebilir. Derleme paylaşılan bir derlemede olarak bulmak işletim sistemi başarısız olursa, bunun için aşağıdaki sırayla özel bir derleme olarak görünüyor:  
  
1.  Adına sahip bir bildirim dosyası için uygulama klasörünü denetleyin \<assemblyName > .manifest. Bu örnekte, yükleyici appl.exe içeren klasöre Fabrikam.SxS.Library.manifest bulmaya çalışır. Bildirim bulursa yükleyicisi uygulama klasöründen derleme yükler. Derleme bulunmazsa yükleme başarısız olur.  
  
2.  Açmaya \\< assemblyName\>\ klasöründe appl.exe, içeren ve \\< assemblyName\>\ yoksa, adına sahip bir bildirim dosyası yüklenmeye \<assemblyName >. Bu klasörden bildirimi. Bildirim bulunursa, yükleyicisi derlemeden yükler \\< assemblyName\>\ klasör. Derleme bulunmazsa yükleme başarısız olur.  
  
 Yükleyici için bağımlı derlemeleri nasıl arayacağını hakkında daha fazla bilgi için bkz: [derleme arama sırası](http://msdn.microsoft.com/library/aa374224). Özel derleme olarak bağımlı bir derleme bulmak yükleyici başarısız olursa, yükleme başarısız olur ve "Sistem belirtilen programı çalıştıramıyor" iletisi görüntülenir. Bu hatayı gidermek için emin olun bağımlı derlemeleri — ve bunları parçası olan DLL'ler — bilgisayarda özel veya paylaşılan derlemeler yüklenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yalıtılmış uygulamalar ve yan yana derlemeler kavramları](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)