---
title: /D (Önişlemci Tanımları)
ms.date: 09/18/2019
f1_keywords:
- VC.Project.VCNMakeTool.PreprocessorDefinitions
- VC.Project.VCCLCompilerTool.PreprocessorDefinitions
- /d
helpviewer_keywords:
- preprocessor definition symbols
- constants, defining
- macros, compiling
- /D compiler option [C++]
- -D compiler option [C++]
- D compiler option [C++]
ms.assetid: b53fdda7-8da1-474f-8811-ba7cdcc66dba
ms.openlocfilehash: b10d611d38508f5696dd3b72fb8458e9b61082c8
ms.sourcegitcommit: 389c559918d9bfaf303d262ee5430d787a662e92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71230392"
---
# <a name="d-preprocessor-definitions"></a>/D (Önişlemci Tanımları)

Bir kaynak dosyası için önceden işleme simgesini tanımlar.

## <a name="syntax"></a>Sözdizimi

> **/D** ]ad | [`=` [{ | dize*numarası* }]] \`#` \[
> **/D** \[ ]ad [[{`=` dizenumarası | }]] |  `"``#``"`

## <a name="remarks"></a>Açıklamalar

Bu sembolü, kaynak kodu koşullu olarak `#if` derlemek `#ifdef` için veya ile birlikte kullanabilirsiniz. Sembol tanımı, kodda yeniden tanımlanana kadar veya bir `#undef` yönergeyle kodda tanımlanana kadar yürürlükte kalır.

**/D** , kaynak kodu dosyasının başındaki bir `#define` yönergeyle aynı etkiye sahiptir. Aradaki fark, **/d** 'nin komut satırındaki tırnak işaretlerini şeritleri ve bir `#define` yönerge tarafından devam eder. **/D** ve sembol arasında boşluk olabilir. Sembol ve eşittir işareti arasında ya da eşittir işareti ile atanan herhangi bir değer arasında boşluk olamaz.

Varsayılan olarak, simgeyle ilişkilendirilen değer 1'dir. Örneğin, `/D name` öğesine `/D name=1`eşdeğerdir. Bu makalenin sonundaki örnekte, tanımı `TEST` Yazdır `1`olarak gösterilir.

Kullanılarak `/D name=` derlenirken, sembol *adının* ilişkili bir değer olmaması gerekir. Simge kodu koşullu olarak derlemek üzere kullanılmaya devam etse de, başka türlü bir değeri yoktur. Örnekte, kullanarak `/DTEST=`derlerseniz bir hata oluşur. Bu davranış, `#define` ile veya arasında bir değer olmadan kullanılmasına benzer.

**/D** seçeneği işlev benzeri makro tanımlarını desteklemez. Komut satırında tanımlanamaz tanımları eklemek için, [/Fi (zorunlu içerme dosyası adı)](fi-name-forced-include-file.md) derleyici seçeneğini göz önünde bulundurun.

Ek sembolleri tanımlamak için komut satırında **/d** ' i birden çok kez kullanabilirsiniz. Aynı sembol birden çok kez tanımlanmışsa, son tanım kullanılır.

Bu komut, TEST.c içinde DEBUG simgesini tanımlar:

```cmd
CL /DDEBUG TEST.C
```

Bu komut, test. c içindeki anahtar `__far` sözcüğünün tüm oluşumlarını kaldırır:

```cmd
CL /D __far= TEST.C
```

**CL** ortam değişkeni eşittir işaretini içeren bir dizeye ayarlanamaz. **/D** 'yi **CL** ortam değişkeniyle birlikte kullanmak için eşittir işareti yerine sayı işaretini (`#`) belirtmeniz gerekir:

```cmd
SET CL=/DTEST#0
```

Komut isteminde önceden işleme simgesi tanımladığınızda, hem derleyici ayrıştırma kurallarını hem de kabuk ayrıştırma kurallarını göz önünde bulundurun. Örneğin, programınızda bir yüzde işareti ön işleme simgesi (`%`) tanımlamak için, komut isteminde iki adet yüzde işareti karakteri (`%%`) belirtin. Yalnızca birini belirtirseniz, ayrıştırma hatası yayınlanır.

```cmd
CL /DTEST=%% TEST.C
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz [. C++ Visual Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. Sol bölmede, **yapılandırma özellikleri**, **C/C++** , **Önişlemci**' yi seçin.

1. Sağ bölmede, **Önişlemci tanımları** özelliğinin sağ sütununda, açılan menüyü açın ve **Düzenle**' yi seçin.

1. Ön **Işlemci tanımları** iletişim kutusunda, bir veya daha fazla tanımı ekleyin (her satır için bir tane), değiştirin veya silin. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

   Burada belirttiğiniz tanımlara '/D ' seçenek önekini eklemeniz gerekmez. Özellik sayfasında, tanımlar noktalı virgülle (`;`) ayrılır.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PreprocessorDefinitions%2A>.

## <a name="example"></a>Örnek

```cpp
// cpp_D_compiler_option.cpp
// compile with: cl /EHsc /DTEST cpp_D_compiler_option.cpp
#include <stdio.h>

int main( )
{
#ifdef TEST
    printf_s("TEST defined %d\n", TEST);
#else
    printf_s("TEST not defined\n");
#endif
}
```

```Output
TEST defined 1
```

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)\
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)\
[/FI (zorunlu içerme dosyasını Adlandır)](fi-name-forced-include-file.md)\
[/U,/u (sembolleri tanımlama)](u-u-undefine-symbols.md)\
[#undef yönergesi (C/C++)](../../preprocessor/hash-undef-directive-c-cpp.md)\
[#define Yönergesi (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)
