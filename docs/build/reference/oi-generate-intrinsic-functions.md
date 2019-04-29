---
title: /Oi (İç İşlevler Üret)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableIntrinsicFunctions
- /oi
- VC.Project.VCCLWCECompilerTool.EnableIntrinsicFunctions
helpviewer_keywords:
- Oi compiler option [C++]
- intrinsic functions, generate
- /Oi compiler option [C++]
- -Oi compiler option [C++]
- generate intrinsic functions compiler option [C++]
ms.assetid: fa4a3bf6-0ed8-481b-91c0-add7636132b4
ms.openlocfilehash: f3afedade6f99129c21069e5117daa4ceb616cc2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320350"
---
# <a name="oi-generate-intrinsic-functions"></a>/Oi (İç İşlevler Üret)

Uygulamanızı yardımcı iç veya aksi halde özel formlarla işlevin bazı işlevini çağıran değiştirir daha hızlı çalışır.

## <a name="syntax"></a>Sözdizimi

```
/Oi[-]
```

## <a name="remarks"></a>Açıklamalar

İşlev çağrılarının ek yükü yoktur ancak oluşturulan ek kod nedeniyle daha büyük olduğundan iç işlevler kullanan programlar daha hızlıdır.

Bkz: [iç](../../preprocessor/intrinsic.md) işlevleri üzerinde iç biçimlere sahip daha fazla bilgi için.

**/Oi** yapı içleri ile; bazı işlev çağrıları değiştirmek için yalnızca bir istek derleyici derleyici işlevi çağırabilir (ve işlev çağrısı bir iç değiştirmeyebilir) daha iyi performans gösterecekse.

**x86 belirli**

İç kayan nokta işlevleri değil giriş değerleri üzerinde herhangi bir özel denetimleri gerçekleştirmek ve bu nedenle kısıtlı giriş aralığındaki çalışma ve farklı bir özel durum işleme ve sınır koşullarından kitaplık yordamları aynı ada sahip. Gerçek iç biçimleri kullanarak gelir kaybı IEEE özel durum işleme ve kaybı `_matherr` ve `errno` işlevselliği; ikincisi ANSI uyumluluğu kaybı anlamına gelir. Ancak, iç biçimleri kayan noktaya yoğun programları hızlandırılabilir ve birçok programları için az pratik değerini uyumluluk sorunlarıdır.

Kullanabileceğiniz [Za](za-ze-disable-language-extensions.md) gerçek iç kayan nokta seçeneklerinin oluşturulmasını geçersiz kılmak için derleyici seçeneği. Bu durumda işlevler, bağımsız değişkenleri program yığınına döndürmek yerine doğrudan kayan nokta yongasına geçiren kitaplık yordamları olarak oluşturulur.

**Son x86 belirli**

Ayrıca [iç](../../preprocessor/intrinsic.md) iç işlevler oluşturma veya [işlevi (C/C++)](../../preprocessor/function-c-cpp.md) açıkça bir işlev çağrısı zorlamak için.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **iyileştirme** özellik sayfası.

1. Değiştirme **iç işlevleri etkinleştir** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableIntrinsicFunctions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/O Seçenekler (Kodu İyileştir)](o-options-optimize-code.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[Derleyici İç Bilgileri](../../intrinsics/compiler-intrinsics.md)
