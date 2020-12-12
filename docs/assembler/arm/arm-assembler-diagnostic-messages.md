---
description: 'Daha fazla bilgi edinin: ARM Assembler tanılama iletileri'
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
ms.openlocfilehash: 91e4640c161cbb58522c3680ae5decdb4cc1e992
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118205"
---
# <a name="arm-assembler-diagnostic-messages"></a>ARM Assembler tanılama iletileri

Microsoft ARM Assembler (*armasd*), karşılaştığı tanılama uyarılarını ve hatalarını yayar. Bu makalede en sık karşılaşılan iletiler açıklanır.

## <a name="syntax"></a>Syntax

> <em>dosya adı</em>**(**<em>satır numarası</em>**):** \[ **hata** | **uyarısı**] **bir**<em>sayı</em>**:** *ileti*

## <a name="diagnostic-messages---errors"></a>Tanılama iletileri-hatalar

> A2193: Bu yönerge öngörülemeyen davranışları oluşturuyor

ARM mimarisi, bu yönerge yürütüldüğünde ne olacağını garanti edemez.  Bu yönergenin iyi tanımlanmış formları hakkında daha fazla bilgi için [ARM mimari başvurusu kılavuzuna](https://go.microsoft.com/fwlink/p/?linkid=246464)bakın.

```asm
    ADD r0, r8, pc         ; A2193: this instruction generates unpredictable behavior
```

> A2196: yönerge 16 bit ile kodlanamaz

Belirtilen yönerge 16 bit Thumb yönergesi olarak kodlanamaz.  32 bitlik bir yönerge belirtin veya hedef etiketi 16 bit yönerge aralığına getirmek için kodu yeniden düzenleyin.

Derleyici, bir dalı 16 bit içinde kodlayabilir ve 32 bitlik bir dal kodlenebilir olsa bile bu hatayla başarısız olur. `.W`Dalı açıkça 32 bit olarak işaretlemek için belirticisi kullanarak bu sorunu çözebilirsiniz.

```asm
    ADD.N r0, r1, r2      ; A2196: instruction cannot be encoded in 16 bits

    B.W label             ; OK
    B.N label             ; A2196: instruction cannot be encoded in 16 bits
    SPACE 10000
label
```

> A2202: THUMB bölgesinde önceden sürekli yönerge sözdizimine izin verilmiyor

Thumb kodu Birleşik assembler dili (sürekli) söz dizimini kullanmalıdır.  Eski sözdizimi artık kabul edilmez

```asm
    ADDEQS r0, r1         ; A2202: Pre-UAL instruction syntax not allowed in THUMB region
    ADDSEQ r0, r1         ; OK
```

> A2513: döndürme çift olmalıdır

ARM modunda, sabitleri belirtmek için alternatif bir sözdizimi vardır.  Yazmak yerine, `#<const>` `#<byte>,#<rot>` değeri sağdan doğru döndürerek elde edilen sabit değeri temsil eden yazabilirsiniz `<byte>` `<rot>` .  Bu söz dizimini kullandığınızda değeri bile yapmanız gerekir `<rot>` .

```asm
    MOV r0, #4, #2       ; OK
    MOV r0, #4, #1       ; A2513: Rotation must be even
```

> A2557: geri yazılacak hatalı sayıda bayt

NEON yapısı yükleme ve depolama yönergeleri ( `VLDn` ,) üzerinde `VSTn` , temel kayda geri yazma belirtmek için alternatif bir sözdizimi vardır.  Adresten sonra bir ünlem işareti (!) koymak yerine, temel kayda eklenecek sapmayı gösteren bir anında değer belirtebilirsiniz.  Bu söz dizimini kullanırsanız, yönerge tarafından yüklenen veya depolanan bayt sayısını tam olarak belirtmeniz gerekir.

```asm
    VLD1.8 {d0-d3}, [r0]!         ; OK
    VLD1.8 {d0-d3}, [r0], #32     ; OK
    VLD1.8 {d0-d3}, [r0], #100    ; A2557: Incorrect number of bytes to write back
```

## <a name="diagnostic-messages---warnings"></a>Tanılama iletileri-uyarılar

> A4228: hizalama değeri alan hizalamasını aşıyor; hizalama garanti edilmez

Bir yönergede belirtilen hizalama `ALIGN` kapsayan hizalamadan daha büyük `AREA` .  Sonuç olarak, çevirici, yönergenin kabul olacağını garanti edemez `ALIGN` .

Bunu yapmak için, `AREA` yönergede `ALIGN` istenen hizalamadan daha büyük veya ona eşit bir öznitelik belirtebilirsiniz.

```asm
AREA |.myarea1|
ALIGN 8           ; A4228: Alignment value exceeds AREA alignment; alignment not guaranteed

AREA |.myarea2|,ALIGN=3
ALIGN 8           ; OK
```

> A4508: Bu döndürülmüş sabitin kullanımı kullanım dışıdır

ARM modunda, sabitleri belirtmek için alternatif bir sözdizimi vardır.  Yazmak yerine, `#<const>` `#<byte>,#<rot>` değeri sağdan doğru döndürerek elde edilen sabit değeri temsil eden yazabilirsiniz `<byte>` `<rot>` .  Bazı bağlamlarda ARM bu döndürülmüş sabitlerin kullanımını kullanımdan kaldırılmıştır. Bu durumlarda, `#<const>` bunun yerine temel sözdizimini kullanın.

```asm
    ANDS r0, r0, #1                ; OK
    ANDS r0, r0, #4, #2            ; A4508: Use of this rotated constant is deprecated
```

> A4509: Bu koşullu yönerge formu kullanım dışıdır

Bu koşullu yönerge formu, ARMv8 mimarisinde ARM tarafından kullanımdan kaldırılmıştır. Koşullu dalları kullanmak için kodu değiştirmenizi öneririz. Hangi koşullu yönergelerin hala desteklendiğini görmek için [ARM mimari başvurusu kılavuzuna](https://go.microsoft.com/fwlink/p/?linkid=246464)bakın.

Bu uyarı, **-oldit** komut satırı anahtarı kullanıldığında yayınlanmaz.

```asm
    ADDEQ r0, r1, r8              ; A4509: This form of conditional instruction is deprecated
```

## <a name="see-also"></a>Ayrıca bkz.

[ARM Assembler Command-Line başvurusu](../../assembler/arm/arm-assembler-command-line-reference.md)<br/>
[ARM Assembler yönergeleri](../../assembler/arm/arm-assembler-directives.md)<br/>
