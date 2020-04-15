---
title: Önceden Derlenmiş Başlık Dosyaları
ms.date: 10/24/2019
helpviewer_keywords:
- precompiled header files, creating
- PCH files, creating
- cl.exe compiler, precompiling code
- .pch files, creating
ms.assetid: e2cdb404-a517-4189-9771-c869c660cb1b
ms.openlocfilehash: 158301ec3caacced1663892071b17ef2b8f8e741
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328667"
---
# <a name="precompiled-header-files"></a>Önceden Derlenmiş Başlık Dosyaları

Visual Studio'da yeni bir proje oluşturduğunuzda, *projeye pch.h* adlı önceden derlenmiş bir *üstbilgi dosyası* eklenir. (Visual Studio 2017 ve daha önce, dosya *stdafx.h*çağrıldı .) Dosyanın amacı, yapı işlemini hızlandırmaktır. Herhangi bir kararlı üstbilgi dosyaları, örneğin `<vector>`Standart Kitaplık üstbilgi gibi, burada yer almalıdır. Önceden derlenen üstbilgi yalnızca derlendiğinde veya içerdiği dosyalar değiştirildiğinde derlenir. Yalnızca proje kaynak kodunuzda değişiklik yaparsanız, yapı önceden derlenmiş üstbilgi için derlemeyi atlar.

Önceden derlenmiş üstbilgi için derleyici seçenekleri [/Y'dir.](reference/y-precompiled-headers.md) Proje özelliği sayfalarında seçenekler Yapılandırma Özellikleri **> C/C++ > Önceden Derlenmiş Üstbilgi**altında yer alır. Önceden derlenmiş üstbilgi kullanmamayı seçebilir ve üstbilgi dosyası adını ve çıktı dosyasının adını ve yolunu belirtebilirsiniz.

## <a name="custom-precompiled-code"></a>Özel önceden derlenmiş kod

Oluşturulması önemli zaman alan büyük projeler için, özel önceden derlenmiş dosyalar oluşturmayı düşünebilirsiniz. Microsoft C ve C++ derleyicileri, satır ara kodu da dahil olmak üzere herhangi bir C veya C++ kodunu önceden derleme kinleri için seçenekler sunar. Bu performans özelliğini kullanarak, kararlı bir kod gövdesi derleyebilir, kodun derlenmiş durumunu bir dosyada depolayabilir ve sonraki derlemeler sırasında önceden derlenmiş kodu hala geliştirilmekte olan kodla birleştirebilirsiniz. Kararlı kodun yeniden derlenmesine gerek olmadığından, sonraki her derleme daha hızlıdır.

## <a name="when-to-precompile-source-code"></a>Kaynak Kodun Ne Zaman Önceden Derleneceği

Önceden derlenmiş kod, özellikle aşağıdakilerde derleme süresini kısaltmak için geliştirme döngüsü sırasında yararlıdır:

- Her zaman seyrek olarak değişen büyük bir kod gövdesi kullanırsınız.

- Programınız, standart bir dosya kümesi ve aynı derleme seçeneklerini kullanan birden çok modülden oluşur. Bu durumda, tüm dahil dosyaları önceden derlenmiş bir üstbilgi içine önceden derlenebilir.

İlk derleme - önceden derlenmiş üstbilgi (PCH) dosyasını oluşturan dosya - sonraki derlemelerden biraz daha uzun sürer. Sonraki derlemeler önceden derlenmiş kodu ekleyerek daha hızlı bir şekilde devam edebilir.

Hem C hem de C++ programlarını önceden hazırlayabilirsiniz. C++ programlamada, sınıf arabirimi bilgilerini üstbilgi dosyalarına ayırmak yaygın bir uygulamadır. Bu üstbilgi dosyaları daha sonra sınıfı kullanan programlara eklenebilir. Bu üstleri önceden derleyerek, bir programın derlemesüresini azaltabilirsiniz.

> [!NOTE]
> Kaynak dosyası başına yalnızca bir önceden derlenmiş üstbilgi (.pch) dosya kullanabiliyor olsa da, projede birden çok .pch dosyası kullanabilirsiniz.

## <a name="two-choices-for-precompiling-code"></a>Kodu Önceden Derlemek için İki Seçenek

Herhangi bir C veya C++ kodunu önceden derleyebilirsiniz; yalnızca üstbilgi dosyalarını önceden derlemek ile sınırlı değildir.

Önceden derleme planlama gerektirir, ancak basit üstbilgi dosyaları dışında kaynak kodu önceden derlerseniz önemli ölçüde daha hızlı derlemeler sunar.

Kaynak dosyalarınızın ortak üstbilgi dosyaları kullandığını, ancak bunları aynı sıraya dahil etmediğini veya kaynak kodunu önceden derlemenize eklemek istediğinizde kodu önceden derleyin.

Önceden derlenmiş üstbilgi seçenekleri [/Yc (Önceden Derlenmiş Üstbilgi Dosyası Oluşturma)](reference/yc-create-precompiled-header-file.md) ve [/Yu (Önceden Derlenmiş Üstbilgi Dosyasını Kullan)](reference/yu-use-precompiled-header-file.md)vardır. Önceden derlenmiş bir üstbilgi oluşturmak için **/Yc'yi** kullanın. İsteğe bağlı [hdrstop](../preprocessor/hdrstop.md) pragma ile kullanıldığında, **/Yc** hem üstbilgi dosyalarını hem de kaynak kodunu önceden derlemenizi sağlar. Varolan derlemede önceden derlenmiş bir üstbilgi kullanmak için **/Yu'yu'yu** seçin. Önceden derlenen üstbilgi için alternatif bir ad sağlamak için **/Yc** ve **/Yu** seçenekleriyle **/Fp** seçeneklerini de kullanabilirsiniz.

**/Yu** ve **/Yc** için derleyici seçeneği başvuru konuları, geliştirme ortamında bu işlevselliktedirnasıl erişilenleri tartışır.

## <a name="precompiled-header-consistency-rules"></a>Önceden Derlenmiş Üst Bilgi Tutarlığı Kuralları

PCH dosyaları makine ortamı nın yanı sıra program la ilgili bellek adresi bilgileri içerdiğinden, yalnızca oluşturulduğu makinede bir PCH dosyası kullanmanız gerekir.

## <a name="consistency-rules-for-per-file-use-of-precompiled-headers"></a>Önceden Derlenmiş Başlıkların Dosya Başına Kullanım için Tutarlık Kuralları

[/Yu](reference/yu-use-precompiled-header-file.md) derleyici seçeneği, hangi PCH dosyasının kullanılacağını belirtmenizi sağlar.

Bir PCH dosyası kullandığınızda, derleyici, aksini belirtmediğiniz sürece PCH dosyasını oluşturduğunuzda geçerli olan tutarlı derleyici seçenekleri, pragmas ve benzeri bir derleme ortamını varsayar. Derleyici bir tutarsızlık algılarsa, bir uyarı yayınlar ve tutarsızlığı mümkün olduğunca tanımlar. Bu tür uyarılar mutlaka PCH dosyası ile ilgili bir sorun göstermez; onlar sadece olası çatışmalar sizi uyarır. PCH dosyaları için tutarlılık gereksinimleri aşağıdaki bölümlerde açıklanmıştır.

### <a name="compiler-option-consistency"></a>Derleyici Seçeneği Tutarlılığı

Aşağıdaki derleyici seçenekleri, Bir PCH dosyası kullanırken bir tutarsızlık uyarısı tetikleyebilir:

- Önişlemci (/D) seçeneği kullanılarak oluşturulan makrolar, PCH dosyasını oluşturan derleme ile geçerli derleme arasında aynı olmalıdır. Tanımlanan sabitlerin durumu denetlenmez, ancak bunlar değişirse öngörülemeyen sonuçlar oluşabilir.

- PCH dosyaları /E ve /EP seçenekleriyle çalışmaz.

- PCH dosyasını kullanan sonraki derlemeler bu seçenekleri kullanamadan önce, Gözat Bilgileri Oluştur (/FR) seçeneği veya Yerel Değişkenleri Hariç Tut (/Fr) seçeneği kullanılarak PCH dosyaları oluşturulmalıdır.

### <a name="c-70-compatible-z7"></a>C 7.0-Uyumlu (/Z7)

PCH dosyası oluşturulduğunda bu seçenek etkinse, PCH dosyasını kullanan sonraki derlemeler hata ayıklama bilgilerini kullanabilir.

PCH dosyası oluşturulduğunda C 7.0-Uyumlu (/Z7) seçeneği etkin değilse, PCH dosyasını ve /Z7 dosyasını kullanan sonraki derlemeler bir uyarı tetikler. Hata ayıklama bilgileri geçerli .obj dosyasına yerleştirilir ve PCH dosyasında tanımlanan yerel simgeler hata ayıklama için kullanılamaz.

### <a name="include-path-consistency"></a>Yol Tutarlılığını Ekle

Bir PCH dosyası oluşturulduğunda etkin olan dahil yolu hakkında bilgi içermez. Bir PCH dosyası kullandığınızda, derleyici her zaman geçerli derlemede belirtilen dahil yolunu kullanır.

### <a name="source-file-consistency"></a>Kaynak Dosya Tutarlılığı

Önceden Derlenmiş Üstbilgi Dosyasını (/Yu) Kullan seçeneğini belirttiğiniz zaman, derleyici önceden derlenecek kaynak kodunda görünen tüm önişlemci yönergelerini (pragmalar dahil) yok sayar. Bu tür önişlemci yönergeleri tarafından belirtilen derleme, Önceden Derlenmiş Üstbilgi Dosyası (/Yc) Oluşturma seçeneği için kullanılan derlemeyle aynı olmalıdır.

### <a name="pragma-consistency"></a>Pragma Tutarlılık

Bir PCH dosyasının oluşturulması sırasında işlenen Pragmalar genellikle PCH dosyasının daha sonra kullanıldığı dosyayı etkiler. Ve `comment` `message` pragmalar derlemenin geri kalanını etkilemez.

Bu pragmalar yalnızca PCH dosyasındaki kodu etkiler; daha sonra PCH dosyasını kullanan kodu etkilemez:

||||
|-|-|-|
|`comment`|`page`|`subtitle`|
|`linesize`|`pagesize`|`title`|
|`message`|`skip`||

Bu pragmalar önceden derlenmiş bir üstbilginin parçası olarak korunur ve önceden derlenmiş üstbilgi kullanan bir derlemenin geri kalanını etkiler:

||||
|-|-|-|
|`alloc_text`|`include_alias`|`pack`|
|`auto_inline`|`init_seg`|`pointers_to_members`|
|`check_stack`|`inline_depth`|`setlocale`|
|`code_seg`|`inline_recursion`|`vtordisp`|
|`data_seg`|`intrinsic`|`warning`|
|`function`|`optimize`||

## <a name="consistency-rules-for-yc-and-yu"></a>/Yc ve /Yu İçin Tutarlık Kuralları

/Yc veya /Yu kullanılarak oluşturulan önceden derlenmiş bir üstbilgi kullandığınızda, derleyici geçerli derleme ortamını PCH dosyasını oluşturduğunuzda var olanla karşılaştırır. Geçerli derleme için öncekiyle tutarlı bir ortam (tutarlı derleyici seçenekleri, pragmas vb.) ile tutarlı bir ortam belirttiğinden emin olun. Derleyici bir tutarsızlık algılarsa, bir uyarı yayınlar ve tutarsızlığı mümkün olduğunca tanımlar. Bu tür uyarılar mutlaka PCH dosyası ile ilgili bir sorun göstermez; onlar sadece olası çatışmalar sizi uyarır. Aşağıdaki bölümlerde önceden derlenmiş üstbilgi için tutarlılık gereksinimleri açıklanır.

### <a name="compiler-option-consistency"></a>Derleyici Seçeneği Tutarlılığı

Bu tablo, önceden derlenmiş bir üstbilgi kullanırken tutarsızlık uyarısı tetikleyebilecek derleyici seçeneklerini listeler:

|Seçenek|Adı|Kural|
|------------|----------|----------|
|/d|Sabitleri ve makroları tanımlama|Önceden derlenmiş üstbilgi ve geçerli derleme oluşturulan derleme arasında aynı olmalıdır. Tanımlı sabitlerin durumu denetlenmez, ancak dosyalarınız değiştirilen sabitlerin değerlerine bağlıysa öngörülemeyen sonuçlar oluşabilir.|
|/E veya /EP|Önişlemci çıktısını standart çıktıya kopyalama|Önceden derlenmiş üstbilgi /E veya /EP seçeneğiyle çalışmaz.|
|/Fr veya /FR|Microsoft Kaynak Tarayıcı bilgilerini oluşturma|/Fr ve /FR seçeneklerinin /Yu seçeneğiyle geçerli olabilmesi için, önceden derlenmiş üstbilgi oluşturulduğunda da etkin olmaları gerekir. Önceden derlenmiş üstbilgiyi kullanan sonraki derlemeler de Kaynak Tarayıcı bilgileri oluşturur. Tarayıcı bilgileri tek bir .sbr dosyasına yerleştirilir ve diğer dosyalar tarafından CodeView bilgileriyle aynı şekilde başvurulur. Kaynak Tarayıcı bilgilerinin yerleşimini geçersiz kılamazsınız.|
|/GA, /GD, /GE, /Gw veya /GW|Windows protokolü seçenekleri|Önceden derlenmiş üstbilgi ve geçerli derleme oluşturulan derleme arasında aynı olmalıdır. Bu seçenekler farklıysa, bir uyarı iletisi sonuçları.|
|/zı|Tam hata ayıklama bilgileri oluşturma|Önceden derlenmiş üstbilgi oluşturulduğunda bu seçenek geçerliyse, ön derlemeyi kullanan sonraki derlemeler bu hata ayıklama bilgilerini kullanabilir. Önceden derlenen üstbilgi oluşturulduğunda /Zi etkin değilse, precompilation ve /Zi seçeneğini kullanan sonraki derlemeler bir uyarı tetikler. Hata ayıklama bilgileri geçerli nesne dosyasına yerleştirilir ve önceden derlenmiş üstbilgide tanımlanan yerel simgeler hata ayıklayıcı tarafından kullanılamaz.|

> [!NOTE]
> Önceden derlenmiş üstbilgi tesisi yalnızca C ve C++ kaynak dosyalarında kullanılmak üzere tasarlanmıştır.

## <a name="using-precompiled-headers-in-a-project"></a>Projede Önceden Derlenmiş Başlıkları Kullanma

Önceki bölümlerde önceden derlenmiş üstbilgiler genel bir bakış sunar: /Yc ve /Yu, /Fp seçeneği ve [hdrstop](../preprocessor/hdrstop.md) pragma. Bu bölümde, projede el ile derlenmiş üstbilgi seçeneklerini kullanma yöntemi açıklanmaktadır; bir örnek makefile ve yönettiği kod ile sona erer.

Bir projede el ile derlenmiş üstbilgi seçeneklerini kullanmaya başka bir yaklaşım için, Visual Studio'nun varsayılan kurulumu sırasında oluşturulan MFC\SRC dizininde bulunan makefiles'den birini inceleyin. Bu makefiles bu bölümde sunulan benzer bir yaklaşım almak, ancak Microsoft Program Bakım Yardımcı Programı (NMAKE) makroları daha fazla yararlanmak ve yapı süreci daha fazla denetim sunuyoruz.

## <a name="pch-files-in-the-build-process"></a>Derleme Sürecindeki PCH Dosyaları

Bir yazılım projesinin kod tabanı genellikle birden çok C veya C++ kaynak dosyasında, nesne dosyalarında, kitaplıklarda ve üstbilgi dosyalarında bulunur. Genellikle, bir makefile yürütülebilir bir dosya içine bu öğelerin birleşimini koordine eder. Aşağıdaki şekil, önceden derlenmiş bir üstbilgi dosyası kullanan bir makefileyapısını gösterir. NMAKE makro adları ve bu diyagramdaki dosya adları, [PCH için Örnek Makefile'da](#sample-makefile-for-pch) bulunan örnek koddakilerle ve [PCH için Örnek](#example-code-for-pch)Kod'dakilerle tutarlıdır.

Şekil, yapı işleminin akışını göstermek için üç diyagramatik aygıt kullanır. Adlandırılmış dikdörtgenler her dosyayı veya makroyu temsil eder; üç makro bir veya daha fazla dosyayı temsil eder. Gölgeli alanlar her derleme veya bağlantı eylemini temsil eder. Oklar derleme veya bağlama işlemi sırasında hangi dosyaların ve makroların birleştirildiğinden ilerler.

![Önceden derlenmiş üstbilgi dosyası kullanan bir makefilenin yapısı](media/vc30ow1.gif "Önceden derlenmiş üstbilgi dosyası kullanan bir makefilenin yapısı") <br/>
Önceden Derlenmiş Üstbilgi Dosyası Kullanan Bir İşlem Dosyasının Yapısı

Diyagramın en üstünden başlayarak, hem STABLEHDRS hem de BOUNDRY, yeniden derlemeye ihtiyaç dalamayan dosyaları listelediğiniz NMAKE makrolarıdır. Bu dosyalar komut dizesi tarafından derlenir

`CL /c /W3 /Yc$(BOUNDRY) applib.cpp myapp.cpp`

yalnızca önceden derlenmiş üstbilgi dosyası (STABLE.pch) yoksa veya iki makroda listelenen dosyalarda değişiklik yaparsanız. Her iki durumda da, önceden derlenmiş üstbilgi dosyası yalnızca STABLEHDRS makrosunda listelenen dosyalardan kod içerir. BOUNDRY makrosunda önceden derlenmiş olmasını istediğiniz son dosyayı listeleyin.

Bu makrolarda listelediğiniz dosyalar üstbilgi dosyaları veya C veya C++ kaynak dosyaları olabilir. (C ve C++ modülleri ile tek bir PCH dosyası kullanılamaz.) BOUNDRY dosyasının içinde bir noktada precompilation durdurmak için **hdrstop** makro kullanabilirsiniz unutmayın. Daha fazla bilgi için [hdrstop](../preprocessor/hdrstop.md) bakın.

Diyagramı aşağı doğru devam eden APPLIB.obj, son uygulamanızda kullanılan destek kodunu temsil eder. BU APPLIB.cpp, UNSTABLEHDRS makro listelenen dosyaları ve önceden derlenmiş üstbilgiden önceden derlenmiş kod oluşturulur.

MYAPP.obj son başvurunuzu temsil eder. MYAPP.cpp, UNSTABLEHDRS makrolistelenen dosyalar ve önceden derlenmiş üstbilgiden önceden derlenmiş kod oluşturulur.

Son olarak, çalıştırılabilir dosya (MYAPP). EXE) OBJS makro (APPLIB.obj ve MYAPP.obj) listelenen dosyaları bağlayarak oluşturulur.

## <a name="sample-makefile-for-pch"></a>PCH için Örnek Derleme Görevleri Dosyası

Aşağıdaki makefile makrolar ve bir kullanır ! EĞER, ! Başka! ENDIF denetim akışı komut yapısı projenize adaptasyonunu kolaylaştırmak için.

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

[Yapı İşleminde PCH Dosyalarında](#pch-files-in-the-build-process)"Önceden Derlenmiş Üstbilgi Dosyası Kullanan Bir Makyaj Dosyasının Yapısı" şeklinde gösterilen STABLEHDRS, BOUNDRY ve UNSTABLEHDRS makrolarının yanı sıra, bu makefile bir CLFLAGS makrosu ve LINKFLAGS makrosu sağlar. Hata ayıklama veya uygulamanın yürütülebilir dosyasının son sürümünü oluştursanız da geçerli olan derleyici ve bağlayıcı seçeneklerini listelemek için bu makroları kullanmanız gerekir. Ayrıca, projenizin gerektirdiği kitaplıkları listelediğiniz bir LIBS makrosu da vardır.

Makefile de kullanır! EĞER, ! Başka! NMAKE komut satırında bir HATA Ayıklama simgesi tanımlayıp tanımlamadığınızı algılamak için ENDIF:

```NMAKE
NMAKE DEBUG=[1|0]
```

Bu özellik, geliştirme sırasında ve programınızın son sürümleri için aynı makefileyi kullanmanızı mümkün kılar — son sürümler için DEBUG=0 kullanın. Aşağıdaki komut satırları eşdeğerdir:

```NMAKE
NMAKE
NMAKE DEBUG=0
```

Makefiles hakkında daha fazla bilgi için [NMAKE Başvurusu'na](reference/nmake-reference.md)bakın. Ayrıca bkz: [MSVC Derleyici Seçenekleri](reference/compiler-options.md) ve [MSVC Bağlantı Seçenekleri.](reference/linker-options.md)

## <a name="example-code-for-pch"></a>PCH için Örnek Kod

Aşağıdaki kaynak dosyaları Yapı İşlemi ve [PCH için Örnek Makefile](#sample-makefile-for-pch) [PCH Dosyaları](#pch-files-in-the-build-process) açıklanan makefile kullanılır. Yorumların önemli bilgiler içerdiğini unutmayın.

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
[MSVC Derleyicisi Seçenekleri](reference/compiler-options.md)
