---
title: "-homeparams (kayıt parametrelerini yığına Kopyala) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /homeparams
dev_langs:
- C++
helpviewer_keywords:
- /homeparams compiler option [C++]
- -homeparams compiler option [C++]
ms.assetid: 51067de4-24f7-436b-b8d9-bc867a7d53aa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fff1b206620ef9efee3fc22c83c8d5317e99b607
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="homeparams-copy-register-parameters-to-stack"></a>/homeparams (Kayıt Parametrelerini Yığına Kopyala)
İşlevi girişte yığında konumlarına yazılacak yazmaçlar zorlar parametre geçirildi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/homeparams  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Yalnızca Bu derleyici seçeneği olan [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] derleyicileri (yerel ve derleme).  
  
 Ne zaman parametreleri geçirilen bir [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] derleme çağırma kurallarını iste stackspace bile Yazmaçları geçirilen parametreler için parametreler. Daha fazla bilgi için bkz: [parametre geçirme](../../build/parameter-passing.md). Ancak, bir sürümde yapıdaki varsayılan olarak, kayıt parametrelerini yığına parametreleri için zaten sağlanan alanına yazılmayacak. Bu, bir en iyi duruma getirilmiş (sürüm) programınızın hata ayıklama derlemesine zorlaştırır.  
  
 Yayın derleme için kullanma **/homeparams** uygulamanızı ayıklayabilirsiniz emin olmak için. **/ homeparams** kayıt parametrelerini yığına açın yüklemek için bir döngü gerektiğinden performansı olumsuz anlamına gelmez.  
  
 Bir hata ayıklama derlemesi yığın her zaman Yazmaçları geçirilen parametre ile doldurulur.  
  
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