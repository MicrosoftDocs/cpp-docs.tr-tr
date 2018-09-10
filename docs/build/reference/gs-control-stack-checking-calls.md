---
title: -Gs (Denetim yığını denetim çağrıları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /GS
dev_langs:
- C++
helpviewer_keywords:
- disabling stack probes
- GS compiler option [C++]
- /GS compiler option [C++]
- stack, stack probes
- stack probes
- -GS compiler option [C++]
- stack checking calls
ms.assetid: 40daed7c-f942-4085-b872-01e12b37729e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c0c6a5af31eaba30af92201a2e2563b67aceed6e
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44104114"
---
# <a name="gs-control-stack-checking-calls"></a>/Gs (Denetim Yığını Denetim Çağrıları)
Yığın araştırmalarını denetler.

## <a name="syntax"></a>Sözdizimi

```  
/Gs[size]
```  

## <a name="arguments"></a>Arguments
*Boyutu*<br/>
(İsteğe bağlı) Yerel değişkenler yığın araştırmaları önce kaplayabilir bayt sayısı başlatılır. Varsa **/Gs** seçeneği olmadan belirtilmiş bir `size` bağımsız değişkeni, belirtmekle aynı olacak **/Gs0**,

## <a name="remarks"></a>Açıklamalar
Bir yığın araştırması, her işlev çağrısını derleyicinin eklediği kod bir dizidir. Başlatıldığında, bir yığın araştırma benignly işlevin yerel değişkenler depolamak için gereken alan miktarı tarafından belleğe ulaşır.

Bir işlev gerektiriyorsa, birden fazla `size` bayt yığın alanı yerel değişkenler için kendi yığın araştırma başlatılır. Varsayılan olarak, derleyici bir işlev yığın alanı birden fazla sayfa gerektirdiğinde yığın araştırma başlatan kodu oluşturur. Bu derleyici seçeneğine eşdeğerdir **/Gs4096** x86 x64 ve ARM platformları için. Bu değer, bir uygulama ve Windows Bellek Yöneticisi için program yığınına çalışma zamanında dinamik olarak kaydedilen bellek miktarını artırmak sağlar.

> [!NOTE]
>  Varsayılan değer olan **/Gs4096** program yığınına çalışma zamanında doğru bir şekilde ulaşması, Windows için uygulamalar sağlar. Tam olarak neden, bunu değiştirmeniz gerekir bilmiyorsanız varsayılan değer değiştirmemenizi öneririz.

Bazı programlar — Örneğin, sanal cihaz sürücüleri — bu varsayılan yığın büyüme mekanizması gerektirmez. Bu gibi durumlarda, yığın yoklamalarını gerekli değildir ve derleyicinin bunları oluşturuluyor ayarlanarak durdurabilirsiniz `size` herhangi bir işlev için yerel değişken depolama gerektirecek boyutundan daha büyük bir değer. Arasında boşluk izin **/Gs** ve `size`.

**/ Gs0** yerel değişkenler için depolama gerektiren her işlev çağrısının yığın araştırmaları etkinleştirir. Bu, performansı üzerinde olumsuz bir etkiye sahip olabilir.

Kullanarak, yığın yoklamalarını açıp kapatabilirsiniz [check_stack](../../preprocessor/check-stack.md). **/GS** ve `check_stack` pragma sahip standart C Kitaplığı yordamları etkilemez; bunlar yalnızca derleme işlevleri etkiler.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1.  Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

2.  Seçin **C/C++** klasör.

3.  Seçin **komut satırı** özellik sayfası.

4.  Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)