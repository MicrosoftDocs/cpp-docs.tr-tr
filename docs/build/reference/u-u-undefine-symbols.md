---
title: "-U, -u (simge tanımlarını Kaldır) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCCLWCECompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCCLCompilerTool.UndefineAllPreprocessorDefinitions
- /u
- VC.Project.VCCLWCECompilerTool.UndefineAllPreprocessorDefinitions
dev_langs:
- C++
helpviewer_keywords:
- -U compiler option [C++]
- Undefine Symbols compiler option
- /U compiler option [C++]
- U compiler option [C++]
ms.assetid: 7bc0474f-6d1f-419b-807d-0d8816763b2a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 18fdaf0c2cb980f1ed19fdfc0577769a9985cf85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="u-u-undefine-symbols"></a>/U, /u (Simge Tanımlarını Kaldır)
**/U** derleyici seçeneği belirtilen önişlemci sembolü undefines. **/U** derleyici seçeneği undefines derleyici tanımlar Microsoft özgü simgeler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/U[ ]symbol  
/u  
```  
  
## <a name="arguments"></a>Arguments  
 `symbol`  
 Tanımsız önişlemci simge.  
  
## <a name="remarks"></a>Açıklamalar  
 Ne **/U** veya **/u** seçeneği kullanılarak oluşturulan bir simge tanımlarını Kaldır **#define** yönergesi.  
  
 **/U** seçeneği kullanılarak önceden tanımlanmış bir simge tanımlarını Kaldır **/D** seçeneği.  
  
 Varsayılan olarak, aşağıdaki Microsoft özgü simgeleri derleyici tanımlar.  
  
|Simgesi|İşlev|  
|------------|--------------|  
|_CHAR_UNSIGNED|Default char türü imzasız. Ne zaman tanımlanan [/J](../../build/reference/j-default-char-type-is-unsigned.md) seçeneği belirtildi.|  
|_CPPRTTI|Derlenmiş kod ile tanımlanan [/GR](../../build/reference/gr-enable-run-time-type-information.md) seçeneği.|  
|_CPPUNWIND|Derlenmiş kod ile tanımlanan [/EHsc](../../build/reference/eh-exception-handling-model.md) seçeneği.|  
|_DLL|Ne zaman tanımlanan [/MD](../../build/reference/md-mt-ld-use-run-time-library.md) seçeneği belirtildi.|  
|_M_IX86|Varsayılan olarak x86 için 600 için tanımlanmış hedefler.|  
|_MSC_VER|Daha fazla bilgi için bkz: [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md).|  
|_WIN32|WIN32 uygulama için tanımlanmış. Her zaman tanımlı.|  
|_MT|Ne zaman tanımlanan [/MD veya/MT](../../build/reference/md-mt-ld-use-run-time-library.md) seçeneği belirtildi.|  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **Gelişmiş** özellik sayfası.  
  
4.  Değiştirme **tanımsız önişlemci tanımları** veya **tanımsız tüm önişlemci tanımları** özellikleri.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefineAllPreprocessorDefinitions%2A> veya <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefinePreprocessorDefinitions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [/J (varsayılan karakter türü imzasız)](../../build/reference/j-default-char-type-is-unsigned.md)   
 [/gr (çalışma zamanı türü bilgileri etkinleştir)](../../build/reference/gr-enable-run-time-type-information.md)   
 [/EH (özel durum işleme modeli)](../../build/reference/eh-exception-handling-model.md)   
 [/ MD, / MT, /LD (çalışma zamanı kitaplığını kullan)](../../build/reference/md-mt-ld-use-run-time-library.md)