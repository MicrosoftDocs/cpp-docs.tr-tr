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
ms.openlocfilehash: cb8083d874abe17add1d27096ebce143d03a04cf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315553"
---
# <a name="zl-omit-default-library-name"></a>/Zl (Varsayılan Kitaplık Adını Atla)

Varsayılan C çalışma zamanı kitaplık adını .obj dosyasından atlar. Varsayılan olarak, derleyici doğru kitaplık bağlayıcıya yönlendirmek için .obj dosyasına kitaplığının adı geçirir.

## <a name="syntax"></a>Sözdizimi

```
/Zl
```

## <a name="remarks"></a>Açıklamalar

Varsayılan kitaplık hakkında daha fazla bilgi için bkz. [çalışma zamanı kitaplığını kullan](md-mt-ld-use-run-time-library.md).

Kullanabileceğiniz **/Zl** planladığınız bir kitaplık içine yerleştirmek için .obj dosyalarını derlemek için. Kaydedilen toplam alan kitaplık adını atlama yalnızca az miktarda alan için bir tek .obj dosyasına kaydeder olsa da, birçok nesne modüller içeren bir kitaplıkta önemlidir.

Bu seçenek Gelişmiş bir seçenektir. Bu ayar, uygulamanız bu desteği bağlıysa, bağlama sırasında hatalarla sonuçlanır uygulamanız tarafından gerekli kılınabilen bazı C çalışma zamanı kitaplığı desteğiyle kaldırır. Bu seçeneği kullanırsanız, gerekli bileşenleri başka bir şekilde sağlamalısınız.

Kullanım [/nodefaultlıb (kitaplıkları yoksay)](nodefaultlib-ignore-libraries.md). Bağlayıcı kitaplık yok saymak için yönlendirmek için tüm .obj dosyalarında başvuruyor.

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

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **Gelişmiş** özellik sayfası.

1. Değiştirme **varsayılan kitaplık adlarını atlamak** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitDefaultLibName%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
