---
title: -D (önişlemci tanımları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCNMakeTool.PreprocessorDefinitions
- VC.Project.VCCLCompilerTool.PreprocessorDefinitions
- /d
dev_langs:
- C++
helpviewer_keywords:
- preprocessor definition symbols
- constants, defining
- macros, compiling
- /D compiler option [C++]
- -D compiler option [C++]
- D compiler option [C++]
ms.assetid: b53fdda7-8da1-474f-8811-ba7cdcc66dba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3dc4da4235b57e9abd8e5f32b8f3e696bd1ce2de
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46397188"
---
# <a name="d-preprocessor-definitions"></a>/D (Önişlemci Tanımları)

Bir kaynak dosyası için önceden işleme simgesini tanımlar.

## <a name="syntax"></a>Sözdizimi

```
/Dname[= | # [{string | number}] ]
```

## <a name="remarks"></a>Açıklamalar

Bu simge ile birlikte kullanabileceğiniz `#if` veya `#ifdef` kaynak kodunu koşullu olarak derleyebilirsiniz. Sembol tanımını etkili kalır, kodda yeniden tanımlanıncaya ya kod tarafından tanımlı değil kadar `#undef` yönergesi.

**/D** aynı etkiye sahiptir `#define` hariç bir kaynak kodu dosyasının başlangıcında **/D** tırnak işaretleri komut satırında kaldırır ve `#define` onları korumasıdır.

Varsayılan olarak, simgeyle ilişkilendirilen değer 1'dir. Örneğin, **/D** `name` eşdeğerdir **/D**`name`**= 1**. Tanımı bu makalenin sonundaki örnekte **TEST** yazdırmak için `1`.

Kullanarak derleme yapıldığında **/D** `name` **=** simgeyle ilişkili değere sahip. Simge kodu koşullu olarak derlemek üzere kullanılmaya devam etse de, başka türlü bir değeri yoktur. Örnekte kullanarak derleme yaparsanız, **/DTEST =**, bir hata oluşur. Bu davranış kullanımını benzer `#define` olan veya olmayan bir değer.

Bu komut, TEST.c içinde DEBUG simgesini tanımlar:

**CL /DDEBUG TEST. C**

Bu komut tüm anahtar sözcüğü kaldırır `__far` TEST.c içinde:

**CL /D__far TEST =. C**

**CL** ortam değişkeni eşittir işareti içeren bir dizeye ayarlanamaz. Kullanılacak **/D** ile birlikte **CL** ortam değişkeni, eşittir işareti yerine sayı işaretini belirtmeniz gerekir:

```
SET CL=/DTEST#0
```

Komut isteminde önceden işleme simgesi tanımladığınızda, hem derleyici ayrıştırma kurallarını hem de kabuk ayrıştırma kurallarını göz önünde bulundurun. Örneğin, programınızda yüzde işareti önceden işleme simgesini (%) tanımlamak için, komut isteminde iki tane yüzde işareti karakteri (%%) belirtin, bir tane belirtmeniz durumunda ayrıştırma hatası yayılır.

```
CL /DTEST=%% TEST.C
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projeyi açmak **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Sol bölmede seçin **yapılandırma özellikleri**, **C/C++**, **önişlemci**.

1. Sağ bölmede, sağ sütununda **önişlemci tanımları** özelliği aşağı açılan menüsünü açın ve seçin **Düzenle**.

1. İçinde **önişlemci tanımları** iletişim kutusu (her satırda bir tane) ekleme, değiştirme veya bir veya daha fazla tanımlarını silebilir. Seçin **Tamam** yaptığınız değişiklikleri kaydedin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PreprocessorDefinitions%2A>.

## <a name="example"></a>Örnek

```
// cpp_D_compiler_option.cpp
// compile with: /DTEST
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

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[/U, /u (Simge Tanımlarını Kaldır)](../../build/reference/u-u-undefine-symbols.md)<br/>
[#undef Yönergesi (C/C++)](../../preprocessor/hash-undef-directive-c-cpp.md)<br/>
[#define Yönergesi (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)