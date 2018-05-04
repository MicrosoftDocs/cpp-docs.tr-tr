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
ms.openlocfilehash: 4b8b386d55804421fb6cb454b4818db52e7cea85
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="d-preprocessor-definitions"></a>/D (Önişlemci Tanımları)
Bir kaynak dosyası için önceden işleme simgesini tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Dname[= | # [{string | number}] ]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu simge ile birlikte kullanabileceğiniz `#if` veya `#ifdef` kaynak kodu koşullu derlemek için. Sembol tanımına yürürlükte kodda tanımlandı veya kodun tanımsız kadar kalır `#undef` yönergesi.  
  
 **/D** aynı etkiye sahiptir `#define` tek fark, bir kaynak kodu dosyasının başındaki yönerge **/D** komut satırında tırnak işaretleri kaldırır ve `#define` bunları korur.  
  
 Varsayılan olarak, simgeyle ilişkilendirilen değer 1'dir. Örneğin, **/D** `name` eşdeğerdir **/D**`name`**= 1**. Örnekte tanımını bu makalenin sonunda **TEST** yazdırmak için gösterilen `1`.  
  
 Kullanarak derleme **/D** `name` **=** ilişkili bir değere sahip simge neden olur. Simge kodu koşullu olarak derlemek üzere kullanılmaya devam etse de, başka türlü bir değeri yoktur. Örnekte kullanarak derleme yaparsanız, **/DTEST =**, bir hata oluşur. Bu davranış kullanımını benzer `#define` olan veya olmayan bir değer.  
  
 Bu komut, TEST.c içinde DEBUG simgesini tanımlar:  
  
 **CL /DDEBUG SINAYIN. C**  
  
 Bu komut tüm anahtar sözcüğü kaldırır `__far` TEST.c içinde:  
  
 **CL /D__far = TEST. C**  
  
 **CL** ortam değişkenine eşittir işareti içeren bir dize olarak ayarlanamaz. Kullanılacak **/D** ile birlikte **CL** ortam değişkenine eşittir işareti yerine sayı işareti belirtmeniz gerekir:  
  
```  
SET CL=/DTEST#0  
```  
  
 Komut isteminde önceden işleme simgesi tanımladığınızda, hem derleyici ayrıştırma kurallarını hem de kabuk ayrıştırma kurallarını göz önünde bulundurun. Örneğin, programınızda yüzde işareti önceden işleme simgesini (%) tanımlamak için, komut isteminde iki tane yüzde işareti karakteri (%%) belirtin, bir tane belirtmeniz durumunda ayrıştırma hatası yayılır.  
  
```  
CL /DTEST=%% TEST.C  
```  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projeyi açın **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Sol bölmede seçin **yapılandırma özellikleri**, **C/C++**, **önişlemci**.  
  
3.  Sağ bölmede sağ taraftaki sütunun **önişlemci tanımları** özelliği, aşağı açılan menüsünü açın ve seçin **Düzenle**.  
  
4.  İçinde **önişlemci tanımları** iletişim kutusu (her satırda bir tane) ekleme, değiştirme ve bir veya daha fazla tanımlarını silebilir. Seçin **Tamam** yaptığınız değişiklikleri kaydetmek için.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PreprocessorDefinitions%2A>.  
  
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
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [/ U, /u (simge tanımlarını Kaldır)](../../build/reference/u-u-undefine-symbols.md)   
 [#undef yönergesi (C/C++)](../../preprocessor/hash-undef-directive-c-cpp.md)   
 [#define Yönergesi (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)