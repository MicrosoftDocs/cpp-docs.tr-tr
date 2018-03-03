---
title: "Önceden derlenmiş üst bilgi dosyaları oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- pch
dev_langs:
- C++
helpviewer_keywords:
- precompiled header files, creating
- PCH files, creating
- cl.exe compiler, precompiling code
- .pch files, creating
ms.assetid: e2cdb404-a517-4189-9771-c869c660cb1b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 09c436d55ad7087d407ba580be0b63286b056898
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-precompiled-header-files"></a>Önceden Derlenmiş Üst Bilgi Dosyaları Oluşturma
  
Microsoft C ve C++ Derleyicileri satır içi kod dahil olmak üzere tüm C veya C++ kodu önceden derlemek için seçenekler sağlar. Bu performans özelliğini kullanarak, kod kararlı gövdesi, kod derlenmiş durumu bir dosyada saklayabilir ve, sonraki derlemeler sırasında önceden derlenmiş kod halen geliştirilme aşamasındadır kodu ile birleştirin. Sonraki her derleme daha hızlı çünkü tutarlı kodun derlenmesi gerekmez.  
  
Bu konuda aşağıdaki önceden derlenmiş üst bilgi konuları içerir:  
  
-   [Kaynak kodu önceden derlemek ne zaman](#when-to-precompile-source-code)  
  
-   [Kodu önceden derlemek için iki seçenek](#two-choices-for-precompiling-code)  
  
-   [Önceden derlenmiş başlık tutarlığı kuralları](#precompiled-header-consistency-rules)  
  
-   [Önceden derlenmiş başlıkların dosya başına kullanım için tutarlık kuralları](#consistency-rules-for-per-file-use-of-precompiled-headers)  
  
-   [/Yc ve /Yu için tutarlık kuralları](#consistency-rules-for-yc-and-yu)  
  
-   [Projede önceden derlenmiş başlıkları kullanma](#using-precompiled-headers-in-a-project)  
  
-   [Derleme işlemindeki PCH dosyaları](#pch-files-in-the-build-process)  
  
-   [PCH için örnek derleme görevleri dosyası](#sample-makefile-for-pch)  
  
-   [PCH için örnek kod](#example-code-for-pch)  
  
Önceden derlenmiş üstbilgiler ilgili derleyici seçenekleri hakkında başvuru bilgileri için bkz: [/Y (önceden derlenmiş başlıklar)](../../build/reference/y-precompiled-headers.md).  
  
<a name="when-to-precompile-source-code"></a>  
  
## <a name="when-to-precompile-source-code"></a>Kaynak Kodun Ne Zaman Önceden Derleneceği  
  
Önceden derlenmiş kod derleme süresini azaltmak için geliştirme döngüsü sırasında özellikle yararlıdır:  
  
-   Her zaman çok sık değişmeyen kod büyük gövdesi kullanırsınız.  
  
-   Programınızı tümü dosyaları Ekle ve aynı derleme seçenekleri standart kümesi kullanan birden fazla modülü oluşur. Bu durumda, tüm dosyaları içerecek bir önceden derlenmiş üst bilgi önceden derlenmiş olabilir.  
  
İlk derleme — önceden derlenmiş üst bilgi (PCH) dosyası oluşturur bir — sonraki derlemeler biraz daha uzun sürer. Önceden derlenmiş kod dahil ederek sonraki derlemeler daha hızlı bir şekilde devam edebilirsiniz.  
  
C ve C++ programlarında ön derleme yap. Programlama C++'da, sınıf arabirimi bilgileri üstbilgi dosyalarına ayırmak için yaygın bir uygulamadır. Bu üst bilgi dosyaları daha sonra bir sınıf kullanma programlarda dahil edilebilir. Bu üstbilgileri önceden derleme tarafından bir programı derlemek için geçen süreyi azaltabilir.  
  
> [!NOTE]
>  Kaynak dosya başına yalnızca bir önceden derlenmiş üst bilgi (.pch) dosyasını kullanabilirsiniz, ancak bir projede birden çok .pch dosyaları kullanabilirsiniz.  
  
<a name="two-choices-for-precompiling-code"></a>  
  
# <a name="two-choices-for-precompiling-code"></a>Kodu Önceden Derlemek için İki Seçenek  
  
Visual C++ ile C veya C++ kodu önceden derlemek; yalnızca üst bilgi dosyaları önceden derlemek için sınırlı değildir.  
  
Önceden derleme planlama gerektirir, ancak basit üstbilgi dosyaları dışındaki kaynak kodu önceden derlemek durumlarda önemli ölçüde daha hızlı derlemeleri sağlar.  
  
Kodu önceden derlemek Kaynak dosyalarınız üstbilgi dosyaları ortak kümesi kullanır ancak bunları aynı sırada içerme bildiğiniz durumlarda veya kaynak kodu, ön derlemesi içinde dahil etmek istediğinizde.  
  
Önceden derlenmiş üstbilgi seçenekleri [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md) ve [/Yu (önceden derlenmiş üst bilgi dosyasını kullanma)](../../build/reference/yu-use-precompiled-header-file.md). Kullanım **/Yc** önceden derlenmiş üstbilgi oluşturmak için. İsteğe bağlı ile kullanıldığında [hdrstop](../../preprocessor/hdrstop.md) pragma, **/Yc** , her iki üst bilgi dosyaları önceden derlemek ve kaynak kodu sağlar. Seçin **/Yu** varolan derlemede varolan bir önceden derlenmiş üstbilgi kullanılacak. Aynı zamanda **/Fp** ile **/Yc** ve **/Yu** seçenekleri önceden derlenmiş üstbilgi için alternatif bir ad girin.  
  
Derleyici seçeneği başvuru konuları için **/Yu** ve **/Yc** geliştirme ortamında bu işleve erişmek nasıl ele almaktadır.  
  
<a name="precompiled-header-consistency-rules"></a>  
  
## <a name="precompiled-header-consistency-rules"></a>Önceden Derlenmiş Üst Bilgi Tutarlığı Kuralları  
  
PCH dosyaları makine ortamı hakkında bilgi bilgilerinin yanı sıra bellek adresi program içerdiğinden, yalnızca oluşturulduğu makinedeki bir PCH dosyası kullanmanız gerekir.  
  
<a name="consistency-rules-for-per-file-use-of-precompiled-headers"></a>  
  
## <a name="consistency-rules-for-per-file-use-of-precompiled-headers"></a>Önceden Derlenmiş Üst Bilgilerin Dosya Başına Kullanım için Tutarlık Kuralları

[/Yu](../../build/reference/yu-use-precompiled-header-file.md) derleyici seçeneği kullanmak için hangi PCH dosyasını belirtmenize olanak sağlar.  
  
PCH dosyasını kullandığınızda, aynı derleme ortamı derleyici varsayar — tutarlı derleyici seçenekleri, pragmaları ve benzeri kullanan —, edildi yürürlükte PCH dosyasını oluştururken aksi belirtilmedikçe. Derleyici bir tutarsızlık algılarsa bir uyarı verir ve mümkün olduğunda tutarsızlığı tanımlar. Bu tür uyarılar PCH dosyası ile ilgili bir sorun göstermiyor; Bunlar yalnızca olası çakışmaları sizi uyarır. PCH dosyaları için tutarlılık gereksinimleri aşağıdaki bölümlerde açıklanmıştır.  
  
### <a name="compiler-option-consistency"></a>Derleyici seçeneği tutarlılık  
  
Aşağıdaki derleyici seçenekleri PCH dosyası kullanıldığında bir tutarsızlık uyarı tetikleyebilirsiniz:  
  
-   Önişlemci kullanılarak oluşturulan makroları (/ D) seçeneği oluşturmuş olduğunuz PCH dosyası derleme ve geçerli derleme arasında aynı olması gerekir. Tanımlı sabitler durumunu işaretli, ancak bunlar değiştirirseniz, beklenmedik sonuçlar oluşabilir.  
  
-   PCH dosyaları /E ve /EP seçenekleriyle çalışmaz.  
  
-   PCH dosyaları ya da Gözat bilgisi Oluştur kullanılarak oluşturulmalıdır (/ FR) seçeneğini veya dışarıda yerel değişkenler (/ Fr) PCH dosyası kullanmak sonraki derlemeler bu seçenekleri kullanmadan önce seçeneği.  
  
### <a name="c-70-compatible-z7"></a>C 7.0 uyumlu (/ Z7)  
  
PCH dosyasını oluştururken bu seçeneği etkinse, PCH dosyası kullanmak sonraki derlemeler hata ayıklama bilgileri kullanabilirsiniz.  
  
Varsa 7.0 uyumlu C (/ Z7) seçeneği etkin PCH dosyasını oluştururken, PCH dosya ve /Z7 kullanmaya sonraki derlemelerinin bir uyarı tetikleyecek. Hata ayıklama bilgisi geçerli .obj dosyasında yerleştirilir ve yerel semboller PCH dosyasında tanımlanan hata ayıklayıcısı için kullanılabilir değil.  
  
### <a name="include-path-consistency"></a>Yol tutarlılık içerir  
  
PCH dosyası oluşturulduğunda, yürürlükte olan INCLUDE yolu hakkında bilgi içermiyor. PCH dosyasını kullandığınızda, derleyici geçerli derlemede belirtilen INCLUDE yolu her zaman kullanır.  
  
### <a name="source-file-consistency"></a>Kaynak dosya tutarlılığı  
  
Önceden derlenmiş üstbilgi dosyası kullan (/Yu) seçeneği belirttiğinizde, derleyici önceden derlenmiş kaynak kodunda görünür (pragmaları dahil) tüm önişlemci yönergeleri yok sayar. Bu tür önişlemci yönergeleri tarafından belirtilen derleme önceden derlenmiş üst bilgi dosyası oluştur (/Yc) seçeneği için kullanılan derleme ile aynı olması gerekir.  
  
### <a name="pragma-consistency"></a>Pragma tutarlılık    
  
PCH dosya oluşturma sırasında genellikle işlenen pragmaları ile sonradan PCH dosya kullanılan dosya etkiler. `comment` Ve `message` pragmaları derleme kalanını etkilemez.  
  
Bu pragmaları yalnızca PCH dosya içindeki kod etkiler; Daha sonra PCH dosyası kullanan kodu etkilemez:  
  
||||  
|-|-|-|  
|`comment`|`page`|`subtitle`|  
|`linesize`|`pagesize`|`title`|  
|`message`|`skip`||  
  
Bu pragmaları önceden derlenmiş üst bilgi bir parçası olarak korunur ve önceden derlenmiş üst bilgi kullanan bir derleme kalanı etkiler:  
  
||||  
|-|-|-|  
|`alloc_text`|`include_alias`|`pack`|  
|`auto_inline`|`init_seg`|`pointers_to_members`|  
|`check_stack`|`inline_depth`|`setlocale`|  
|`code_seg`|`inline_recursion`|`vtordisp`|  
|`data_seg`|`intrinsic`|`warning`|  
|`function`|`optimize`||  
  
<a name="consistency-rules-for-yc-and-yu"></a>  
  
## <a name="consistency-rules-for-yc-and-yu"></a>/Yc ve /Yu İçin Tutarlık Kuralları  
  
/Yc veya /Yu kullanılarak oluşturulan önceden derlenmiş üstbilgi kullandığınızda, derleyici geçerli derleme ortamı PCH dosyasını oluştururken var olan bir karşılaştırır. (Tutarlı derleyici seçenekleri, pragmaları vb. kullanarak) öncekinin geçerli derleme için tutarlı bir ortam belirttiğinizden emin olun. Derleyici bir tutarsızlık algılarsa bir uyarı verir ve mümkün olduğunda tutarsızlığı tanımlar. Bu tür uyarılar mutlaka PCH dosyası ile ilgili bir sorun göstermediği; Bunlar yalnızca olası çakışmaları sizi uyarır. Aşağıdaki bölümlerde önceden derlenmiş üst bilgileri için tutarlılık gereksinimleri açıklanmaktadır.  
  
### <a name="compiler-option-consistency"></a>Derleyici seçeneği tutarlılık  
  
Bu tabloda bir tutarsızlık uyarı önceden derlenmiş üst bilgi kullanırken tetikleyebilir derleyici seçenekleri listelenmiştir:  
  
|Seçenek|Ad|Kural|  
|------------|----------|----------|  
|/D|Sabitler ve makroları tanımlama|Önceden derlenmiş üst bilgi oluşturulan derleme ve geçerli derleme arasında aynı olmalıdır. Tanımlı sabitler durumunu işaretli, ancak değiştirilen sabitleri değerlerine dosyalarınızı bağımlı beklenmedik sonuçlar oluşabilir.|  
|/E veya /EP|Önişlemci çıktısını standart çıktıya Kopyala|Önceden derlenmiş üstbilgiler /E veya /EP seçeneğiyle çalışmaz.|  
|/FR veya /FR|Microsoft kaynak tarayıcısı bilgileri oluşturmak|Önceden derlenmiş üst bilgi oluşturulduğunda /Fr ve /FR seçenekleri /Yu seçeneğiyle geçerli olması, bunlar ayrıca yürürlükte verilmiş olması gerekir. Önceden derlenmiş üstbilgi kullanmak sonraki derlemeler Ayrıca kaynak tarayıcısı bilgisi oluşturur. Tarayıcı bilgileri tek .sbr dosyası yerleştirilir ve CodeView bilgileri aynı şekilde diğer dosyalar tarafından başvuruluyor. Kaynak tarayıcı bilgileri yerleşimini geçersiz kılamaz.|  
|/ GA /GD, /GE, /Gw veya /GW|Windows protokolü seçenekleri|Önceden derlenmiş üst bilgi oluşturulan derleme ve geçerli derleme arasında aynı olmalıdır. Bu seçenekler farklıysa, bir uyarı iletisi sonuçlanır.|  
|/Zi|Tam hata ayıklama bilgisi oluştur|Önceden derlenmiş üst bilgi oluşturulduğunda, bu seçeneği etkinse, ön derlemesi kullanan sonraki derlemeler, hata ayıklama bilgileri kullanabilirsiniz. Önceden derlenmiş üst bilgi oluşturulduğunda, / zi etkin değilse, ön derlemesi ve /Zi seçeneği kullanan sonraki derlemelerinin bir uyarı tetikler. Hata ayıklama bilgileri geçerli nesne dosyasında yerleştirilir ve önceden derlenmiş üst bilgi tanımlanan yerel semboller hata ayıklayıcısı için kullanılabilir değil.|  
  
> [!NOTE]
>  Önceden derlenmiş üst bilgi tesis yalnızca C ve C++ kaynak dosyalarını kullanımına yöneliktir.  
  
<a name="using-precompiled-headers-in-a-project"></a>  
  
## <a name="using-precompiled-headers-in-a-project"></a>Projede Önceden Derlenmiş Üst Bilgileri Kullanma  
  
Önceki bölümlerde önceden derlenmiş üstbilgiler genel bir bakış sunar: /Yc ve /Yu, /Fp seçeneği ve [hdrstop](../../preprocessor/hdrstop.md) pragması. Bu bölümde bir proje ile el ile önceden derlenmiş başlık seçeneklerini kullanmak için bir yöntem açıklar; Örnek derleme görevleri dosyası ve yönettiği koduyla sona erer.  
  
Bir proje ile el ile önceden derlenmiş başlık seçeneklerini kullanarak başka bir yaklaşım için Visual C++ varsayılan kurulum sırasında oluşturulur MFC\SRC dizininde bulunan derleme görevleri dosyaları biri üzerinde çalışın. Bu derleme görevleri dosyaları bu bölümde sunulan bir benzer bir yaklaşım uygular, ancak Microsoft Program Bakımı yardımcı programı (NMAKE) makroları büyük kullanılmasını sağlamak ve bu derleme işleminin daha fazla denetim sağlar.  
  
<a name="pch-files-in-the-build-process"></a>  
  
## <a name="pch-files-in-the-build-process"></a>Derleme Sürecindeki PCH Dosyaları  
  
Bir yazılım projenin kod temeli genellikle birden çok C veya C++ kaynak dosyaları, nesne dosyaları, kitaplıklar ve başlık dosyaları içinde yer alır. Genellikle, bir derleme görevleri dosyası bu öğelerin bileşimini yürütülebilir bir dosya halinde düzenler. Aşağıdaki şekilde önceden derlenmiş üst bilgi dosyası kullanan derleme görevleri dosyası yapısını gösterir. NMAKE makrosu adlarını ve dosya adlarını Bu diyagramda bulunan örnek kodda edilenlerle tutarlı [PCH için örnek derleme görevleri dosyası](#sample-makefile-for-pch) ve [PCH için örnek kod](#example-code-for-pch).  
  
Şekil derleme işlem akışını göstermek için üç grafiksel cihazlar kullanır. Dikdörtgenler temsil eder, her dosya veya makro adlı; bir veya daha fazla dosyaları üç makroları gösterir. Gölgeli alanların her derleme veya bağlantı eylemini temsil eder. Oklar, hangi dosyaları ve makroları derleme ve bağlama işlemi sırasında birlikte gösterir.  
  
![Önceden derlenmiş üst bilgi dosyasını kullanan derleme görevleri dosyası](../../build/reference/media/vc30ow1.gif "önceden derlenmiş başlık dosyası kullanan derleme görevleri dosyası yapısı")  
##### <a name="structure-of-a-makefile-that-uses-a-precompiled-header-file"></a>Önceden derlenmiş üst bilgi dosyası kullanan derleme görevleri dosyası yapısı  
  
Diyagram üstünde başlayarak, STABLEHDRS ve sınır NMAKE makroları dosyaları yeniden derlenmek gerek olası değil listesi var. Bu dosyalar komut dizesi tarafından derlenen  
  
`CL /c /W3 /Yc$(BOUNDRY) applib.cpp myapp.cpp`  
  
yalnızca önceden derlenmiş üst bilgi dosyasını (STABLE.pch) yoksa veya iki makrolarındaki listelenen dosyaları değişiklik yaparsanız. Her iki durumda da, önceden derlenmiş üst bilgi dosyası yalnızca STABLEHDRS makro içinde listelenen dosyaların koddan içerir. SINIR makrosu önceden derlenmiş istediğiniz dosyanın son listeleyin.  
  
Bu makroları listesinde dosyaları üstbilgi dosyaları veya C veya C++ kaynak dosyalarını olabilir. (Tek bir PCH dosyası C ve C++ modüllerle kullanılamaz.) Kullanabileceğiniz Not **hdrstop** makrosu ön derlemesi sınır dosyası içinde belirli bir noktada durdurmak için. Bkz: [hdrstop](../../preprocessor/hdrstop.md) daha fazla bilgi için.  
  
Diyagram devam etmeden, APPLIB.obj son uygulamanızda kullanılan destek kodunu temsil eder. APPLIB.cpp oluşturulur, dosya UNSTABLEHDRS makro içinde listelenen ve önceden derlenmiş üst bilgi koddan önceden derlenmiş.  
  
MYAPP.obj son uygulamanızı temsil eder. MYAPP.cpp oluşturulur, dosya UNSTABLEHDRS makro içinde listelenen ve önceden derlenmiş üst bilgi koddan önceden derlenmiş.  
  
Son olarak, yürütülebilir dosya (UYGULAMAM. EXE) OBJS makrosu (APPLIB.obj ve MYAPP.obj) içinde listelenen dosyaların bağlayarak oluşturulur.  
  
<a name="sample-makefile-for-pch"></a>  
  
## <a name="sample-makefile-for-pch"></a>PCH için Örnek Derleme Görevleri Dosyası  
  
Aşağıdaki derleme görevleri dosyası makroları kullanır ve bir! EĞER! BAŞKA! Projeniz için kendi uyarlama basitleştirmek için denetim akışı komutu yapısı ENDIF.  
  
```NMAKE  
# Makefile : Illustrates the effective use of precompiled  
#            headers in a project  
# Usage:     NMAKE option  
# option:    DEBUG=[0|1]  
#            (DEBUG not defined is equivalent to DEBUG=0)  
#  
OBJS = myapp.obj applib.obj  
# List all stable header files in the STABLEHDRS macro.  
STABLEHDRS = stable.h another.h  
# List the final header file to be precompiled here:  
BOUNDRY = stable.h  
# List header files under development here:  
UNSTABLEHDRS = unstable.h  
# List all compiler options common to both debug and final  
# versions of your code here:  
CLFLAGS = /c /W3  
# List all linker options common to both debug and final  
# versions of your code here:  
LINKFLAGS = /NOD /ONERROR:NOEXE  
!IF "$(DEBUG)" == "1"  
CLFLAGS   = /D_DEBUG $(CLFLAGS) /Od /Zi /f  
LINKFLAGS = $(LINKFLAGS) /COD  
LIBS      = slibce  
!ELSE  
CLFLAGS   = $(CLFLAGS) /Oselg /Gs  
LINKFLAGS = $(LINKFLAGS)  
LIBS      = slibce  
!ENDIF  
myapp.exe: $(OBJS)  
    link $(LINKFLAGS) @<<  
$(OBJS), myapp, NUL, $(LIBS), NUL;  
<<  
# Compile myapp  
myapp.obj  : myapp.cpp $(UNSTABLEHDRS)  stable.pch  
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    myapp.cpp  
# Compile applib  
applib.obj : applib.cpp $(UNSTABLEHDRS) stable.pch  
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    applib.cpp  
# Compile headers  
stable.pch : $(STABLEHDRS)  
    $(CPP) $(CLFLAGS) /Yc$(BOUNDRY)    applib.cpp myapp.cpp  
```  
  
"Yapısı, bir derleme görevleri dosyası olduğunu kullanan bir önceden derlenmiş üstbilgi dosyası" çizimde gösterilen STABLEHDRS, sınır ve UNSTABLEHDRS makroları yanı sıra [derleme sürecindeki PCH dosyaları](#pch-files-in-the-build-process), bu derleme görevleri dosyası CLFLAGS makrosu ve bir LINKFLAGS sağlar Makro. Derleme ve hata ayıklama veya yürütülebilir dosya uygulamanın son sürümü derleme olup olmadığını geçerli bağlayıcı seçenekleri listelemek için bu makroları kullanmanız gerekir. Ayrıca vardır KİTAPLIKLAR makrosu listesinde nereye kitaplıklarının projenizi gerektirir.  
  
Derleme görevleri dosyası da kullanır. EĞER! BAŞKA! NMAKE komut satırında bir hata ayıklama simge tanımlamak olup olmadığını algılamak için ENDIF:  
  
```NMAKE  
NMAKE DEBUG=[1|0]  
```  
  
Bu özellik, aynı derleme görevleri dosyası geliştirme sırasında kullanmak ve son sürümleri programınızın mümkün kılar — hata ayıklama kullanmak = 0 son sürümleri için. Aşağıdaki komut satırlarından eşdeğerdir:  
  
```NMAKE  
NMAKE   
NMAKE DEBUG=0  
```  
  
Derleme görevleri dosyaları hakkında daha fazla bilgi için bkz: [NMAKE başvurusu](../../build/nmake-reference.md). Ayrıca bkz. [derleyici seçenekleri](../../build/reference/compiler-options.md) ve [bağlayıcı seçenekleri](../../build/reference/linker-options.md).  
  
<a name="example-code-for-pch"></a>  
  
## <a name="example-code-for-pch"></a>PCH için Örnek Kod  
  
Aşağıdaki kaynak dosyalarını açıklanan makefile kullanılan [derleme sürecindeki PCH dosyaları](#pch-files-in-the-build-process) ve [PCH için örnek derleme görevleri dosyası](#sample-makefile-for-pch). Açıklama önemli bilgiler içeren unutmayın.  
  
```cpp  
// ANOTHER.H : Contains the interface to code that is not  
//             likely to change.  
//  
#ifndef __ANOTHER_H  
#define __ANOTHER_H  
#include<iostream>  
void savemoretime( void );  
#endif // __ANOTHER_H  
```  
  
```cpp  
// STABLE.H : Contains the interface to code that is not likely  
//            to change. List code that is likely to change   
//            in the makefile's STABLEHDRS macro.  
//  
#ifndef __STABLE_H  
#define __STABLE_H  
#include<iostream>  
void savetime( void );  
#endif // __STABLE_H  
```  
  
```cpp  
// UNSTABLE.H : Contains the interface to code that is  
//              likely to change. As the code in a header  
//              file becomes stable, remove the header file  
//              from the makefile's UNSTABLEHDR macro and list  
//              it in the STABLEHDRS macro.  
//  
#ifndef __UNSTABLE_H  
#define __UNSTABLE_H  
#include<iostream.h>  
void notstable( void );  
#endif // __UNSTABLE_H  
```  
  
```cpp
// APPLIB.CPP : This file contains the code that implements  
//              the interface code declared in the header  
//              files STABLE.H, ANOTHER.H, and UNSTABLE.H.  
//  
#include"another.h"  
#include"stable.h"  
#include"unstable.h"  
// The following code represents code that is deemed stable and  
// not likely to change. The associated interface code is  
// precompiled. In this example, the header files STABLE.H and  
// ANOTHER.H are precompiled.  
void savetime( void )  
    { cout << "Why recompile stable code?\n"; }  
void savemoretime( void )  
    { cout << "Why, indeed?\n\n"; }  
// The following code represents code that is still under  
// development. The associated header file is not precompiled.  
void notstable( void )  
    { cout << "Unstable code requires"  
            << " frequent recompilation.\n"; 
    }  
```  
  
```cpp
// MYAPP.CPP : Sample application  
//             All precompiled code other than the file listed  
//             in the makefile's BOUNDRY macro (stable.h in  
//             this example) must be included before the file  
//             listed in the BOUNDRY macro. Unstable code must  
//             be included after the precompiled code.  
//  
#include"another.h"  
#include"stable.h"  
#include"unstable.h"  
int main( void )  
{  
    savetime();  
    savemoretime();  
    notstable();  
}  
```  
    
## <a name="see-also"></a>Ayrıca Bkz.  
[C/C++ oluşturma başvurusu](../../build/reference/c-cpp-building-reference.md)   
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)