---
description: Daha fazla bilgi edinin:/GS (denetim yığını denetim çağrıları)
title: /Gs (Denetim Yığını Denetim Çağrıları)
ms.date: 10/25/2018
f1_keywords:
- /GS
helpviewer_keywords:
- disabling stack probes
- GS compiler option [C++]
- /GS compiler option [C++]
- stack, stack probes
- stack probes
- -GS compiler option [C++]
- stack checking calls
ms.assetid: 40daed7c-f942-4085-b872-01e12b37729e
ms.openlocfilehash: 128a5ad4dbcba15dfc5b76313b8576ce1448ec68
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200174"
---
# <a name="gs-control-stack-checking-calls"></a>/Gs (Denetim Yığını Denetim Çağrıları)

Yığın araştırmaları eşiğini denetler.

## <a name="syntax"></a>Syntax

> **/GS**[*Boyut*]

## <a name="arguments"></a>Arguments

*boyutla*<br/>
Seçim Yığın araştırması başlatılmadan önce yerel değişkenlerin kaplayabileceği bayt sayısı. **/GS** ve *Boyut* arasında boşluk yapılmasına izin verilmez.

## <a name="remarks"></a>Açıklamalar

*Yığın araştırması* , derleyicinin işlev çağrısının başına eklediği kod dizisidir. Başlatıldığında, yığın araştırması, işlevin yerel değişkenlerini depolamak için gereken alan miktarına göre zararsız şekilde belleğe ulaşır. Bu, işlevin geri kalanı çalıştırılmadan önce gerekirse, işletim sisteminin ek yığın belleğinde şeffaf bir şekilde sayfasına neden olur.

Varsayılan olarak, bir işlev yığın alanı için birden fazla sayfa gerektirdiğinde, derleyici yığın araştırması başlatan kodu oluşturur. Bu, x86, x64, ARM ve ARM64 platformları için **/Gs4096** ' ın bir derleyici seçeneğine eşdeğerdir. Bu değer, bir uygulamanın ve Windows bellek yöneticisinin, çalışma zamanında dinamik olarak program yığınına kaydedilen bellek miktarını artırması için izin verir.

> [!NOTE]
> **/Gs4096** varsayılan değeri, Windows için uygulama yığınının çalışma zamanında düzgün bir şekilde büyümesini sağlar. Tam olarak neden değiştirmeniz gerektiğini bilmiyorsanız varsayılan değeri değiştirmemenizi öneririz.

Bazı programlar — Örneğin, sanal cihaz sürücüleri — bu varsayılan yığın büyüme mekanizmasını gerektirmez. Bu gibi durumlarda, yığın araştırmaları gerekli değildir ve her bir işlevden daha büyük bir *değere ayarlayarak derleyicinin* bunları oluşturmasını durdurabilirsiniz.

**/GS0** , yerel değişkenler için depolama gerektiren her işlev çağrısı için yığın araştırmaları başlatır. Bu, performansa olumsuz bir etkiye sahip olabilir.

X64 hedefleri için, **/GS** seçeneği bir *Boyut* bağımsız değişkeni olmadan belirtilmişse, **/GS0** ile aynıdır. *Boyut* bağımsız değişkeni 1 ile 9 arasında ise, uyarı D9014 yayılır ve bu efekt **/GS0** belirtilerek aynı olur.

X86, ARM ve ARM64 hedefleri için, *Boyut* bağımsız değişkeni olmayan **/GS** seçeneği **/Gs4096** ile aynıdır. *Boyut* bağımsız değişkeni 1 ile 9 arasında ise, uyarı D9014 yayılır ve etki, **/Gs4096** belirtilerek aynı olur.

Tüm hedefler için, 10 ile 2147485647 arasındaki bir *Boyut* bağımsız değişkeni, eşiği belirtilen değerde ayarlar. 2147485648 veya üzeri bir *Boyut* , önemli hata C1049 neden olur.

[Check_stack](../../preprocessor/check-stack.md) yönergesini kullanarak yığın araştırmalarını açabilir veya kapatabilirsiniz. **/GS** ve `check_stack` pragma 'ın standart C Kitaplığı yordamları üzerinde hiçbir etkisi yoktur; yalnızca derleme yaptığınız işlevleri etkiler.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **/GS** derleyici seçeneğini ve **ek seçeneklere** isteğe bağlı bir boyut girin. Değişikliklerinizi kaydetmek için **Tamam ' ı** veya **Uygula** ' yı seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
