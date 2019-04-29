---
title: /Qfast_transcendentals (Hızlı Soyutları Zorla)
ms.date: 11/04/2016
f1_keywords:
- /Qfast_transcendentals
helpviewer_keywords:
- /Qfast_transcendentals
- Force Fast Transcendentals
ms.assetid: 4de24bd1-38e6-49d4-9a05-04c9937d24ac
ms.openlocfilehash: 383a915721d627367ca2ca035957df947996bbe2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319323"
---
# <a name="qfasttranscendentals-force-fast-transcendentals"></a>/Qfast_transcendentals (Hızlı Soyutları Zorla)

aşkın işlevleri için satır içi kod oluşturur.

## <a name="syntax"></a>Sözdizimi

```
/Qfast_transcendentals
```

## <a name="remarks"></a>Açıklamalar

Bu derleyici seçeneğini yürütme hızını artırmak için satır içi kod dönüştürülecek aşkın işlevleri zorlar. Bu seçenek yalnızca ile birlikte kullanıldığında bir etkisi **/FP: dışında** veya **/FP: precise**. Aşkın işlevler için satır içi kod oluşturma zaten varsayılan davranıştır altında **Fast**.

Bu seçenek ile uyumsuz **/FP: strict**. Bkz: [FP (Floating-Point davranışını belirtin)](fp-specify-floating-point-behavior.md) kayan nokta derleyici seçenekleri hakkında daha fazla bilgi.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Q Seçenekler (Düşük Düzey İşlemler)](q-options-low-level-operations.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
