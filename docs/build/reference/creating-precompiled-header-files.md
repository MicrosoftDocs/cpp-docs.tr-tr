---
title: Önceden derlenmiş üst bilgi dosyaları oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e050532de79a82291948862840b4c8fa6a3b4995
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703209"
---
# <a name="creating-precompiled-header-files"></a>Önceden Derlenmiş Üst Bilgi Dosyaları Oluşturma

Microsoft C and C++ Derleyicileri, satır içi kod dahil olmak üzere tüm C veya C++ kodu önceden derlemek için seçenekler sağlar. Bu performans özelliği kullanarak, kod kararlı gövdesi, kodun derlenmiş hali bir dosyada depolar ve, sonraki derleme sırasında önceden derlenmiş kod hala geliştirilmekte olan kod ile birleştirin. Tutarlı kodun derlenmesi gerekmez çünkü her sonraki derleme daha hızlıdır.

Bu konu, önceden derlenmiş üst bilgi aşağıdaki konuları içerir:

- [Kaynak kodu önceden derlemek ne zaman](#when-to-precompile-source-code)

- [Kodu önceden derlemek için iki seçenek](#two-choices-for-precompiling-code)

- [Önceden derlenmiş üst bilgi tutarlığı kuralları](#precompiled-header-consistency-rules)

- [Önceden derlenmiş üst bilgilerin dosya başına kullanım için tutarlık kuralları](#consistency-rules-for-per-file-use-of-precompiled-headers)

- [/Yc ve /Yu için tutarlık kuralları](#consistency-rules-for-yc-and-yu)

- [Projede önceden derlenmiş üst bilgileri kullanma](#using-precompiled-headers-in-a-project)

- [Derleme sürecindeki PCH dosyaları](#pch-files-in-the-build-process)

- [PCH için örnek derleme görevleri dosyası](#sample-makefile-for-pch)

- [PCH için örnek kod](#example-code-for-pch)

Önceden derlenmiş üst bilgiler için ilgili derleyici seçenekleri hakkında başvuru bilgileri için bkz [/Y (önceden derlenmiş üst bilgiler)](../../build/reference/y-precompiled-headers.md).

<a name="when-to-precompile-source-code"></a>

## <a name="when-to-precompile-source-code"></a>Kaynak Kodun Ne Zaman Önceden Derleneceği

Önceden derlenmiş kod geliştirme döngüsü sırasında derleme zamanı azaltmak için özellikle yararlıdır:

- Her zaman büyük seyrek değişen kod gövdesi de kullanın.

- Programınız her biri bir standart içerme dosyaları ve aynı derleme seçenekleri kullanan birden çok modül oluşur. Bu durumda, tüm dosyaları içerecek bir önceden derlenmiş üst bilgi önceden derlenmiş olabilir.

İlk derleme — (PCH) önceden derlenmiş üst bilgi dosyası oluşturur bir — sonraki derlemeler biraz daha uzun sürer. Sonraki derlemeler önceden derlenmiş kod ekleyerek daha hızlı bir şekilde devam edebilirsiniz.

Hem C ve C++ programları ön derleme. Programlama C++'da, sınıf arabirimi bilgileri üstbilgi dosyalarına ayırmak için yaygın bir uygulamadır. Bu üst bilgi dosyaları, daha sonra sınıfı kullanan programlarda eklenebilir. Bu üstbilgileri önceden derlemek tarafından bir programı derlemek için gereken süreyi azaltabilir.

> [!NOTE]
>  Kaynak dosya yalnızca bir önceden derlenmiş üst bilgi (.pch) dosyasını kullanabilirsiniz, ancak bir projede birden çok .pch dosyaları kullanabilirsiniz.

<a name="two-choices-for-precompiling-code"></a>

# <a name="two-choices-for-precompiling-code"></a>Kodu Önceden Derlemek için İki Seçenek

Visual C++ ile herhangi bir C veya C++ kodu önceden derlemek; yalnızca üst bilgi dosyaları önceden derlemek için sınırlı değildir.

Önceden derleme planlama gerektirir, ancak basit bir üst bilgi dosyaları dışındaki kaynak kodu önceden derlemek, önemli ölçüde daha hızlı derlemeler sağlar.

Kod, kaynak dosyalarınızda ortak başlık dosyaları kümesi kullanın ancak bunları aynı sırada içermez bildiğinizde ya da kaynak kodu, ön derleme içinde dahil etmek istediğiniz ön derleme.

Önceden derlenmiş üst bilgi seçenekleri [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md) ve [/Yu (önceden derlenmiş üst bilgi dosyasını kullanma)](../../build/reference/yu-use-precompiled-header-file.md). Kullanım **/Yc** bir önceden derlenmiş üst bilgi oluşturulacak. İsteğe bağlı ile kullanıldığında [hdrstop](../../preprocessor/hdrstop.md) pragması **/Yc** her iki başlık dosyası ön derleme ve kaynak kodu sağlar. Seçin **/Yu** mevcut derlemede varolan önceden derlenmiş üst bilgi kullanılacak. Ayrıca **/FP** ile **/Yc** ve **/Yu** önceden derlenmiş üst bilgi alternatif bir ad vermek için Seçenekler.

Derleyici seçeneği başvuru konusundan **/Yu** ve **/Yc** geliştirme ortamındaki bu işleve erişmek nasıl ele almaktadır.

<a name="precompiled-header-consistency-rules"></a>

## <a name="precompiled-header-consistency-rules"></a>Önceden Derlenmiş Üst Bilgi Tutarlığı Kuralları

PCH dosyaları makine ortamı hakkında bilgi bilgilerinin yanı sıra bellek adresi program içerdiğinden, yalnızca oluşturulduğu, makinedeki bir PCH dosyası kullanmanız gerekir.

<a name="consistency-rules-for-per-file-use-of-precompiled-headers"></a>

## <a name="consistency-rules-for-per-file-use-of-precompiled-headers"></a>Önceden Derlenmiş Üst Bilgilerin Dosya Başına Kullanım için Tutarlık Kuralları

[/Yu](../../build/reference/yu-use-precompiled-header-file.md) derleyici seçeneği kullanmak için hangi PCH dosyası belirtmenize olanak sağlar.

PCH dosyası kullandığınızda, derleyici aynı derleme ortamı varsayar — tutarlı derleyici seçenekleri, pragmalar vb. kullanan bir — olan geçerli PCH dosyası oluştururken, aksini belirtmediğiniz sürece. Derleyici bir tutarsızlık algılarsa bir uyarı verir ve mümkün olduğunda tutarsızlığı tanımlar. Bu tür uyarılar PCH dosyası ile ilgili bir sorun göstermez; Bunlar yalnızca olası çakışmaların uyar. PCH dosyaları tutarlılık gereksinimleri, aşağıdaki bölümlerde açıklanmıştır.

### <a name="compiler-option-consistency"></a>Derleyici seçeneği tutarlılık

Aşağıdaki derleyici seçeneklerinin PCH dosyası kullanırken bir tutarsızlık uyarı tetikleyebilir:

- Önişlemci kullanılarak oluşturulan makroları (/ D) seçeneği PCH dosyası oluşturulan derleme ve geçerli derleme arasında aynı olması gerekir. Tanımlı sabitler durumunu işaretli, ancak bunlar değiştirirseniz, beklenmeyen sonuçlar oluşabilir.

- PCH dosyaları /E ve /EP seçenekleriyle birlikte çalışmaz.

- PCH dosyaları ya da Gözat bilgisi Oluştur kullanılarak oluşturulmalıdır (/ FR) seçeneği veya dışarıda yerel değişkenler (/ Fr) PCH dosyası kullanan sonraki derlemeler bu seçenekler kullanabilmeniz için seçenek.

### <a name="c-70-compatible-z7"></a>C 7.0 uyumlu (/ Z7)

PCH dosyası oluşturulduğunda bu seçenek geçerli ise PCH dosyası kullanan sonraki derleme, hata ayıklama bilgileri kullanabilirsiniz.

C 7.0 uyumlu (/ Z7) seçeneği etkin PCH dosyası oluşturulduğunda, / z7 ve PCH dosyası kullanan sonraki derlemeler bir uyarı tetikler. Hata ayıklama bilgileri geçerli bir .obj dosyasında yerleştirilir ve yerel semboller PCH dosyasında tanımlanan hata ayıklayıcısı için kullanılabilir değil.

### <a name="include-path-consistency"></a>Yol tutarlılık içerir

PCH dosyası oluşturulduğunda, yürürlükte olan yoluna hakkında bilgi içermiyor. PCH dosyası kullandığınızda, derleyici her zaman geçerli derlemede belirtilen yoluna kullanır.

### <a name="source-file-consistency"></a>Kaynak dosya tutarlılığı

Önceden derlenmiş üst bilgi dosyasını kullanma (/Yu) seçeneğini belirttiğinizde, derleyici kaynak kodda önceden derlenmiş (pragmaları dahil) tüm önişlemci yönergeleri yok sayar. Bu tür önişlemci yönergeleri tarafından belirtilen derleme seçeneği önceden derlenmiş üst bilgi dosyası oluştur (/Yc) için kullanılan derleme ile aynı olmalıdır.

### <a name="pragma-consistency"></a>Pragma tutarlılık

PCH dosyası oluşturma sırasında genellikle işlenen pragmalar, sonradan PCH dosyası kullanılan dosya etkiler. `comment` Ve `message` pragmaları derleme geri kalanında etkilemez.

Bu pragmaları yalnızca PCH dosyası içindeki kod etkiler; Daha sonra PCH dosyası kullanan kodu etkilemez:

||||
|-|-|-|
|`comment`|`page`|`subtitle`|
|`linesize`|`pagesize`|`title`|
|`message`|`skip`||

Bu pragmalar, önceden derlenmiş üstbilgi bir parçası olarak korunur ve önceden derlenmiş üst bilgi kullanan derleme geri kalanında etkiler:

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

/Yc veya /Yu kullanılarak oluşturulan önceden derlenmiş üst bilgi kullandığınızda, derleyici PCH dosyası oluştururken var olan bir geçerli derleme ortamı karşılaştırır. (Tutarlı derleyici seçenekleri, pragmalar vb. kullanarak) önceki bir geçerli derleme için tutarlı bir ortam belirttiğinizden emin olun. Derleyici bir tutarsızlık algılarsa bir uyarı verir ve mümkün olduğunda tutarsızlığı tanımlar. Bu tür uyarılar, mutlaka PCH dosyası ile ilgili bir sorun göstermediği; Bunlar yalnızca olası çakışmaların uyar. Aşağıdaki bölümlerde, önceden derlenmiş üst bilgiler için tutarlılık gereksinimleri açıklanmaktadır.

### <a name="compiler-option-consistency"></a>Derleyici seçeneği tutarlılık

Bu tablo, bir önceden derlenmiş üst bilgi kullanırken bir tutarsızlık uyarı tetikleyebilir derleyici seçenekleri listeler:

|Seçenek|Ad|Kural|
|------------|----------|----------|
|/D|Sabitleri ve makroları tanımlama|Önceden derlenmiş üst bilgi oluşturulan derleme ve geçerli derleme arasında aynı olması gerekir. Tanımlı sabitler durumunu işaretli, ancak dosyalarınızı değiştirilen sabitlerin değerlerine bağımlı beklenmeyen sonuçlar oluşabilir.|
|/E veya /EP|Önişlemci çıktısını standart çıktıya Kopyala|Önceden derlenmiş üst bilgiler /E veya /EP seçeneğiyle çalışmaz.|
|/FR veya /FR|Microsoft kaynak tarayıcı bilgilerini oluştur|Önceden derlenmiş üstbilgi oluşturulduğunda /Fr ve /FR seçenekleri /Yu seçeneğiyle geçerli olması, bunlar da aslında verilmiş olması gerekir. Önceden derlenmiş üst bilgi kullanan sonraki derlemeler, kaynak tarayıcı bilgileri de oluşturur. Tarayıcı bilgileri tek .sbr dosyasında yerleştirilir ve aynı şekilde CodeView bilgisi olarak diğer dosyalar tarafından başvuruluyor. Kaynak tarayıcı bilgileri yerleşimini geçersiz kılamaz.|
|/ GA, /GD, /GE, /Gw veya /GW|Windows protokol seçenekleri|Önceden derlenmiş üst bilgi oluşturulan derleme ve geçerli derleme arasında aynı olması gerekir. Bu seçenekler farklıysa, bir uyarı iletisi sonuçlanır.|
|/Zi|Tam hata ayıklama bilgileri üret|Ön derlenmiş üstbilgi oluşturulduğunda bu seçeneği etkinse, ön derleme kullanan sonraki derleme, hata ayıklama bilgileri kullanabilirsiniz. Ön derlenmiş üstbilgi oluşturulduğunda / zi etkin değilse, ön derleme ve/zi seçeneğini kullanan sonraki derlemeler bir uyarı tetikler. Hata ayıklama bilgileri geçerli nesne dosyasında yerleştirilir ve yerel semboller derlenmiş üstbilgide tanımlanan hata ayıklayıcısı için kullanılabilir değil.|

> [!NOTE]
>  Önceden derlenmiş üst bilgi özelliği yalnızca C ve C++ kaynak dosyaları kullanımına yöneliktir.

<a name="using-precompiled-headers-in-a-project"></a>

## <a name="using-precompiled-headers-in-a-project"></a>Projede Önceden Derlenmiş Üst Bilgileri Kullanma

Önceki bölümlerde, önceden derlenmiş üst bilgiler genel bir bakış sunar: /Yc ve /Yu/FP seçeneği ve [hdrstop](../../preprocessor/hdrstop.md) pragması. Bu bölümde, bir projede el ile önceden derlenmiş üst bilgi Seçenekleri'ni kullanarak bir yöntem anlatılmaktadır; bir örnek derleme görevleri dosyası ve yönettiği kod ile sona erer.

Bir projede el ile önceden derlenmiş üst bilgi Seçenekleri'ni kullanarak başka bir yaklaşım için bir Visual C++ varsayılan kurulum sırasında oluşturulur MFC\SRC dizininde bulunan derleme görevleri dosyalarını inceleyin. Bu derleme görevleri dosyalarını bu bölümde sunulan bir benzer bir yaklaşım yararlanın ancak Microsoft Program Bakımı yardımcı programı (NMAKE) makroları büyük kullanılmasını sağlamak ve yapı işleminin daha fazla denetim sağlar.

<a name="pch-files-in-the-build-process"></a>

## <a name="pch-files-in-the-build-process"></a>Derleme Sürecindeki PCH Dosyaları

Bir yazılım projesinde kod tabanını genellikle birden çok C veya C++ kaynak dosyaları, nesne dosyaları, kitaplıklar ve üst bilgi dosyaları içinde yer alır. Genellikle, bir derleme görevleri dosyası bu öğeleri birleşimi bir yürütülebilir dosyasına düzenler. Aşağıdaki şekilde önceden derlenmiş üst bilgi dosyası kullanan derleme görevleri dosyası yapısı gösterilmektedir. NMAKE makrosu adları ve dosya adları Bu diyagramda bulunan örnek kodda tutarlı [PCH için örnek derleme görevleri dosyası](#sample-makefile-for-pch) ve [PCH için örnek kod](#example-code-for-pch).

Şekil, yapı işleminin akışını göstermek için üç içeren cihazlarda kullanır. Her dosya veya makro dikdörtgenler temsil adlı; üç makroları, bir veya daha fazla dosyayı temsil eder. Gölgeli alanları her derleme veya bağlantı eylemi temsil eder. Oklar, hangi dosyaları ve makroları derleme ve bağlama işlemi sırasında birleştirilir gösterir.

![Önceden derlenmiş üst bilgi dosyası kullanan derleme görevleri dosyası](../../build/reference/media/vc30ow1.gif "önceden derlenmiş bir üstbilgi dosyası kullanan derleme görevleri dosyası yapısı")
##### <a name="structure-of-a-makefile-that-uses-a-precompiled-header-file"></a>Önceden derlenmiş üst bilgi dosyası kullanan derleme görevleri dosyası yapısı

Diyagramın üst kısmında başlayarak STABLEHDRS hem sınır dosyalarını yeniden derleme gerek olası değil listelediğiniz NMAKE makrolardır. Bu dosyalar komut dizesi tarafından derlenen

`CL /c /W3 /Yc$(BOUNDRY) applib.cpp myapp.cpp`

önceden derlenmiş üst bilgi dosyası (STABLE.pch) mevcut değilse veya dosyalarda değişiklik yapmadan yalnızca iki makrolarındaki listelenir. Her iki durumda da, önceden derlenmiş üst bilgi dosyası yalnızca STABLEHDRS makro içinde listelenen dosyaların koddan içerir. SINIR makroda önceden derlenmiş istediğiniz dosyanın son listeleyin.

Bu makrolar liste dosyaları, üstbilgi dosyaları veya C veya C++ kaynak dosyaları olabilir. (Tek bir PCH dosyası hem C hem de C++ modülleri ile kullanılamaz.) Kullanabileceğiniz Not **hdrstop** ön derleme sınır dosyası içinde belirli bir noktada durdurmak için makrosu. Bkz: [hdrstop](../../preprocessor/hdrstop.md) daha fazla bilgi için.

Diyagramı devam, APPLIB.obj son uygulamanızda kullanılan destek kodunu temsil eder. APPLIB.cpp oluşturulur, dosyaları UNSTABLEHDRS makroda listelenen ve önceden derlenmiş üst bilgi koddan önceden derlenmiş.

MYAPP.obj son uygulamanızı temsil eder. MYAPP.cpp oluşturulur, dosyaları UNSTABLEHDRS makroda listelenen ve önceden derlenmiş üst bilgi koddan önceden derlenmiş.

Son olarak, yürütülebilir dosya (UYGULAMAM. EXE) OBJS makrosu (APPLIB.obj ve MYAPP.obj) içinde listelenen dosyaların bağlayarak oluşturulur.

<a name="sample-makefile-for-pch"></a>

## <a name="sample-makefile-for-pch"></a>PCH için Örnek Derleme Görevleri Dosyası

Aşağıdaki görevleri makrolarını kullanır ve bir! EĞER! BAŞKA! Projenize, uyarlama kolaylaştıran denetim akışı komutu yapısı ENDIF.

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

"Yapısı, bir derleme görevleri dosyası olduğunu kullanan bir önceden derlenmiş üstbilgi dosyası" çizimde gösterilen STABLEHDRS, sınır ve UNSTABLEHDRS makroları yanı sıra [derleme sürecindeki PCH dosyaları](#pch-files-in-the-build-process), bu derleme görevleri dosyası CLFLAGS makro ve bir LINKFLAGS sağlar. Makro. Bu makrolar, derleyici ve hata ayıklama veya son sürümü uygulamanın yürütülebilir dosyanın derleme olup olmadığını geçerli bağlayıcı seçenekleri listelemede kullanmanız gerekir. De mevcuttur LIBS makrosu listesinde burada kitaplıklarını projenize gerektirir.

Derleme görevleri dosyası da kullanır. EĞER! BAŞKA! NMAKE komut satırında bir hata ayıklama sembolünü tanımlayın olup olmadığını algılamak için ENDIF:

```NMAKE
NMAKE DEBUG=[1|0]
```

Bu özellik, aynı derleme görevleri dosyası geliştirme sırasında kullanmanızı ve programınızı son sürümleri için mümkün kılar — hata ayıklama kullanmak = 0 son sürümleri. Aşağıdaki komut satırlarını eşdeğerdir:

```NMAKE
NMAKE
NMAKE DEBUG=0
```

Derleme görevleri dosyaları hakkında daha fazla bilgi için bkz. [NMAKE başvurusu](../../build/nmake-reference.md). Ayrıca bkz: [derleyici seçenekleri](../../build/reference/compiler-options.md) ve [bağlayıcı seçenekleri](../../build/reference/linker-options.md).

<a name="example-code-for-pch"></a>

## <a name="example-code-for-pch"></a>PCH için Örnek Kod

Aşağıdaki kaynak dosyaları açıklanan derleme görevleri dosyası kullanılan [derleme sürecindeki PCH dosyaları](#pch-files-in-the-build-process) ve [PCH için örnek derleme görevleri dosyası](#sample-makefile-for-pch). Açıklamaları önemli bilgileri içerdiğini unutmayın.

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

[C/C++ Derleme Başvurusu](../../build/reference/c-cpp-building-reference.md)<br/>
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)