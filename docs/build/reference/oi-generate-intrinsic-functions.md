---
description: Şu konuda daha fazla bilgi edinin:/Oi (Iç Işlevler üret)
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
ms.openlocfilehash: fc08ff495391092115197fe70e8c3673b77f32e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214285"
---
# <a name="oi-generate-intrinsic-functions"></a>/Oi (İç İşlevler Üret)

Uygulamanızın daha hızlı çalışmasına yardımcı olan işlevin iç veya diğer özel formlarıyla birlikte bazı işlev çağrılarını değiştirir.

## <a name="syntax"></a>Syntax

```
/Oi[-]
```

## <a name="remarks"></a>Açıklamalar

İç işlevleri kullanan programlar, işlev çağrılarının ek yüküne sahip olmadıkları için daha hızlıdır, ancak oluşturulan ek kod nedeniyle daha büyük olabilir.

İç formlara sahip olan işlevler hakkında daha fazla bilgi için bkz. [iç](../../preprocessor/intrinsic.md) öğe.

**/Oi** yalnızca derleyiciye yönelik bir istek, bazı işlev çağrılarını iç derleyiciler ile değiştirir; Derleyici, daha iyi performans elde edilmesine neden olacak şekilde işlevi çağırabilir (ve işlev çağrısını bir iç ile değiştirmez).

**x86 özgü**

İç kayan nokta işlevleri, giriş değerleri üzerinde herhangi bir özel denetim gerçekleştirmez ve bu nedenle kısıtlanmış giriş aralıklarında çalışır ve aynı ada sahip kitaplık yordamlarından farklı özel durum işleme ve sınır koşullarına sahiptir. Gerçek iç formların kullanılması, IEEE özel durum işlemenin kaybını ve işlevlerin kaybedilmesi ve işlevselliğin kaybı anlamına gelir `_matherr` `errno` ; IKINCISI ise ANSI uygunluk kaybı anlamına gelir. Ancak, iç formlar kayan nokta yoğunluklu programları önemli ölçüde hızlandırabilir ve birçok program için uyumluluk sorunları çok pratik bir değerdir.

Gerçek iç kayan nokta seçeneklerinin oluşturulmasını geçersiz kılmak için [za](za-ze-disable-language-extensions.md) derleyici seçeneğini kullanabilirsiniz. Bu durumda işlevler, bağımsız değişkenleri program yığınına döndürmek yerine doğrudan kayan nokta yongasına geçiren kitaplık yordamları olarak oluşturulur.

**Son x86 özel**

Ayrıca, bir işlev çağrısını açıkça zorlamak için iç işlevler veya [işlev (C/C++)](../../preprocessor/function-c-cpp.md) oluşturmak üzere [iç](../../preprocessor/intrinsic.md) işlevleri de kullanabilirsiniz.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **İyileştirme** Özellik sayfasına tıklayın.

1. **Iç Işlevleri etkinleştir** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableIntrinsicFunctions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/O seçenekler (kodu Iyileştirme)](o-options-optimize-code.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)<br/>
[Derleyici Iç bilgileri](../../intrinsics/compiler-intrinsics.md)
