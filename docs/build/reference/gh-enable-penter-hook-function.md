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
ms.openlocfilehash: 608472f3133464137d2d0f96128453e4239b16a2
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49162093"
---
# <a name="gh-enable-penter-hook-function"></a>/Gh (_penter Kanca İşlevini Etkinleştir)

Bir çağrısına neden `_penter` her yöntem veya işlev başlangıcında işlevi.

## <a name="syntax"></a>Sözdizimi

```
/Gh
```

## <a name="remarks"></a>Açıklamalar

`_penter` İşlevi herhangi kitaplığının parçası değildir ve sizin için bir tanım sağlamak için en fazla `_penter`.

Açıkça çağırmak planlamıyorsanız `_penter`, bir prototip sağlamanız gerekmez. İşlev aşağıdaki prototipe sahip, içeriği tüm kayıtları girişinde anında iletme gerekir ve Çıkışta değişmeden içerik pop gibi görünmelidir:

```
void __declspec(naked) __cdecl _penter( void );
```

Bu bildirim, 64-bit projeleri için kullanılabilir değil.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="example"></a>Örnek

Aşağıdaki kod ile derlendiğinde **/Gh**, gösterir nasıl `_penter` iki kez; adlı işlev girildiğinde bir kez `main` ve işlev girildiğinde bir kez `x`.

```cpp
// Gh_compiler_option.cpp
// compile with: /Gh
// processor: x86
#include <stdio.h>
void x() {}

int main() {
   x();
}

extern "C" void __declspec(naked) __cdecl _penter( void ) {
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

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)