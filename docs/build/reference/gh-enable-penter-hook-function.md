---
title: -Gh (_penter kanca işlevini etkinleştir) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 68497e4e760e1268a0175d5a68452678153896b8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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