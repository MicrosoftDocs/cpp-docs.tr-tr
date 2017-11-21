---
title: "-clr (ortak dil çalışma zamanı derlemesi) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /CLR
- VC.Project.VCNMakeTool.CompileAsManaged
- VC.Project.VCCLCompilerTool.CompileAsManaged
dev_langs: C++
helpviewer_keywords:
- cl.exe compiler, common language runtime option
- -clr compiler option [C++]
- clr compiler option [C++]
- /clr compiler option [C++]
- Managed Extensions for C++, compiling
- common language runtime, /clr compiler option
ms.assetid: fec5a8c0-40ec-484c-a213-8dec918c1d6c
caps.latest.revision: "72"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d6c6882732064b002f0c2d4eef03a0fee2f62287
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
  
 **/ CLR: pure**  
 Bir Microsoft Ara dili (MSIL) üretir-yerel yürütülebilir kod sahip çıktı dosyası. Ancak, yerel türleri için MSIL derlenmiş içerebilir.  
  
 Daha fazla bilgi için bkz: [saf ve doğrulanabilen kod (C + +/ CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 / CLR: pure kullanım dışıdır. Derleyici gelecek bir sürümünde bu seçeneği desteklemiyor olabilir. Saf MSIL C# olmalıdır kod bağlantı noktası öneririz.  
  
 **/ CLR: safe**  
 Bir MSIL yalnızca üretir (hiçbir yerel yürütülebilir kod) doğrulanabilir çıktı dosyası. **/ CLR: safe** doğrulama tanılama sağlar ([PEVerify Aracı (Peverify.exe)](/dotnet/framework/tools/peverify-exe-peverify-tool)).  
  

 / CLR: safe kullanım dışıdır. Derleyici gelecek bir sürümünde bu seçeneği desteklemiyor olabilir. C# saf, doğrulanabilen MSIL olmalıdır kod bağlantı noktası öneririz.  
  
 **/CLR:noAssembly**  
 Derleme bildirimi çıktı dosyasına eklenecek değil olduğunu belirtir. Varsayılan olarak, **noAssembly** seçeneği etkin değil.  
  
 **NoAssembly** seçeneği kullanım dışıdır. Kullanım [/LN (MSIL modülü Oluştur)](../../build/reference/ln-create-msil-module.md) yerine.  
  
 Derleme meta verilerini bildiriminde yok yönetilen bir program olarak bilinen bir *Modülü*. **NoAssembly** seçeneği, yalnızca bir modül üretmek için kullanılabilir. Kullanarak derleme yaparsanız [/c](../../build/reference/c-compile-without-linking.md) ve **/clr:noAssembly**, ardından belirtin [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md) bir modül oluşturmak için bağlayıcı aşamasında seçeneği.  
  
 Visual C++ 2005 önce **/clr:noAssembly** gerekli **/LD**. **/LD** belirttiğinizde şimdi kapsanan **/clr:noAssembly**.  
  
 **/CLR:initialAppDomain**  
 Sağlayan bir [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] CLR sürüm 1 çalıştırmak için uygulama. Kullanırsanız **initialAppDomain**, bazı ele alınmıştır sorunları görebilirsiniz sonra [hata: Visual C++ bileşenleri için Uzantılar yönetilen kullandığınızda AppDomainUnloaded özel durum](http://go.microsoft.com/fwlink/?LinkID=169465) Microsoft Destek Web sitesi.  
  
 Kullanarak derlenmiş bir uygulama **initialAppDomain** CLR 1. sürümü desteklenmediğinden, ASP.NET kullanan bir uygulama tarafından kullanılmamalıdır.  
  
 **/CLR:nostdlib**  
 Varsayılan \clr dizini yok saymak için derleyiciye. DLL System.dll gibi birden fazla sürümünü ekliyorsanız derleyici hataları üretir. Bu seçeneği kullanarak belirli framework derleme sırasında kullanılacak belirtmenize olanak sağlar.  
  
## <a name="remarks"></a>Açıklamalar  
 Yönetilen kod Denetlenmekte ve CLR tarafından yönetilen kodudur. Yönetilen kod yönetilen nesnelere erişebilirsiniz. Daha fazla bilgi için bkz: [/CLR kısıtlamalar](../../build/reference/clr-restrictions.md).  
  
 Tanımlama ve yönetilen türler kullanma uygulamaları geliştirme hakkında daha fazla bilgi için bkz: [çalışma zamanı platformları için bileşen uzantıları](../../windows/component-extensions-for-runtime-platforms.md).  
  
 Bir uygulama kullanarak derlenmiş **/CLR** olabilir veya yönetilen bir veri içermemesi.  
  
 Yönetilen bir uygulama üzerinde hata ayıklamayı etkinleştirmek için bkz: [/ASSEMBLYDEBUG (DebuggableAttribute ekleme)](../../build/reference/assemblydebug-add-debuggableattribute.md).  
  
 Yalnızca CLR Türleri atık toplanan yığında örneği. Daha fazla bilgi için bkz: [sınıflar ve yapılar](../../windows/classes-and-structs-cpp-component-extensions.md). Yerel kod işleve derlemek için kullanmak `unmanaged` pragması. Daha fazla bilgi için bkz: [yönetilen, yönetilmeyen](../../preprocessor/managed-unmanaged.md).  
  
 Varsayılan olarak, **/CLR** etkili değildir. Zaman **/CLR** yürürlükte, **/MD** de etkilidir. Daha fazla bilgi için bkz: [/MD, / MT, /LD (çalışma zamanı kitaplığını kullan)](../../build/reference/md-mt-ld-use-run-time-library.md). **/MD** çalışma zamanı yordamları dinamik olarak bağlanmış, birden çok iş parçacıklı sürümleri standart üstbilgi (.h) dosyalarından seçilmesini sağlar. Çoklu iş parçacığı kullanımı için CLR Atık toplayıcısının yardımcı bir iş parçacığı sonlandırıcılar çalıştığından programlama yönetilen için gereklidir.  
  
 Kullanarak derleme yaparsanız **/c**, sonuçta elde edilen çıktı dosyasıyla CLR türünü (IJW, güvenli veya saf) belirtebilirsiniz [/CLRIMAGETYPE](../../build/reference/clrimagetype-specify-type-of-clr-image.md).  
  
 **/ CLR** gelir **/EHa**ve başka **/EH** için desteklenen seçenekler **/CLR**. Daha fazla bilgi için bkz: [/EH (özel durum işleme modeli)](../../build/reference/eh-exception-handling-model.md).  
  
 Bir dosya CLR görüntü türünü belirleme hakkında daha fazla bilgi için bkz: [/CLRHEADER](../../build/reference/clrheader.md).  
  
 Aynı çalışma zamanı kitaplığı derleyici seçeneği kullanarak belirli bir bağlayıcı çağrılması için geçirilen tüm modüllerin derlenmelidir (**/MD** veya **/LD**).  
  
 Kullanım [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md) kaynak derlemede katıştırmak için bağlayıcı seçeneği. [/ DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md), [/keycontainer](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md), ve [/keyfile](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) bağlayıcı seçenekleri de olanak tanır özelleştirmenize bütünleştirilmiş nasıl oluşturulur.  
  
 Zaman **/CLR** kullanılan `_MANAGED` sembol 1 olarak tanımlanır. Daha fazla bilgi için bkz: [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md).  
  
 Genel değişkenler yerel nesne dosyasına başlatılır (sırasında yürütülebilir bir DLL ise DllMain) ilk ve genel değişkenler yönetilen bölümünde (herhangi bir yönetilen kod çalıştırmadan önce) başlatılır. `#pragma`[init_seg](../../preprocessor/init-seg.md) yalnızca yönetilen ve yönetilmeyen kategorilerdeki başlatma sırasını etkiler.  
  
 Kullanarak derleme **/CLR: safe** kullanarak derleme için benzer [/platform:anycpu](/dotnet/csharp/language-reference/compiler-options/platform-compiler-option) C# gibi dillerde.  
  
## <a name="safe-and-pure-images"></a>Güvenli ve saf görüntüleri  
 Saf görüntü C çalışma zamanı (CRT) kitaplığı CLR sürümü kullanır. Kullanarak derleme CRT kullanmazsınız ancak CRT doğrulanabilen, olmadığından **/CLR: safe**. Daha fazla bilgi için bkz: [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md).  
  
 Saf bir görüntüde yer alamaz yerel kod örnekleri arasında satır içi derleme [setjmp](../../c-runtime-library/reference/setjmp.md), ve [longjmp](../../c-runtime-library/reference/longjmp.md).  
  
 Her giriş noktası saf veya güvenli görüntüsünün yönetilir. Ne zaman derleme kullanarak **/CLR**, yerel giriş noktasıdır. Daha fazla bilgi için bkz: [__clrcall](../../cpp/clrcall.md).  
  
 Ne zaman derleme kullanarak **/CLR: safe**, varsayılan olarak, değişkenlerdir [appdomain](../../cpp/appdomain.md) ve işlem içi olamaz. İçin **/CLR: pure**, ancak **appdomain** varsayılandır kullanabileceğiniz [işlem](../../cpp/process.md) değişkenleri.  
  
 Ne zaman bir 32 bit .exe dosyası çalıştıran derlenmiş kullanarak **/CLR** veya **/CLR: pure** 32-bit üzerinde çalıştırmak 32 bit bir uygulama sağlar WOW64 altında uygulamayı bir 64-bit işletim sisteminde çalıştırılacak CLR bir 64-bit işletim sisteminde. Varsayılan olarak, kullanarak derlenmiş bir .exe dosyası **/CLR: safe** bir 64-bit işletim sistemi çalıştıran bir bilgisayarda 64-bit CLR üzerinde çalışır. (32-bit işletim sisteminde aynı .exe dosyasının 32-bit CLR üzerinde çalışır.) Ancak, güvenli bir uygulama bir 32 bit bileşen yük. 32 bit uygulama (BadFormatException) yüklediğinde, bu durumda, işletim sistemi 64-bit desteği altında çalışan güvenli bir görüntü başarısız olur. Güvenli bir görüntü bir 64-bit işletim sisteminde 32 bit bir görüntü yüklediğinde, çalışmaya devam etmesini sağlamak için kullanmalısınız [/CLRIMAGETYPE](../../build/reference/clrimagetype-specify-type-of-clr-image.md) (.corflags) meta veri değiştirip WOW64 altında çalışmasına işaretlemek için. Aşağıdaki komut satırını bir örnektir. (Kendi giriş simge değiştirin.)  
  
 **cl/CLR: safe t.cpp/Link /clrimagetype: Saf /entry:?main@@$$HYMHXZ /subsystem:console**  
  
 Düzenlenmiş adı alma hakkında daha fazla bilgi için bkz: [donatılmış adları](../../build/reference/decorated-names.md). 64-bit hedefleri hakkında daha fazla bilgi için bkz: [yapılandırma Visual C++ 64-bit, x64 için hedefleri](../../build/configuring-programs-for-64-bit-visual-cpp.md). Saf CLR kod kullanma hakkında daha fazla bilgi için bkz: [nasıl yapılır: pure'a Geçiş: Saf (C + +/ CLI)](../../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md) ve [saf ve doğrulanabilen kod (C + +/ CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
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
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)