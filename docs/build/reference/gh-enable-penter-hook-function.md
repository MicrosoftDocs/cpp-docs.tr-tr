---
title: "-Gh (_penter kanca işlevini etkinleştir) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _penter
dev_langs:
- C++
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _penter function
- -Gh compiler option [C++]
ms.assetid: 1510a082-8a0e-486e-a309-6add814b494f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dec38a8822bb8a330c4dccff9833780ea3a0a45d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="gh-enable-penter-hook-function"></a>/Gh (_penter Kanca İşlevini Etkinleştir)
Çağrı neden `_penter` her yöntemi veya işlev başlangıç işlevi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Gh  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `_penter` İşlevi herhangi bir kitaplığı parçası değil ve sizin için bir tanımını sağlamak üzere kadar `_penter`.  
  
 Açıkça çağırma planlamıyorsanız `_penter`, prototip sağlamanız gerekmez. İşlevi aşağıdaki prototipe vardı ve tüm yazmaçların içeriğini girişinde itme gerekir ve Çıkışta değişmeden içerik pop gibi görünmelidir:  
  
```  
void __declspec(naked) _cdecl _penter( void );  
```  
  
 Bu bildirim 64-bit projeleri için kullanılabilir değil.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneği yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod ile derlendiğinde **/Gh**, gösterir nasıl `_penter` iki kez; adlı işlevi girerken bir kez `main` işlevi girerken bir kez `x`.  
  
```  
// Gh_compiler_option.cpp  
// compile with: /Gh  
// processor: x86  
#include <stdio.h>  
void x() {}  
  
int main() {  
   x();  
}  
  
extern "C" void __declspec(naked) _cdecl _penter( void ) {  
   _asm {  
      push eax  
      push ebx  
      push ecx  
      push edx  
      push ebp  
      push edi  
      push esi  
    }  
  
   printf_s("\nIn a function!");  
  
   _asm {  
      pop esi  
      pop edi  
      pop ebp  
      pop edx  
      pop ecx  
      pop ebx  
      pop eax  
      ret  
    }  
}  
```  
  
```Output  
In a function!  
In a function!  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)