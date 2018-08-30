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
ms.openlocfilehash: 61bf8844a5471a97214ca6f3d3b5b473c9cd6217
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194669"
---
# <a name="ga-optimize-for-windows-application"></a>/GA (Windows Uygulaması için İyileştir)
İş parçacığı yerel depolama (TLS) değişkenleri erişmek için bir .exe dosyası için daha verimli kod sonuçlanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/GA  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **/GA** veri erişimi ile bildirilmiş [gt;__declspec(thread)](../../cpp/declspec.md) Windows tabanlı bir programı. Bu seçenek ayarlandığında [__tls_index](/windows/desktop/ProcThread/thread-local-storage) makrosu 0 olarak varsayılır.  
  
 Kullanarak **/GA** için bir DLL hatalı kod oluşturma neden olabilir.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).  
  
2.  Tıklayın **C/C++** klasör.  
  
3.  Tıklayın **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneğini yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)