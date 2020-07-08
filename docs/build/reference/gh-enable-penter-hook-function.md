---
title: /Gh (_penter kanca işlevini etkinleştir)
description: Sağlanan _penter işlevini çağırmak için/GH derleyici seçeneğini açıklar.
ms.date: 07/06/2020
f1_keywords:
- _penter
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _penter function
- -Gh compiler option [C++]
ms.assetid: 1510a082-8a0e-486e-a309-6add814b494f
ms.openlocfilehash: 96597d964e6a341aa25f4d52d34974949eb7b096
ms.sourcegitcommit: 85d96eeb1ce41d9e1dea947f65ded672e146238b
ms.contentlocale: tr-TR
ms.lasthandoff: 07/07/2020
ms.locfileid: "86058588"
---
# <a name="gh-enable-_penter-hook-function"></a>/Gh (_penter kanca işlevini etkinleştir)

`_penter`Her yöntemin veya işlevin başlangıcında işleve bir çağrı oluşmasına neden olur.

## <a name="syntax"></a>Syntax

> **`/Gh`**

## <a name="remarks"></a>Açıklamalar

`_penter`İşlev herhangi bir kitaplığın parçası değil. İçin bir tanım sağlamanız gerekir `_penter` .

Açıkça çağırmanız planlanmadığınız takdirde `_penter` , prototip sağlamanız gerekmez. İşlev, girişte tüm Yazmaçların içeriğini itmeli ve çıkışta değiştirilmeyen içeriği bir pencerede döndürmelidir. Aşağıdaki prototiple sahip gibi görünmelidir:

```cpp
void __declspec(naked) __cdecl _penter( void );
```

Bu bildirim 64-bit projeler için kullanılamaz.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** özellik sayfasını açın.

1. **Ek seçenekler** kutusunda derleyici seçeneğini girin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="example"></a>Örnek

Aşağıdaki kod **/GH**ile derlendiğinde, ne `_penter` kadar iki kez çağrıldığını gösterir; işlev girilirken bir kez `main` ve işlev girilirken bir kez `x` . Örnek, ayrı olarak derleyebileceğiniz iki kaynak dosyadan oluşur.

```cpp
// local_penter.cpp
// compile with: cl /EHsc /c local_penter.cpp
// processor: x86
#include <stdio.h>

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

```cpp
// Gh_compiler_option.cpp
// compile with: cl /EHsc /Gh Gh_compiler_option.cpp local_penter.obj
// processor: x86
#include <stdio.h>

void x() {}

int main() {
   x();
}
```

Çalıştırıldığında, yerel işlev, `_penter` ve ' a girişte çağrılır `main` `x` :

```Output

In a function!
In a function!
```

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyicisi seçenekleri](compiler-options.md)<br/>
[MSVC derleyicisi komut satırı söz dizimi](compiler-command-line-syntax.md)<br/>
[`/GH`(_Pexit Kanca işlevini etkinleştir)](gh-enable-pexit-hook-function.md)
