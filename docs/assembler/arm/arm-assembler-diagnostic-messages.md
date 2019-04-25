---
title: ARM Assembler tanılama iletileri
ms.date: 08/30/2018
f1_keywords:
- A2193
- A2196
- A2202
- A2513
- A2557
- A4228
- A4508
- A4509
helpviewer_keywords:
- A2193
- A2196
- A2202
- A2513
- A2557
- A4228
- A4508
- A4509
ms.assetid: 52b38267-6023-4bdc-a0ef-863362f48eec
ms.openlocfilehash: 867ef50065c6ed63a4da6d37523bd5a1f3cbadba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167849"
---
# <a name="arm-assembler-diagnostic-messages"></a>ARM Assembler tanılama iletileri

Microsoft ARM derleyicisi (*armasm*) bu karşılaştığında tanılama uyarıları ve hataları yayar. Bu makalede, en sık karşılaşılan iletilerini açıklar.

## <a name="syntax"></a>Sözdizimi

> <em>filename</em>**(**<em>satır numarası</em>**):** \[ **hata**|**Uyarısı** ] **A**<em>numarası</em>**:** *iletisi*

## <a name="diagnostic-messages---errors"></a>Tanılama iletileri - hata

> A2193: Bu yönergeyi öngörülemeyen davranışlara oluşturur.

ARM mimarisi, bu yönerge yürütme sırasında ne olacağını garanti edemez.  Bu yönerge, iyi tanımlanmış biçimleri hakkında daha fazla ayrıntı için inceleyin [ARM mimarisi Reference Manual](http://go.microsoft.com/fwlink/p/?linkid=246464).

```asm
    ADD r0, r8, pc         ; A2193: this instruction generates unpredictable behavior
```

> A2196: 16 bit kodlanamaz yönerge

Belirtilen yönergeyi 16-bit Thumb yönerge olarak kodlanamaz.  Bir 32-bit yönergesi belirtin veya bir 16 bit yönergesi aralığına hedef etiketi getirmek için kodu yeniden düzenleyin.

Bir 32-bit dal encodable olsa bile derleyici 16 bit bir dalda kodlama ve bu hata ile başarısız deneyebilir. Kullanarak bu sorunu çözebilirsiniz `.W` açıkça dalı 32-bit olarak işaretlemek için tanımlayıcısı.

```asm
    ADD.N r0, r1, r2      ; A2196: instruction cannot be encoded in 16 bits

    B.W label             ; OK
    B.N label             ; A2196: instruction cannot be encoded in 16 bits
    SPACE 10000
label
```

> A2202: Pre-UAL yönerge söz dizimi THUMB bölgede izin verilmiyor

Thumb kodu Unified Çevirici dili (UAL) sözdizimini kullanmanız gerekir.  Eski sözdizimi artık kabul edilir

```asm
    ADDEQS r0, r1         ; A2202: Pre-UAL instruction syntax not allowed in THUMB region
    ADDSEQ r0, r1         ; OK
```

> A2513: Döndürme bile olmalıdır

ARM modunda sabitleri belirtmek için alternatif bir sözdizimi yoktur.  Yazma yerine `#<const>`, yazabileceğiniz `#<byte>,#<rot>`, değeri döndürerek alınan sabit değeri temsil eden `<byte>` sağ tarafından `<rot>`.  Bu sözdizimi kullandığınızda, değerini yapmalısınız `<rot>` bile.

```asm
    MOV r0, #4, #2       ; OK
    MOV r0, #4, #1       ; A2513: Rotation must be even
```

> A2557: Yanlış geri yazılacak bayt sayısı

NEON yapısı yüklemek ve yönergeleri depolamak (`VLDn`, `VSTn`), temel kaydı için geri yazma belirtmek için alternatif bir sözdizimi yoktur.  Ünlem işareti (!), sonra adresi almak yerine temel kasaya eklenecek uzaklığını belirten anında bir değer belirtebilirsiniz.  Bu söz dizimi kullanırsanız, yüklenen ya da yönergesi tarafından depolanan bayt tam sayı belirtmeniz gerekir.

```asm
    VLD1.8 {d0-d3}, [r0]!         ; OK
    VLD1.8 {d0-d3}, [r0], #32     ; OK
    VLD1.8 {d0-d3}, [r0], #100    ; A2557: Incorrect number of bytes to write back
```

## <a name="diagnostic-messages---warnings"></a>Tanılama iletileri - uyarılar

> A4228: Hizalama değeri alanı hizalama aşıyor; yıkıcıları hizalama

Belirtilen hizalama bir `ALIGN` yönergesi kapsayan hizalamasından büyükse `AREA`.  Derleyici, sonuç olarak, garanti edemez `ALIGN` yönergesi kullanılacaktır.

Bu sorunu gidermek için belirtebilirsiniz `AREA` yönergesi bir `ALIGN` istenen hizalama büyüktür veya ona eşit bir öznitelik.

```asm
AREA |.myarea1|
ALIGN 8           ; A4228: Alignment value exceeds AREA alignment; alignment not guaranteed

AREA |.myarea2|,ALIGN=3
ALIGN 8           ; OK
```

> A4508: Döndürülen bu sabitin kullanım dışı

ARM modunda sabitleri belirtmek için alternatif bir sözdizimi yoktur.  Yazma yerine `#<const>`, yazabileceğiniz `#<byte>,#<rot>`, değeri döndürerek alınan sabit değeri temsil eden `<byte>` sağ tarafından `<rot>`.  Bazı bağlamlarda ARM Bu döndürülmüş sabiti kullanımı kullanım dışı. Bu durumda, temel kullanın `#<const>` söz dizimi yerine.

```asm
    ANDS r0, r0, #1                ; OK
    ANDS r0, r0, #4, #2            ; A4508: Use of this rotated constant is deprecated
```

> A4509: Bu formu koşullu yönerge kullanım dışıdır

Bu formu koşullu yönerge ARM ARMv8 mimarisinde tarafından onaylanmaz. Koşullu dalları kullanmak için kodu değiştirmenizi öneririz. Hangi koşullu yönergeleri hala desteklenmektedir görmek için başvurun [ARM mimarisi Reference Manual](http://go.microsoft.com/fwlink/p/?linkid=246464).

Bu uyarı değil ne zaman yayılan **- oldit** komut satırı anahtarı kullanılır.

```asm
    ADDEQ r0, r1, r8              ; A4509: This form of conditional instruction is deprecated
```

## <a name="see-also"></a>Ayrıca bkz.

[ARM Assembler Komut Satırı Başvurusu](../../assembler/arm/arm-assembler-command-line-reference.md)<br/>
[ARM Assembler Yönergeleri](../../assembler/arm/arm-assembler-directives.md)<br/>
