---
title: -Qfast_transcendentals (hızlı Soyutları zorla) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Qfast_transcendentals
dev_langs:
- C++
helpviewer_keywords:
- /Qfast_transcendentals
- Force Fast Transcendentals
ms.assetid: 4de24bd1-38e6-49d4-9a05-04c9937d24ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d979dc9005921ce1a760b2e61c4519ef852b7f84
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709442"
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

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[/Q Seçenekler (düşük düzey işlemler)](../../build/reference/q-options-low-level-operations.md)
[derleyici seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)