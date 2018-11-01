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
ms.openlocfilehash: ba30efd76e94749dd261f3528535d674b5e155e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621916"
---
# <a name="zl-omit-default-library-name"></a>/Zl (Varsayılan Kitaplık Adını Atla)

Varsayılan C çalışma zamanı kitaplık adını .obj dosyasından atlar. Varsayılan olarak, derleyici doğru kitaplık bağlayıcıya yönlendirmek için .obj dosyasına kitaplığının adı geçirir.

## <a name="syntax"></a>Sözdizimi

```
/Zl
```

## <a name="remarks"></a>Açıklamalar

Varsayılan kitaplık hakkında daha fazla bilgi için bkz. [çalışma zamanı kitaplığını kullan](../../build/reference/md-mt-ld-use-run-time-library.md).

Kullanabileceğiniz **/Zl** planladığınız bir kitaplık içine yerleştirmek için .obj dosyalarını derlemek için. Kaydedilen toplam alan kitaplık adını atlama yalnızca az miktarda alan için bir tek .obj dosyasına kaydeder olsa da, birçok nesne modüller içeren bir kitaplıkta önemlidir.

Bu seçenek Gelişmiş bir seçenektir. Bu ayar, uygulamanız bu desteği bağlıysa, bağlama sırasında hatalarla sonuçlanır uygulamanız tarafından gerekli kılınabilen bazı C çalışma zamanı kitaplığı desteğiyle kaldırır. Bu seçeneği kullanırsanız, gerekli bileşenleri başka bir şekilde sağlamalısınız.

Kullanım [/nodefaultlıb (kitaplıkları yoksay)](../../build/reference/nodefaultlib-ignore-libraries.md). Bağlayıcı kitaplık yok saymak için yönlendirmek için tüm .obj dosyalarında başvuruyor.

Daha fazla bilgi için [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md).

İle derlerken **/Zl**, `_VC_NODEFAULTLIB` tanımlanır.  Örneğin:

```
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

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **Gelişmiş** özellik sayfası.

1. Değiştirme **varsayılan kitaplık adlarını atlamak** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitDefaultLibName%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)