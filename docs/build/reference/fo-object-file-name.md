---
title: -Fo (nesne dosya adı) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Fo
- VC.Project.VCCLCompilerTool.ObjectFile
- VC.Project.VCCLWCECompilerTool.ObjectFile
dev_langs:
- C++
helpviewer_keywords:
- Fo compiler option [C++]
- object files, naming
- /Fo compiler option [C++]
- -Fo compiler option [C++]
ms.assetid: 0e6d593e-4e7f-4990-9e6e-92e1dcbcf6e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ea552b149270b8e644140a4dd51f220648ef376e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="fo-object-file-name"></a>/Fo (Nesne Dosya Adı)
Bir nesne (.obj) dosya adı veya varsayılan yerine kullanılacak dizini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Fopathname  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu seçeneği kullanmazsanız, nesne dosyası temel kaynak dosyasının adını ve .obj uzantısı kullanır. Herhangi bir adı ve uzantısı istediğiniz kullanabilirsiniz, ancak kullanmak için önerilen kuraldır. obj.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **çıktı dosyaları** özellik sayfası.  
  
4.  Değiştirme **nesne dosya adı** özelliği.  Geliştirme ortamında nesne dosya uzantısı olması gerekir. obj.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ObjectFile%2A>.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komut satırını THIS.obj varolan bir dizin, \OBJECT, sürücüde b adlı bir nesne dosyası oluşturur  
  
```  
CL /FoB:\OBJECT\ THIS.C  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıktı dosyası (/ F) seçenekleri](../../build/reference/output-file-f-options.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [Yol Adını Belirtme](../../build/reference/specifying-the-pathname.md)