---
title: -Fp (adı. PCH dosyası) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.PrecompiledHeaderFile
- /fp
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderFile
dev_langs:
- C++
helpviewer_keywords:
- Fp compiler option [C++]
- -Fp compiler option [C++]
- naming precompiler header files
- PCH files, naming
- names [C++], PCH
- .pch files, naming
- precompiled header files, naming
- /Fp compiler option [C++]
ms.assetid: 0fcd9cbd-e09f-44d3-9715-b41efb5d0be2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 80f59477695b83b33dd3cfa2b37837c5b52c8002
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376338"
---
# <a name="fp-name-pch-file"></a>/Fp (.Pch Dosyası Adlandır)
Bir yol adı için varsayılan yolu adını kullanmak yerine önceden derlenmiş üst bilgi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
> **/FP**_yol adı_  
  
## <a name="remarks"></a>Açıklamalar  
 Bu seçenek ile kullanmak [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md) veya [/Yu (önceden derlenmiş üst bilgi dosyasını kullanma)](../../build/reference/yu-use-precompiled-header-file.md) bir yol adı için varsayılan yolu adını kullanmak yerine önceden derlenmiş üst bilgi sağlamak için. De kullanabilirsiniz **/Fp** ile **/Yc** farklı bir önceden derlenmiş üst bilgi dosyası kullanıldığını belirtmek için **/Yc *** filename* bağımsız değişkeni ve kaynak dosyasının temel adı.  
  
 Yol adının bir parçası olarak bir uzantı belirtmezseniz .pch uzantısı varsayılır. Bir dosya adı olmadan bir dizin belirtin, varsayılan dosya adı VC ise*x*0.pch, burada *x* Visual C++ ana sürümü kullanılıyor.  
  
 Aynı zamanda **/Fp** seçeneğini **/Yu**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **önceden derlenmiş üstbilgiler** özellik sayfası.  
  
4.  Değiştirme **önceden derlenmiş üstbilgi dosyası** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderFile%2A>.  
  
## <a name="example"></a>Örnek  
 Programınızın hata ayıklama sürümü için önceden derlenmiş üst bilgi dosyası oluşturun ve başlık dosyaları ve kaynak kodu derleme istiyorsanız, bir komut gibi belirtebilirsiniz:  
  
```  
CL /DDEBUG /Zi /Yc /FpDPROG.PCH PROG.CPP  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komutu MYPCH.pch adlı bir önceden derlenmiş üst bilgi dosyası kullanımını belirtir. Derleyici PROG.cpp kaynak kodunda önceden MYAPP.h derlenmiş olduğunu ve önceden derlenmiş kod MYPCH.pch içinde bulunduğu varsayılmaktadır. MYPCH.pch içeriğini kullanır ve bir .obj dosyası oluşturmak için PROG.cpp kalan derler. Bu örnek çıktı PROG.exe adlı bir dosyadır.  
  
```  
CL /YuMYAPP.H /FpMYPCH.PCH PROG.CPP  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıktı dosyası (/ F) seçenekleri](../../build/reference/output-file-f-options.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [Yol Adını Belirtme](../../build/reference/specifying-the-pathname.md)