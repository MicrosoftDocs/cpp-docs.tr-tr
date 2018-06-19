---
title: -clr (ortak dil çalışma zamanı derlemesi) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /CLR
- VC.Project.VCNMakeTool.CompileAsManaged
- VC.Project.VCCLCompilerTool.CompileAsManaged
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, common language runtime option
- -clr compiler option [C++]
- clr compiler option [C++]
- /clr compiler option [C++]
- Managed Extensions for C++, compiling
- common language runtime, /clr compiler option
ms.assetid: fec5a8c0-40ec-484c-a213-8dec918c1d6c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1284d0300fcea3adc5f2884a7d1eff7862ff2b65
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379620"
---
# <a name="clr-common-language-runtime-compilation"></a>/clr (Ortak Dil Çalışma Zamanı Derlemesi)
Ortak dil çalışma zamanı (CLR) özellikleri kullanmak için uygulamaları ve bileşenleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/clr[:options]  
```  
  
## <a name="arguments"></a>Arguments  
 `options`  
 Bir veya daha fazla aşağıdaki anahtarları, virgülle ayrılmış.  
  
 **/ CLR**  
 Uygulama meta verilerini oluşturur. Meta verileri diğer CLR uygulamaları tarafından kullanılabilecek ve uygulama türleri ve CLR bileşenlerle meta veri tüketmek sağlar.  
  
 Daha fazla bilgi için bkz.  
  
 [Karışık (yerel ve yönetilen) derlemeler](../../dotnet/mixed-native-and-managed-assemblies.md) ve  
  
 [Nasıl yapılır: pure'a Geçiş](../../dotnet/how-to-migrate-to-clr.md).  
  
 **/clr:pure**  
 / CLR: pure kullanım dışıdır. Derleyici gelecek bir sürümünde bu seçeneği desteklemiyor olabilir. Saf MSIL C# olmalıdır kod bağlantı noktası öneririz.  
  
 **/clr:safe**  
 / CLR: safe kullanım dışıdır. Derleyici gelecek bir sürümünde bu seçeneği desteklemiyor olabilir. C# Güvenli MSIL olmalıdır kod bağlantı noktası öneririz. 
  
 **/clr:noAssembly**  
 Derleme bildirimi çıktı dosyasına eklenecek değil olduğunu belirtir. Varsayılan olarak, **noAssembly** seçeneği etkin değil.  
  
 **NoAssembly** seçeneği kullanım dışıdır. Kullanım [/LN (MSIL modülü Oluştur)](../../build/reference/ln-create-msil-module.md) yerine.  
  
 Derleme meta verilerini bildiriminde yok yönetilen bir program olarak bilinen bir *Modülü*. **NoAssembly** seçeneği, yalnızca bir modül üretmek için kullanılabilir. Kullanarak derleme yaparsanız [/c](../../build/reference/c-compile-without-linking.md) ve **/clr:noAssembly**, ardından belirtin [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md) bir modül oluşturmak için bağlayıcı aşamasında seçeneği.  
  
 Visual C++ 2005 önce **/clr:noAssembly** gerekli **/LD**. **/LD** belirttiğinizde şimdi kapsanan **/clr:noAssembly**.  
  
 **/clr:initialAppDomain**  
 Sağlayan bir [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] CLR sürüm 1 çalıştırmak için uygulama. Kullanırsanız **initialAppDomain**, bazı ele alınmıştır sorunları görebilirsiniz sonra [hata: Visual C++ bileşenleri için Uzantılar yönetilen kullandığınızda AppDomainUnloaded özel durum](http://go.microsoft.com/fwlink/p/?linkid=169465) Microsoft Destek Web sitesi.  
  
 Kullanarak derlenmiş bir uygulama **initialAppDomain** CLR 1. sürümü desteklenmediğinden, ASP.NET kullanan bir uygulama tarafından kullanılmamalıdır.  
  
 **/clr:nostdlib**  
 Varsayılan \clr dizini yok saymak için derleyiciye. DLL System.dll gibi birden fazla sürümünü ekliyorsanız derleyici hataları üretir. Bu seçeneği kullanarak belirli framework derleme sırasında kullanılacak belirtmenize olanak sağlar.  
  
## <a name="remarks"></a>Açıklamalar  
 Yönetilen kod Denetlenmekte ve CLR tarafından yönetilen kodudur. Yönetilen kod yönetilen nesnelere erişebilirsiniz. Daha fazla bilgi için bkz: [/CLR kısıtlamalar](../../build/reference/clr-restrictions.md).  
  
 Tanımlama ve yönetilen türler kullanma uygulamaları geliştirme hakkında daha fazla bilgi için bkz: [çalışma zamanı platformları için bileşen uzantıları](../../windows/component-extensions-for-runtime-platforms.md).  
  
 Bir uygulama kullanarak derlenmiş **/CLR** olabilir veya yönetilen bir veri içermemesi.  
  
 Yönetilen bir uygulama üzerinde hata ayıklamayı etkinleştirmek için bkz: [/ASSEMBLYDEBUG (DebuggableAttribute ekleme)](../../build/reference/assemblydebug-add-debuggableattribute.md).  
  
 Yalnızca CLR Türleri atık toplanan yığında örneği. Daha fazla bilgi için bkz: [sınıflar ve yapılar](../../windows/classes-and-structs-cpp-component-extensions.md). Yerel kod işleve derlemek için kullanmak `unmanaged` pragması. Daha fazla bilgi için bkz: [yönetilen, yönetilmeyen](../../preprocessor/managed-unmanaged.md).  
  
 Varsayılan olarak, **/CLR** etkili değildir. Zaman **/CLR** yürürlükte, **/MD** de etkilidir. Daha fazla bilgi için bkz: [/MD, / MT, /LD (çalışma zamanı kitaplığını kullan)](../../build/reference/md-mt-ld-use-run-time-library.md). **/MD** çalışma zamanı yordamları dinamik olarak bağlanmış, birden çok iş parçacıklı sürümleri standart üstbilgi (.h) dosyalarından seçilmesini sağlar. Çoklu iş parçacığı kullanımı için CLR Atık toplayıcısının yardımcı bir iş parçacığı sonlandırıcılar çalıştığından programlama yönetilen için gereklidir.  
  
 Kullanarak derleme yaparsanız **/c**, sonuçta elde edilen çıktı dosyasıyla CLR türünü belirtebilirsiniz [/CLRIMAGETYPE](../../build/reference/clrimagetype-specify-type-of-clr-image.md).  
  
 **/ CLR** gelir **/EHa**ve başka **/EH** için desteklenen seçenekler **/CLR**. Daha fazla bilgi için bkz: [/EH (özel durum işleme modeli)](../../build/reference/eh-exception-handling-model.md).  
  
 Bir dosya CLR görüntü türünü belirleme hakkında daha fazla bilgi için bkz: [/CLRHEADER](../../build/reference/clrheader.md).  
  
 Aynı çalışma zamanı kitaplığı derleyici seçeneği kullanarak belirli bir bağlayıcı çağrılması için geçirilen tüm modüllerin derlenmelidir (**/MD** veya **/LD**).  
  
 Kullanım [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md) kaynak derlemede katıştırmak için bağlayıcı seçeneği. [/ DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md), [/keycontainer](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md), ve [/keyfile](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) bağlayıcı seçenekleri de olanak tanır özelleştirmenize bütünleştirilmiş nasıl oluşturulur.  
  
 Zaman **/CLR** kullanılan `_MANAGED` sembol 1 olarak tanımlanır. Daha fazla bilgi için bkz: [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md).  
  
 Genel değişkenler yerel nesne dosyasına başlatılır (sırasında yürütülebilir bir DLL ise DllMain) ilk ve genel değişkenler yönetilen bölümünde (herhangi bir yönetilen kod çalıştırmadan önce) başlatılır. `#pragma`[init_seg](../../preprocessor/init-seg.md) yalnızca yönetilen ve yönetilmeyen kategorilerdeki başlatma sırasını etkiler.  
  
## <a name="metadata-and-unnamed-classes"></a>Meta veri ve adsız sınıfları  
 Adlandırılmamış sınıflar gibi adlı meta verilerde görünecektir: `$UnnamedClass$` *crc-in-geçerli-dosya adı*`$`*dizin*`$`, burada *dizin*derleme adlandırılmamış sınıflarda sıralı sayısıdır. Örneğin, aşağıdaki kod örneği, meta verilerde adsız bir sınıf oluşturur.  
  
```  
// clr_unnamed_class.cpp  
// compile by using: /clr /LD  
class {} x;  
```  
  
 İldasm.exe meta verileri görüntülemek için kullanın.  
  
## <a name="managed-extensions-for-c"></a>C++ için Yönetilen Uzantılar  
 Visual C++ artık destekler **/clr:oldsyntax** seçeneği. Bu seçenek, Visual Studio 2005'te kullanımdan kaldırılmıştır. Desteklenen için yönetilen kod yazma c++ C + söz dizimi +/ CLI. Daha fazla bilgi için bkz: [çalışma zamanı platformları için bileşen uzantıları](../../windows/component-extensions-for-runtime-platforms.md).  
  
 C++ için Yönetilen Uzantılar kullanan kodu varsa, C + kullanacak şekilde bağlantı öneririz +/ CLI sözdizimi. Kodunuzu bağlantı noktası hakkında daha fazla bilgi için bkz: [C + +/ CLI geçiş öncüsü](../../dotnet/cpp-cli-migration-primer.md).  
  
#### <a name="to-set-this-compiler-option-in-visual-studio"></a>Visual Studio'da Bu derleyici seçeneği ayarlamak için  
  
1.  İçinde **Çözüm Gezgini**, proje adına sağ tıklayın ve ardından **özellikleri** projeyi açmak için **özellik sayfaları** iletişim kutusu.  
  
2.  Seçin **yapılandırma özellikleri** klasör.  
  
3.  Üzerinde **genel** özellik sayfasında, değişiklik **ortak dil çalışma zamanı Destek** özelliği.  
  
    > [!NOTE]
    >  Zaman **/CLR** etkin **özellik sayfaları** iletişim kutusu, uyumlu olmayan derleyici seçeneği özellikleri **/CLR** da ayarlanır, gerektiği gibi. Örneğin, varsa **eş yordamlarla/RTC** ayarlanır ve ardından **/CLR** etkin, **eş yordamlarla/RTC** devre dışı bırakılacak.  
    >   
    >  Ayrıca, ne zaman hata ayıklama bir **/CLR** uygulama ayarlamak **hata ayıklayıcı türü** özelliğine **karma** veya **yalnızca yönetilen**. Daha fazla bilgi için bkz: [bir C++ hata ayıklama yapılandırması proje ayarları](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration).  
  
     Bir modül oluşturma hakkında bilgi için bkz [/NOASSEMBLY (MSIL modülü Oluştur)](../../build/reference/noassembly-create-a-msil-module.md).  
  
#### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAsManaged%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)