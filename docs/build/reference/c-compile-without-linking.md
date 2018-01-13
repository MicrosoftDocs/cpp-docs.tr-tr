---
title: "-c (bağlamadan Derle) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /c
dev_langs: C++
helpviewer_keywords:
- suppress link
- cl.exe compiler, compiling without linking
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 8017fc3d-e5dd-4668-a1f7-3120daa95d20
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 112e063af9c56ead8ae7e8f59fe88853ff55f7b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="c-compile-without-linking"></a>/c (Bağlamadan Derle)
BAĞLANTI otomatik çağrısı engeller.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/c  
```  
  
## <a name="remarks"></a>Açıklamalar  
 İle derleme **/c** yalnızca .obj dosyaları oluşturur. Derleme bağlama aşamasını gerçekleştirmek için seçenekler ve uygun dosya ile bağlantı açıkça çağırmalıdır.  
  
 Geliştirme ortamında oluşturulan herhangi bir iç projeye kullanan **/c** varsayılan seçeneği.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
-   Bu seçenek geliştirme ortamında kullanılamaz.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bu derleyici seçeneği programlı olarak ayarlamak için bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileOnly%2A>.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komut satırını FIRST.obj ve SECOND.obj nesne dosyaları oluşturur. THIRD.obj göz ardı edilir.  
  
```  
CL /c FIRST.C SECOND.C THIRD.OBJ  
```  
  
 Yürütülebilir bir dosya oluşturmak için bağlantı çağırmanız gerekir:  
  
```  
LINK firsti.obj second.obj third.obj /OUT:filename.exe  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)