---
title: /Gh (_penter Kanca İşlevini Etkinleştir)
ms.date: 11/04/2016
f1_keywords:
- _penter
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _penter function
- -Gh compiler option [C++]
ms.assetid: 1510a082-8a0e-486e-a309-6add814b494f
ms.openlocfilehash: 87815b5f0e0450b84acbe3c35b7ef4f31216ec72
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749299"
---
# <a name="gh-enable-_penter-hook-function"></a>/Gh (_penter Kanca İşlevini Etkinleştir)

Her yöntemin `_penter` veya işlevin başında işleviçin bir çağrıya neden olur.

## <a name="syntax"></a>Sözdizimi

```
/Gh
```

## <a name="remarks"></a>Açıklamalar

İşlev `_penter` herhangi bir kitaplığın bir parçası değildir ve `_penter`bir tanım sağlamak size kalmış.

Açıkça aramayı `_penter`planlamadığınız sürece, bir prototip sağlamanız gerekmez. İşlev aşağıdaki prototipe sahipmiş gibi görünmelidir ve girişteki tüm kayıtların içeriğini itmeli ve çıkışta değişmemiş içeriği patlatmalıdır:

```cpp
void __declspec(naked) __cdecl _penter( void );
```

Bu bildirim 64 bit projeler için kullanılamaz.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik Sayfaları** iletişim kutusunu açın. Ayrıntılar için [Visual Studio'da C++ derleyicisi ayarlanın ve özellikler oluşturun.](../working-with-project-properties.md)

1. **C/C++** klasörünü tıklatın.

1. Komut **Satırı** özelliği sayfasını tıklatın.

1. **Ek Seçenekler** kutusuna derleyici seçeneğini yazın.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="example"></a>Örnek

/Gh ile derlendiğinde **/Gh**aşağıdaki kod, `_penter` nasıl iki kez çağrıldığını gösterir; bir kez fonksiyon `main` girerken ve `x`bir kez fonksiyon girerken .

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

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
