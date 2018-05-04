---
title: -GA (Windows uygulaması için İyileştir) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.OptimizeForWindowsApplication
- /ga
dev_langs:
- C++
helpviewer_keywords:
- /GA compiler option [C++]
- GA compiler option [C++]
- -GA compiler option [C++]
- Optimize for Windows compiler options
ms.assetid: be97323e-15a0-4836-862c-95980b51926a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 387732c5bde04970e3a467ca4f43f911afa7a9a6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ga-optimize-for-windows-application"></a>/GA (Windows Uygulaması için İyileştir)
İş parçacığı yerel depolaması (TLS) değişkenleri erişmek için bir .exe dosyası için daha verimli kodu sonuçlanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/GA  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **/GA** veri erişimi hızlandıran bildirilen ile [__declspec(thread)](../../cpp/declspec.md) Windows tabanlı bir programı. Bu seçeneği ayarlarken [__tls_index](http://msdn.microsoft.com/library/windows/desktop/ms686749) makrosu 0 olarak varsayılır.  
  
 Kullanarak **/GA** için DLL hatalı kod oluşturmasına neden olabilir.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneği yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)