---
title: /Qfast_transcendentals (Hızlı Soyutları Zorla)
ms.date: 11/04/2016
f1_keywords:
- /Qfast_transcendentals
helpviewer_keywords:
- /Qfast_transcendentals
- Force Fast Transcendentals
ms.assetid: 4de24bd1-38e6-49d4-9a05-04c9937d24ac
ms.openlocfilehash: 512e658cf546e77bff6d58465932d2f830541521
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666134"
---
# <a name="qfasttranscendentals-force-fast-transcendentals"></a>/Qfast_transcendentals (Hızlı Soyutları Zorla)

aşkın işlevleri için satır içi kod oluşturur.

## <a name="syntax"></a>Sözdizimi

```
/Qfast_transcendentals
```

## <a name="remarks"></a>Açıklamalar

Bu derleyici seçeneğini yürütme hızını artırmak için satır içi kod dönüştürülecek aşkın işlevleri zorlar. Bu seçenek yalnızca ile birlikte kullanıldığında bir etkisi **/FP: dışında** veya **/FP: precise**. Aşkın işlevler için satır içi kod oluşturma zaten varsayılan davranıştır altında **Fast**.

Bu seçenek ile uyumsuz **/FP: strict**. Bkz: [FP (Floating-Point davranışını belirtin)](../../build/reference/fp-specify-floating-point-behavior.md) kayan nokta derleyici seçenekleri hakkında daha fazla bilgi.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[/Q Seçenekler (Düşük Düzey İşlemler)](../../build/reference/q-options-low-level-operations.md)<br/>
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)