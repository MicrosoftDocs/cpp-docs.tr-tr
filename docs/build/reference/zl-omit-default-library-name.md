---
title: /Zl (Varsayılan Kitaplık Adını Atla)
ms.date: 11/04/2016
f1_keywords:
- /zi
- VC.Project.VCCLCompilerTool.OmitDefaultLibName
helpviewer_keywords:
- -Zl compiler option [C++]
- ZI compiler option
- Omit Default Library Name compiler option
- /Zl compiler option [C++]
- default libraries, omitting names
ms.assetid: b27d39d0-44d6-498c-84ae-27c1326fee59
ms.openlocfilehash: 1bcb90dbf071253dc0561845e3bd713dc42d5aef
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988559"
---
# <a name="zl-omit-default-library-name"></a>/Zl (Varsayılan Kitaplık Adını Atla)

. Obj dosyasından varsayılan C çalışma zamanı kitaplığı adını atlar. Varsayılan olarak, derleyici, bağlayıcıyı doğru kitaplığa yönlendirmek için kitaplığın adını. obj dosyasına koyar.

## <a name="syntax"></a>Sözdizimi

```
/Zl
```

## <a name="remarks"></a>Açıklamalar

Varsayılan kitaplık hakkında daha fazla bilgi için bkz. [çalışma zamanı kitaplığı kullanma](md-mt-ld-use-run-time-library.md).

Bir kitaplığa koymak üzere planladığınız. obj dosyalarını derlemek için **/zl** kullanabilirsiniz. Kitaplık adının atlanması tek bir. obj dosyası için yalnızca küçük miktarda alan kaydetse de, kaydedilen toplam alan birçok nesne modülünü içeren bir kitaplıkta önemli olur.

Bu seçenek gelişmiş bir seçenektir. Bu seçeneğin ayarlanması, uygulamanız tarafından gerekebilecek bazı C çalışma zamanı kitaplığı desteğini kaldırır ve uygulamanız bu desteğe bağımlıysa bağlantı zamanı hatalarına neden olur. Bu seçeneği kullanırsanız, gerekli bileşenleri başka bir şekilde sağlamanız gerekir.

[/Nodefaultlib (kitaplıkları Yoksay)](nodefaultlib-ignore-libraries.md)kullanın. Bağlayıcıyı tüm. obj dosyalarındaki kitaplık başvurularını yoksayacak şekilde yönlendirmek için.

Daha fazla bilgi için bkz. [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md).

**/Zl**ile derlerken `_VC_NODEFAULTLIB` tanımlanmıştır.  Örneğin:

```cpp
// vc_nodefaultlib.cpp
// compile with: /Zl
void Test() {
   #ifdef _VC_NODEFAULTLIB
      int i;
   #endif

   int i;   // C2086
}
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++**  klasörüne tıklayın.

1. **Gelişmiş** Özellik sayfasına tıklayın.

1. **Varsayılan kitaplık adlarını atla** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitDefaultLibName%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
