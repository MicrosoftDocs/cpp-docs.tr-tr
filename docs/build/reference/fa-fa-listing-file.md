---
title: "/ FA, /Fa (listeleme dosyası) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.AssemblerListingLocation
- VC.Project.VCCLCompilerTool.ConfigureASMListing
- VC.Project.VCCLWCECompilerTool.AssemblerOutput
- VC.Project.VCCLCompilerTool.AssemblerListingLocation
- /fa
- VC.Project.VCCLCompilerTool.AssemblerOutput
- VC.Project.VCCLCompilerTool.UseUnicodeForAssemblerListing
dev_langs: C++
helpviewer_keywords:
- FA compiler option [C++]
- /FA compiler option [C++]
- -FA compiler option [C++]
- listing file type
- assembly-only listing
ms.assetid: c7507d0e-c69d-44f9-b8e2-d2c398697402
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 44d21eae211bd2d01e202a516ef487c8d0df3684
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fa-fa-listing-file"></a>/FA, /Fa (Listeleme Dosyası)
Derleyici kodu içeren bir listeyi dosyası oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
> **/FA**[**c**\][**s**\][**u**]  
> **/FA**_yol adı_  
  
## <a name="remarks"></a>Açıklamalar  
`/FA` Derleyici seçeneği genellikle C veya C++ bir kaynak dosyaya karşılık gelen derleme her çeviri birimi için bir assembler listeleme dosyası oluşturur. Varsayılan olarak, yalnızca assembler ANSI kodlanmış listeleme dosyasına dahil edilir. İsteğe bağlı `c`, `s`, ve `u` bağımsız değişkenleri `/FA` denetim kodu olup olmadığını makine veya kaynak kodu listeleme assembler birlikte çıkarılır ve olup listenin kodlanmış UTF-8 olarak.  
  
Varsayılan olarak, her listeleme dosyası kaynak dosyası olarak aynı temel adını alır ve .asm uzantısına sahip. Ne zaman makine kodu dahil kullanarak `c` seçeneği, listeleme dosyası .cod uzantısı vardır. Adı ve uzantısı listeleme dosyası ve nerede oluşturulacağını kullanarak dizin değiştirebileceğiniz `/Fa` seçeneği.  

### <a name="fa-arguments"></a>/FA bağımsız değişkenleri  
yok  
Yalnızca assembler dil listesindeki dahil edilir.  
  
`c`  
İsteğe bağlı. Makine kodu listesindeki içerir.  
  
`s`  
İsteğe bağlı. Kaynak kodu listesindeki içerir.  
  
`u`İsteğe bağlı. UTF-8 biçiminde listeleme dosyası kodlar ve bayt sırası işaret içerir. Varsayılan olarak, dosya ANSI kodlanır. Kullanım `u` doğru herhangi bir sisteminde görüntüler bir listeyi dosyası oluşturmak için veya Unicode kullanıyorsanız, kaynak kodu dosyaları derleyici giriş olarak.  
  
Her iki `s` ve `u` belirtilir ve dosya bir kaynak kod kullanıyorsa, UTF-8 sonra .asm dosyasındaki kod satırı düzgün görüntülenmeyebilir dışında bir Unicode kodlama.  
  
### <a name="fa-argument"></a>/FA bağımsız değişken  
yok  
Bir *kaynak*.asm dosyası, her kaynak kodu dosyasının derlemedeki için oluşturulur.  
  
*Dosya adı* adlı bir listeyi dosyası *filename*.asm geçerli dizinde yerleştirilir. Bu yalnızca bir tek kaynak kodu dosyasının derlerken geçerlidir.  
  
*dosyaadı.uzantı*  
Adlı bir listeyi dosyası *dosyaadı.uzantı* geçerli dizinde yerleştirilir. Bu yalnızca bir tek kaynak kodu dosyasının derlerken geçerlidir.  
  
*Dizin*\  
Bir *source_file*.asm dosya oluşturulur ve belirtilen yerleştirilen *directory* her kaynak kodu dosyasının derlemedeki için. Gerekli eğik unutmayın. Yalnızca geçerli disk üzerindeki yollara izin verilir.  
  
*Dizin*\\*filename* adlı bir listeyi dosyası *filename*.asm yerleştirilir belirtilen *directory*. Bu yalnızca bir tek kaynak kodu dosyasının derlerken geçerlidir.  
  
*Dizin*\\*dosyaadı.uzantı*  
Adlı bir listeyi dosyası *dosyaadı.uzantı* yerleştirildiğinde belirtilen *directory*. Bu yalnızca bir tek kaynak kodu dosyasının derlerken geçerlidir.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Açık **C/C++** klasörü ve select **çıktı dosyaları** özellik sayfası.  
  
3.  Değiştirme **derleyici çıktı** ayarlamak için özellik `/FAc` ve `/FAs` derleyici, makine ve kaynak kodu için Seçenekler. Değiştirme **kullanım listeleme Assembler Unicode için** ayarlamak için özellik `/FAu` ANSI veya UTF-8 çıktı seçeneği. Değiştirme **ASM listesi konumu** ayarlamak için `/Fa` dosya adını ve konumunu listeleme seçeneği.  
  
Her ikisi de bu ayarı Not **derleyici çıktı** ve **kullanım listeleme Assembler Unicode için** özellikleri neden olabilir [komut satırı uyarısı D9025](../../error-messages/tool-errors/command-line-warning-d9025.md). IDE bu seçeneklerinde birleştirmek için kullanın **ek seçenekler** alanındaki **komut satırı** özellik sayfasında yerine.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerListingLocation%2A> veya <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerOutput%2A>. Belirtmek için `/FAu`, bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="example"></a>Örnek  
Aşağıdaki komut satırını birleşik kaynak oluşturur ve makine kod listesi HELLO.cod çağrılır:  
  
```  
CL /FAcs HELLO.CPP  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıktı dosyası (/ F) seçenekleri](../../build/reference/output-file-f-options.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [Yol adını belirtme](../../build/reference/specifying-the-pathname.md)