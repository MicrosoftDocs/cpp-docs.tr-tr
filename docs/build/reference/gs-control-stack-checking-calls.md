---
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
ms.openlocfilehash: 52e203380045c3e23b04950cb241176f10321c2b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50646487"
---
# <a name="gs-control-stack-checking-calls"></a>/Gs (Denetim Yığını Denetim Çağrıları)

Yığın yoklamalarını eşiği denetler.

## <a name="syntax"></a>Sözdizimi

> **/GS**[*boyutu*]

## <a name="arguments"></a>Arguments

*Boyutu*<br/>
(İsteğe bağlı) Yerel değişkenler yığın araştırmaları önce kaplayabilir bayt sayısı başlatılır. Arasında boşluk izin **/Gs** ve *boyutu*.

## <a name="remarks"></a>Açıklamalar

A *yığın araştırma* bir işlev çağrısı başında derleyicinin eklediği kod oluşan bir dizidir. Başlatıldığında, bir yığın araştırma benignly işlevin yerel değişkenler depolamak için gereken alan miktarı tarafından belleğe ulaşır. Bu, işletim sisteminin şeffaf bir şekilde işlev kalan çalışmadan önce gerekirse ek yığın bellekte sayfa neden olur.

Varsayılan olarak, derleyici bir işlev yığın alanı birden fazla sayfa gerektirdiğinde yığın araştırma başlatan kodu oluşturur. Bu derleyici seçeneğine eşdeğerdir **/Gs4096** için x86, x 64, ARM ve ARM64 platformlar. Bu değer, bir uygulama ve Windows Bellek Yöneticisi için program yığınına çalışma zamanında dinamik olarak kaydedilen bellek miktarını artırmak sağlar.

> [!NOTE]
> Varsayılan değer olan **/Gs4096** program yığınına çalışma zamanında doğru bir şekilde ulaşması, Windows için uygulamalar sağlar. Tam olarak neden, bunu değiştirmeniz gerekir bilmiyorsanız varsayılan değer değiştirmemenizi öneririz.

Bazı programlar — Örneğin, sanal cihaz sürücüleri — bu varsayılan yığın büyüme mekanizması gerektirmez. Bu gibi durumlarda, yığın yoklamalarını gerekli değildir ve derleyicinin bunları oluşturuluyor ayarlanarak durdurabilirsiniz *boyutu* herhangi bir işlev için yerel değişken depolama gerektirecek boyutundan daha büyük bir değer.

**/ Gs0** yığın yoklamalarını yerel değişkenler için depolama gerektiren her işlev çağrısının başlatır. Bu, performansı üzerinde olumsuz bir etkiye sahip olabilir.

X64 için hedefler **/Gs** seçeneği olmadan belirtilmiş bir *boyutu* bağımsız olduğu aynı **/Gs0**. Varsa *boyutu* bağımsız değişken 1-9, uyarı D9014 yayılan, ve etkisi belirtmekle aynı **/Gs0**.

X86, ARM, için ve ARM64 hedefleri **/Gs** seçeneği olmadan bir *boyutu* bağımsız değişkeni ile aynı olduğu **/Gs4096**. Varsa *boyutu* bağımsız değişken 1-9, uyarı D9014 yayılan, ve etkisi belirtmekle aynı **/Gs4096**.

Tüm hedefler için bir *boyutu* 2147485647 ile 10 arasındaki bağımsız değişkeni belirtilen değeri eşik ayarlar. A *boyutu* 2147485648 veya büyük neden önemli hata C1049.

Kullanarak, yığın yoklamalarını açıp kapatabilirsiniz [check_stack](../../preprocessor/check-stack.md) yönergesi. **/GS** ve `check_stack` pragma sahip standart C Kitaplığı yordamları etkilemez; bunlar yalnızca derleme işlevleri etkiler.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Girin **/Gs** derleyici seçeneği ve isteğe bağlı bir boyut **ek seçenekler**. Seçin **Tamam** veya **Uygula** yaptığınız değişiklikleri kaydedin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)