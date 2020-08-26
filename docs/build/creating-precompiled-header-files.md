---
title: Önceden Derlenmiş Başlık Dosyaları
ms.date: 10/24/2019
helpviewer_keywords:
- precompiled header files, creating
- PCH files, creating
- cl.exe compiler, precompiling code
- .pch files, creating
ms.assetid: e2cdb404-a517-4189-9771-c869c660cb1b
ms.openlocfilehash: c68de0ee8e6376731254adf965fb9a81f10f2861
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838860"
---
# <a name="precompiled-header-files"></a>Önceden Derlenmiş Başlık Dosyaları

Visual Studio 'da yeni bir proje oluşturduğunuzda, projeye *pch. h* adlı *önceden derlenmiş bir üstbilgi dosyası* eklenir. (Visual Studio 2017 ve önceki sürümlerde dosya *stbafx. h*olarak adlandırılmıştı.) Dosyanın amacı, yapı sürecini hızlandırmaya yönelik olur. Tüm kararlı üstbilgi dosyaları, örneğin gibi standart kitaplık üstbilgileri dahil edilmelidir `<vector>` . Ön derlenmiş üstbilgi yalnızca, veya içerdiği herhangi bir dosya değiştirildiğinde derlenir. Yalnızca proje kaynak kodunuzda değişiklik yaparsanız, derleme ön derlenmiş üst bilgi için derlemeyi atlar.

Önceden derlenmiş üst bilgiler için derleyici seçenekleri [/y](reference/y-precompiled-headers.md). Proje özelliği sayfalarında, Seçenekler, **önceden derlenmiş üst bilgiler > > C/C++ yapılandırma özellikleri**altında bulunur. Önceden derlenmiş üst bilgileri kullanmayı seçebilirsiniz ve çıkış dosyasının adını ve yolunu belirtebilirsiniz.

## <a name="custom-precompiled-code"></a>Özel önceden derlenmiş kod

Oluşturmak için önemli zaman alan büyük projeler için özel önceden derlenmiş dosyalar oluşturmayı düşünmek isteyebilirsiniz. Microsoft C ve C++ derleyicileri, satır içi kod dahil olmak üzere herhangi bir C veya C++ kodunu önceden derlemeye yönelik seçenekler sağlar. Bu performans özelliğini kullanarak kodun kararlı bir gövdesini derleyebilir, kodun derlenmiş durumunu bir dosyada saklayabilir ve sonraki derlemeler sırasında, önceden derlenmiş kodu, hala geliştirme aşamasında olan kodla birleştirebilirsiniz. Kararlı kodun yeniden derlenmesi gerekmediğinden, sonraki her derleme daha hızlıdır.

## <a name="when-to-precompile-source-code"></a>Kaynak Kodun Ne Zaman Önceden Derleneceği

Önceden derlenmiş kod, derleme süresini azaltmak için geliştirme sürecinde yararlıdır, özellikle de:

- Her zaman seyrek olarak değişen büyük bir kod gövdesi kullanırsınız.

- Programınız, hepsi standart bir içerme dosyaları kümesi ve aynı derleme seçenekleri kullanan birden çok modülle oluşur. Bu durumda, tüm içerme dosyaları önceden derlenmiş bir üst bilgide önceden derlenmiş olabilir.

İlk derleme — önceden derlenmiş üst bilgi (PCH) dosyasını oluşturan bir, sonraki derlemeden biraz daha uzun sürer. Sonraki derlemeler önceden derlenmiş kodu ekleyerek daha hızlı devam edebilir.

Hem C hem de C++ programlarını önceden derleyebilirsiniz. C++ programlamada, sınıf arabirim bilgilerini üst bilgi dosyalarına ayırmak yaygın bir uygulamadır. Bu üstbilgi dosyaları daha sonra sınıfını kullanan programlara dahil edilebilir. Bu üst bilgileri önceden derleyerek, bir programın derlenmesi için geçen süreyi azaltabilirsiniz.

> [!NOTE]
> Kaynak dosya başına yalnızca bir ön derlenmiş üstbilgi (. pch) dosyası kullanabilseniz de bir projede birden fazla. pch dosyası kullanabilirsiniz.

## <a name="two-choices-for-precompiling-code"></a>Kodu Önceden Derlemek için İki Seçenek

Herhangi bir C veya C++ kodunu önceden derleyebilirsiniz; yalnızca üst bilgi dosyalarını önceden derlemek sınırlı değildir.

Ön derleme için planlama gereklidir, ancak basit üstbilgi dosyaları dışında kaynak kodu önceden derlerseniz önemli ölçüde daha hızlı derlemeler sunar.

Kaynak dosyalarınızın ortak başlık dosyaları kümelerini kullandığını ancak bunları aynı sırada içermediğini veya ön derlemenize kaynak kodu eklemek istediğinizde kodu önceden derleyin.

Önceden derlenmiş üst bilgi seçenekleri [/Rivc 'dir (ön derlenmiş üstbilgi dosyası oluştur)](reference/yc-create-precompiled-header-file.md) ve [/yu (önceden derlenmiş üst bilgi dosyası kullan)](reference/yu-use-precompiled-header-file.md). Ön derlenmiş üst bilgi oluşturmak için **/Yıc** kullanın. İsteğe bağlı [hdrstop](../preprocessor/hdrstop.md) pragma ile kullanıldığında, **/i c** hem üstbilgi dosyalarını hem de kaynak kodu önceden derlemenize olanak tanır. Var olan derlemede var olan bir ön derlenmiş üstbilgiyi kullanmak için **/yu** seçin. Ayrıca, ön derlenmiş üst bilgi için alternatif bir ad sağlamak üzere **/N** ve **/yu** seçenekleriyle **/FP** 'yi de kullanabilirsiniz.

**/Yu** ve **/i c** için derleyici seçeneği başvuru konuları geliştirme ortamında bu işlevselliğe nasıl erişileceni tartışır.

## <a name="precompiled-header-consistency-rules"></a>Önceden Derlenmiş Üst Bilgi Tutarlığı Kuralları

PCH dosyaları, makine ortamı ve programla ilgili bellek adresi bilgileri hakkında bilgi içerdiğinden, yalnızca oluşturulduğu makinede bir PCH dosyası kullanmanız gerekir.

## <a name="consistency-rules-for-per-file-use-of-precompiled-headers"></a>Önceden Derlenmiş Başlıkların Dosya Başına Kullanım için Tutarlık Kuralları

[/Yu](reference/yu-use-precompiled-header-file.md) derleyici SEÇENEĞI kullanılacak pch dosyasını belirtmenize olanak tanır.

Bir PCH dosyası kullandığınızda, derleyici aynı derleme ortamını (bir tane (örneğin, tutarlı derleyici seçenekleri, pragmalar vb.), aksi belirtilmedikçe, PCH dosyasını oluştururken geçerli olan olduğunu varsayar. Derleyici bir tutarsızlık algılarsa, bir uyarı verir ve mümkün olduğunda tutarsızlığı tanımlar. Bu tür uyarılar, PCH dosyası ile ilgili bir sorun olduğunu göstermez; yalnızca olası çakışmaların sizi uyarır. PCH dosyaları için tutarlılık gereksinimleri aşağıdaki bölümlerde açıklanmıştır.

### <a name="compiler-option-consistency"></a>Derleyici seçenek tutarlılığı

Aşağıdaki derleyici seçenekleri, bir PCH dosyası kullanılırken bir tutarsızlık uyarısı tetikleyebilir:

- Ön Işlemci (/D) seçeneği kullanılarak oluşturulan makrolar, PCH dosyasını ve geçerli derlemeyi oluşturan derleme ile aynı olmalıdır. Tanımlı sabitlerin durumu işaretli değil, ancak bu değişiklik için öngörülemeyen sonuçlar oluşabilir.

- PCH dosyaları/E ve/EP seçenekleriyle çalışmaz.

- PCH dosyası, PCH dosyasını kullanan sonraki derlemelerin bu seçenekleri kullanabilmesi için, tarayıcı bilgisi oluştur (/FR) seçeneği veya yerel değişkenleri hariç tut (/fr) seçeneğini kullanarak oluşturulmalıdır.

### <a name="c-70-compatible-z7"></a>C 7,0 uyumlu (/Z7)

PCH dosyası oluşturulduğunda bu seçenek etkinse, PCH dosyasını kullanan sonraki derlemeler hata ayıklama bilgilerini kullanabilir.

PCH dosyası oluşturulduğunda C 7,0 uyumlu (/Z7) seçeneği etkin değilse, PCH dosyası ve/Z7 kullanan sonraki derlemeler bir uyarı tetikler. Hata ayıklama bilgileri geçerli. obj dosyasına yerleştirilir ve PCH dosyasında tanımlanan yerel semboller hata ayıklayıcı için kullanılamaz.

### <a name="include-path-consistency"></a>Yol tutarlılığını dahil et

PCH dosyası, oluşturulduğu sırada geçerli olan ekleme yolu hakkında bilgi içermez. Bir PCH dosyası kullandığınızda, derleyici her zaman geçerli derlemede belirtilen ekleme yolunu kullanır.

### <a name="source-file-consistency"></a>Kaynak dosya tutarlılığı

Ön derlenmiş üstbilgi dosyası kullan (/Yu) seçeneğini belirttiğinizde, derleyici ön derlenmiş kaynak kodunda görüntülenen tüm önişlemci yönergelerini (pragmalar dahil) yoksayar. Bu tür Önişlemci yönergeleri tarafından belirtilen derleme, ön derlenmiş üstbilgi dosyası oluştur (/Yıc) seçeneği için kullanılan derleme ile aynı olmalıdır.

### <a name="pragma-consistency"></a>Pragma tutarlılığı

Bir PCH dosyasının oluşturulması sırasında işlenen pragmalar genellikle PCH dosyasının daha sonra kullanıldığı dosyayı etkiler. `comment`Ve `message` pragmaları, derlemenin kalanını etkilemez.

Bu pragmalar yalnızca PCH dosyası içindeki kodu etkiler; daha sonra PCH dosyasını kullanan kodu etkilemez:

:::row:::
   :::column span="":::
      `comment`\
      `linesize`
   :::column-end:::
   :::column span="":::
      `message`\
      `page`
   :::column-end:::
   :::column span="":::
      `pagesize`\
      `skip`
   :::column-end:::
   :::column span="":::
      `subtitle`\
      `title`
   :::column-end:::
:::row-end:::

Bu pragmalar, önceden derlenmiş üstbilginin bir parçası olarak tutulur ve önceden derlenmiş üst bilgiyi kullanan bir derlemenin kalanını etkiler:

:::row:::
   :::column span="":::
      `alloc_text`\
      `auto_inline`\
      `check_stack`\
      `code_seg`\
      `data_seg`
   :::column-end:::
   :::column span="":::
      `function`\
      `include_alias`\
      `init_seg`\
      `inline_depth`
   :::column-end:::
   :::column span="":::
      `inline_recursion`\
      `intrinsic`\
      `optimize`\
      `pack`
   :::column-end:::
   :::column span="":::
      `pointers_to_members`\
      `setlocale`\
      `vtordisp`\
      `warning`
   :::column-end:::
:::row-end:::

## <a name="consistency-rules-for-yc-and-yu"></a>/Yc ve /Yu İçin Tutarlık Kuralları

/Yıc veya/yu kullanılarak oluşturulan önceden derlenmiş bir üst bilgi kullandığınızda, derleyici geçerli derleme ortamını PCH dosyasını oluştururken var olan bir ile karşılaştırır. Geçerli derleme için bir önceki uygulamayla (tutarlı derleyici seçenekleri, pragmalar, vb. kullanarak) tutarlı bir ortam belirttiğinizden emin olun. Derleyici bir tutarsızlık algılarsa, bir uyarı verir ve mümkün olduğunda tutarsızlığı tanımlar. Bu tür uyarılar, PCH dosyası ile ilgili bir sorun olduğunu göstermez; yalnızca olası çakışmaların sizi uyarır. Aşağıdaki bölümlerde önceden derlenmiş üst bilgiler için tutarlılık gereksinimleri açıklanmaktadır.

### <a name="compiler-option-consistency"></a>Derleyici seçenek tutarlılığı

Bu tabloda, ön derlenmiş üst bilgi kullanılırken tutarsızlık uyarısı tetikleyebilen derleyici seçenekleri listelenmektedir:

|Seçenek|Name|Kural|
|------------|----------|----------|
|Belirtilmediyse|Sabitleri ve makroları tanımlama|Ön derlenmiş üstbilgiyi ve geçerli derlemeyi oluşturan derleme arasında aynı olmalıdır. Tanımlı sabitlerin durumu işaretli değil, ancak dosyalarınız değiştirilen sabitlerin değerlerine bağlıysa öngörülemeyen sonuçlar ortaya çıkabilir.|
|/E veya/EP|Önişlemci çıkışını standart çıktıya Kopyala|Önceden derlenmiş üstbilgiler/E veya/EP seçeneğiyle çalışmaz.|
|/Fr veya/FR|Microsoft kaynak tarayıcısı bilgilerini oluştur|/Fr ve/FR seçeneklerinin/yu seçeneğiyle geçerli olması için, önceden derlenmiş üst bilgi oluşturulduğunda da etkin olmaları gerekir. Ön derlenmiş üstbilgiyi kullanan sonraki derlemeler de kaynak tarayıcı bilgileri oluşturur. Tarayıcı bilgileri tek bir. sbr dosyasına yerleştirilir ve diğer dosyalar tarafından CodeView bilgileriyle aynı şekilde başvurulur. Kaynak tarayıcı bilgilerinin yerleşimini geçersiz kılamazsınız.|
|/GA,/GD,/GE,/GW veya/GW|Windows protokol seçenekleri|Ön derlenmiş üstbilgiyi ve geçerli derlemeyi oluşturan derleme arasında aynı olmalıdır. Bu seçenekler farklıysa bir uyarı mesajı oluşur.|
|/Zi|Tüm hata ayıklama bilgilerini oluştur|Ön derlenmiş üstbilgi oluşturulduğunda bu seçenek etkinse, ön derlemeyi kullanan sonraki derlemeler bu hata ayıklama bilgilerini kullanabilir. Ön derlenmiş üstbilgi oluşturulduğunda/Zi etkin değilse, ön derleme ve/Zi seçeneğini kullanan sonraki derlemeler bir uyarı tetikler. Hata ayıklama bilgileri geçerli nesne dosyasına yerleştirilir ve önceden derlenmiş üst bilgide tanımlanan yerel semboller hata ayıklayıcı için kullanılamaz.|

> [!NOTE]
> Ön derlenmiş üstbilgi özelliği yalnızca C ve C++ kaynak dosyalarında kullanılmak üzere tasarlanmıştır.

## <a name="using-precompiled-headers-in-a-project"></a>Projede Önceden Derlenmiş Başlıkları Kullanma

Önceki bölümlerde önceden derlenmiş üstbilgilere genel bir bakış sunulmaktadır:/Yc ve/Yu,/fp seçeneği ve [hdrstop](../preprocessor/hdrstop.md) pragması. Bu bölümde, bir projede el ile önceden derlenmiş üst bilgi seçeneklerini kullanma yöntemi açıklanmaktadır; örnek derleme görevleri dosyası ve yönettiği kod ile biter.

Bir projede el ile önceden derlenmiş üst bilgi seçeneklerini kullanma ile ilgili başka bir yaklaşım için, Visual Studio 'nun varsayılan kurulumu sırasında oluşturulan MFC\SRC dizininde bulunan derleme görevleri dosyalarını listesinden birini inceleyin. Bu derleme görevleri dosyalarını, bu bölümde sunulan birine benzer bir yaklaşım getirir, ancak Microsoft program bakım yardımcı programı (NMAKE) makrolarını daha fazla kullanır ve derleme sürecinde daha fazla denetim sağlar.

## <a name="pch-files-in-the-build-process"></a>Derleme Sürecindeki PCH Dosyaları

Yazılım projesinin kod tabanı genellikle birden çok C veya C++ kaynak dosyasında, nesne dosyalarında, kitaplıklarda ve üstbilgi dosyalarında bulunur. Genellikle, bir derleme görevleri dosyası bu öğelerin birleşimini yürütülebilir bir dosyaya koordine eder. Aşağıdaki şekilde, önceden derlenmiş bir üstbilgi dosyası kullanan derleme görevleri dosyası yapısı gösterilmektedir. Bu diyagramdaki NMAKE makro adları ve dosya adları, [PCH Için örnek derleme görevleri](#sample-makefile-for-pch) dosyası ve [PCH için örnek kod](#example-code-for-pch)içinde bulunan örnek kodda olanlarla tutarlıdır.

Şekil, yapı sürecinin akışını göstermek için üç diagrammatik cihaz kullanır. Adlandırılmış dikdörtgenler her bir dosyayı veya makroyu temsil eder; Üç makro bir veya daha fazla dosyayı temsil eder. Gölgeli alanlarda her derleme veya bağlantı eylemi temsil eder. Oklar, derleme veya bağlama işlemi sırasında hangi dosyaların ve makroların birleştirildiğini gösterir.

![Ön derlenmiş üstbilgi dosyası kullanan derleme görevleri dosyası yapısı](media/vc30ow1.gif "Ön derlenmiş üstbilgi dosyası kullanan derleme görevleri dosyası yapısı") <br/>
Ön derlenmiş üstbilgi dosyası kullanan derleme görevleri dosyası yapısı

Diyagramın en üstünden başlayarak, her iki STABLEHDRS ve BOUNDNMAKE, dosyaları yeniden derlemek zorunda kalmaz. Bu dosyalar komut dizesi tarafından derlenir

`CL /c /W3 /Yc$(BOUNDRY) applib.cpp myapp.cpp`

yalnızca önceden derlenmiş üstbilgi dosyası (STABLE. pch) yoksa veya iki makroda listelenen dosyalarda değişiklik yaparsanız. Her iki durumda da, ön derlenmiş üstbilgi dosyası yalnızca STABLEHDRS makrosunda listelenen dosyalardan kod içerir. Daha önceden derlenmiş olmasını istediğiniz son dosyayı BOUNDRY makrosunda listeleyin.

Bu makrolarda listeettiğiniz dosyalar başlık dosyaları ya da C veya C++ kaynak dosyaları olabilir. (Tek bir PCH dosyası hem C hem de C++ modülleriyle kullanılamaz.) BOUNDRY dosyasının içindeki bir noktada ön derlemeyi durdurmak için **hdrstop** makrosunu kullanabileceğinizi unutmayın. Daha fazla bilgi için bkz. [hdrstop](../preprocessor/hdrstop.md) .

Diyagramda devam etme, APPLIB. obj son uygulamanızda kullanılan destek kodunu temsil eder. APPLIB. cpp, UNSTABLEHDRS makrosunda listelenen dosyalar ve önceden derlenmiş üstbilginin ön derlenmiş kodu oluşturulur.

MYAPP. obj son uygulamanızı temsil eder. MYAPP. cpp, UNSTABLEHDRS makrosunda listelenen dosyalar ve önceden derlenmiş üstbilginin ön derlenmiş kodu oluşturulur.

Son olarak, yürütülebilir dosya (MYAPP.EXE), OBJS makrosunda listelenen dosyalar (APPLIB. obj ve MYAPP. obj) ile ilişkilendirilerek oluşturulur.

## <a name="sample-makefile-for-pch"></a>PCH için Örnek Derleme Görevleri Dosyası

Aşağıdaki derleme görevleri dosyası makroları ve bir kullanır! Ise,! ELSE,! , Projenize yapısını basitleştirmek için, Denetim akış komut yapısı.

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
LINKFLAGS = /nologo
!IF "$(DEBUG)" == "1"
CLFLAGS   = /D_DEBUG $(CLFLAGS) /Od /Zi
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

[Derleme Işlemindeki PCH dosyalarında](#pch-files-in-the-build-process)"ön derlenmiş üstbilgi dosyası kullanan derleme görevleri dosyası yapısı" ŞEKLINDE GÖSTERILEN stablehdrs, BOUNDRY ve UNSTABLEHDRS makrolarından bağımsız olarak, bu derleme görevleri dosyası BIR clflags MAKROSU ve linkflags makrosu sağlar. Uygulamanın yürütülebilir dosyasının bir hata ayıklama veya son sürümünü oluşturup uygulamadığınızda uygulanan derleyici ve bağlayıcı seçeneklerini listelemek için bu makroları kullanmanız gerekir. Ayrıca, projenizin gerektirdiği kitaplıkları listeleyinizdeki bir LIBS makrosu de vardır.

Derleme görevleri dosyası da kullanır! Ise,! ELSE,! NMAKE komut satırında bir hata ayıklama sembolü tanımlayıp tanımlamacağınızı saptamak için ENDIF:

```NMAKE
NMAKE DEBUG=[1|0]
```

Bu özellik, geliştirme sırasında ve programınızın son sürümlerinde aynı derleme görevleri dosyasını kullanmanızı sağlar. son sürümler için DEBUG = 0 kullanın. Aşağıdaki komut satırları eşdeğerdir:

```NMAKE
NMAKE
NMAKE DEBUG=0
```

Makefiles hakkında daha fazla bilgi için bkz. [NMAKE Başvurusu](reference/nmake-reference.md). Ayrıca bkz. [MSVC derleyici seçenekleri](reference/compiler-options.md) ve [MSVC bağlayıcı seçenekleri](reference/linker-options.md).

## <a name="example-code-for-pch"></a>PCH için Örnek Kod

Aşağıdaki kaynak dosyalar [derleme Işlemindeki PCH dosyalarında](#pch-files-in-the-build-process) açıklanan derleme görevleri dosyası ve [PCH için örnek derleme](#sample-makefile-for-pch)görevleri dosyasında kullanılır. Yorumların önemli bilgileri içerdiğini unutmayın.

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
#include<iostream>
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
using namespace std;
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

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Oluşturma Başvurusu](reference/c-cpp-building-reference.md)<br/>
[MSVC derleyici seçenekleri](reference/compiler-options.md)
