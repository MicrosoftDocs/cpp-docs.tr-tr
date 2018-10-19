---
title: İşleçler başvurusu MASM | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), operators reference
- operators [MASM]
ms.assetid: c069cab7-d6b0-4f82-a6ce-0ca3fc7e6428
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5c9f5beb0e3525de6df88e44248410810502962e
ms.sourcegitcommit: 4cbde5d164d681204c4011dc95a921d75292f423
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2018
ms.locfileid: "49459159"
---
# <a name="masm-operators-reference"></a>MASM işleçler başvurusu

## <a name="arithmetic"></a>Aritmetik

||||
|-|-|-|
|[* (Çarp)](operator-multiply.md)|[+ (Ekle)](operator-add.md)|[-(veya negate Çıkart)](operator-subtract-2.md)|
|[. (alan)](operator-dot.md)|[/ (bölme)](operator-subtract-1.md)|[&#91;&#93;(dizin)](operator-brackets.md)|
|[MOD (kalanını)](operator-mod.md)|||

## <a name="control-flow"></a>Denetim Akışı

||||
|-|-|-|
|[\! (çalışma zamanı mantıksal değil)](operator-logical-not-masm-run-time.md)|[\!(çalışma zamanı eşit değil) =](operator-not-equal-masm.md)|[&#124;&#124;(çalışma zamanı mantıksal veya)](operator-logical-or.md)|
|[& & (çalışma zamanı mantıksal ve)](operator-logical-and-masm-run-time.md)|[< (çalışma zamanı küçüktür)](operator-less-than-masm-run-time.md)|[\<(çalışma zamanı küçük veya buna eşit) =](operator-less-or-equal-masm-run-time.md)|
|[== (çalışma zamanı eşit)](operator-equal-masm-run-time.md)|[> (büyüktür çalışma zamanı)](operator-greater-than-masm-run-time.md)|[> = (çalışma zamanı büyük veya buna eşit)](operator-greater-or-equal-masm-run-time.md)|
|[& (bit çalışma zamanı ve)](operator-bitwise-and.md)|||
|[CARRY? (çalışma zamanı taşıma test)](operator-carry-q.md)|[OVERFLOW? (çalışma zamanı taşma test)](operator-overflow-q.md)|[EŞLİK? (çalışma zamanı eşlik test)](operator-parity-q.md)|
|[OTURUM? (çalışma zamanı oturum test)](operator-sign-q.md)|[ZERO? (çalışma zamanı sıfır test)](operator-zero-q.md)||

## <a name="logical-and-shift"></a>Mantıksal and -Shift ile

||||
|-|-|-|
|[VE (bit düzeyinde ve)](operator-and.md)|[YOK (bit düzeyinde değil)](operator-not.md)|[OR (Bitsel veya)](operator-or.md)|
|[SHL (sol shift BITS)](operator-shl.md)|[SHR (sağ shift BITS)](operator-shr.md)|[XOR (bit düzeyinde özel veya)](operator-xor.md)|

## <a name="macro"></a>Makrosu

||||
|-|-|-|
|[\! (karakter sabit değeri)](operator-logical-not-masm.md)|[% (metin olarak davranma)](operator-percent.md)||
|[;; (açıklama olarak işle)](operator-semicolons.md)|[&lt; &gt; (bir değişmez değer olarak işle)](operator-literal.md)|[& & (parametre değeri yerine)](operator-logical-and-masm.md)|

## <a name="miscellaneous"></a>Çeşitli

||||
|-|-|-|
|[' ' (dize olarak işle)](operator-single-quote.md)|["" (dize olarak işle)](operator-double-quote.md)||
|: (yerel etiket tanımı)|:: (segment ve uzaklık Kaydet)|:: (genel etiket tanımı)|
|[; (açıklama olarak işle)](operator-semicolon.md)|[DUP (yineleme bildirim)](operator-dup.md)||

## <a name="record"></a>Kayıt

|||
|-|-|
|[MASKESİ (kayıt veya alan bit maskesi alma)](operator-mask.md)|[Genişlik (kayıt veya alan genişliği alma)](operator-width.md)|

## <a name="relational"></a>İlişkisel

||||
|-|-|-|
|[EQ (eşittir)](operator-eq.md)|[GE (büyük veya buna eşit)](operator-ge.md)|[GT (büyüktür)](operator-gt.md)|
|[LE (daha az veya buna eşit)](operator-le.md)|[LT (küçüktür)](operator-lt.md)|[NE (eşit değildir)](operator-ne.md)|

## <a name="segment"></a>Segment

|||
|-|-|
|[: (geçersiz kılma segmentlere ayırın.)](operator-colon.md)|:: (segment ve uzaklık Kaydet)|
|[IMAGEREL (görüntü göreli konum)](operator-imagerel.md)|[LROFFSET (Yükleyici çözümlenen uzaklık)](operator-lroffset.md)|
|[UZAKLIK (göreli segment uzaklığı)](operator-offset.md)|[SECTIONREL (bölüm göreli uzaklık)](operator-sectionrel.md)|
|[SEG (get kesim)](operator-seg.md)||

## <a name="type"></a>Tür

||||
|-|-|-|
|[Yüksek (en düşük 16 bit yüksek 8 bit)](operator-high.md)|[Hıgh32 (64 bit yüksek 32 bit)](operator-high32.md)|[HIGHWORD (en düşük 32 bit yüksek 16 bit)](operator-highword.md)|
|[UZUNLUK (dizideki öğelerin sayısı)](operator-length.md)|[LENGTHOF (dizideki öğelerin sayısı)](operator-lengthof.md)|[DÜŞÜK (düşük 8 bit)](operator-low.md)|
|[LOW32 (32 bit düşük)](operator-low32.md)|[LOWWORD (düşük 16 bit)](operator-lowword.md)|[OPATTR (get bağımsız değişken türü bilgileri)](operator-opattr.md)|
|[PTR (işaretçi veya türü olarak)](operator-ptr.md)|[SHORT (kısa etiket türü)](operator-short.md)|[Boyut (tür veya değişken boyutu)](operator-size.md)|
|[SIZEOF (tür veya değişken boyutu)](operator-sizeof.md)|[Bu (geçerli konumu)](operator-this.md)|[TÜRÜ (get ifade türü)](operator-type.md)|
|[. TÜRÜ (get bağımsız değişken türü bilgileri)](operator-dot-type.md)|||

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Macro Assembler Başvurusu](microsoft-macro-assembler-reference.md)<br/>
