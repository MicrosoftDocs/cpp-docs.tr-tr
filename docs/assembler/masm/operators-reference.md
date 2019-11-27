---
title: Masz Işleçleri başvurusu
ms.date: 08/30/2018
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), operators reference
- operators [MASM]
ms.assetid: c069cab7-d6b0-4f82-a6ce-0ca3fc7e6428
ms.openlocfilehash: 5295307ad668b76e5ff39882ce2613f2042f914a
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74395209"
---
# <a name="masm-operators-reference"></a>Masz Işleçleri başvurusu

## <a name="arithmetic"></a>Aritmetik

||||
|-|-|-|
|[* (çarp)](operator-multiply.md)|[+ (Ekle)](operator-add.md)|[-(çıkart veya Negate)](operator-subtract-2.md)|
|[. alanla](operator-dot.md)|[/(Böl)](operator-subtract-1.md)|[&#91;&#93;indeks](operator-brackets.md)|
|[MOD (kalan)](operator-mod.md)|||

## <a name="control-flow"></a>Denetim Akışı

||||
|-|-|-|
|[\! (çalışma zamanı mantıksal değil)](operator-logical-not-masm-run-time.md)|[\!= (çalışma zamanı eşit değildir)](operator-not-equal-masm.md)|[&#124;&#124;(çalışma zamanı mantıksal veya)](operator-logical-or.md)|
|[& & (çalışma zamanı mantıksal ve)](operator-logical-and-masm-run-time.md)|[< (çalışma zamanı şundan küçüktür)](operator-less-than-masm-run-time.md)|[\<= (çalışma zamanı daha az veya eşittir)](operator-less-or-equal-masm-run-time.md)|
|[= = (çalışma zamanı eşittir)](operator-equal-masm-run-time.md)|[> (çalışma zamanı büyüktür)](operator-greater-than-masm-run-time.md)|[> = (çalışma zamanı büyük veya eşittir)](operator-greater-or-equal-masm-run-time.md)|
|[& (çalışma zamanı bit düzeyinde and)](operator-bitwise-and.md)|||
|[Sürdür? (çalışma zamanı testi testi)](operator-carry-q.md)|[TAŞMA? (çalışma zamanı taşması testi)](operator-overflow-q.md)|[EŞLIK? (çalışma zamanı eşlik testi)](operator-parity-q.md)|
|[IMZALAYABILIRSINIZ? (çalışma zamanı imza testi)](operator-sign-q.md)|[SıFıRLAMA? (çalışma zamanı sıfır testi)](operator-zero-q.md)||

## <a name="logical-and-shift"></a>Mantıksal ve kaydırma

||||
|-|-|-|
|[VE (bit düzeyinde and)](operator-and.md)|[NOT (bit düzeyinde değil)](operator-not.md)|[OR (bit düzeyinde OR)](operator-or.md)|
|[SHL (vardiya bitleri sol)](operator-shl.md)|[SHR (Shift bitleri sağ)](operator-shr.md)|[XOR (bit düzeyinde dışlamalı veya)](operator-xor.md)|

## <a name="macro"></a>Makrosu

||||
|-|-|-|
|[\! (karakter sabit değeri)](operator-logical-not-masm.md)|[% (metin olarak davran)](operator-percent.md)||
|[;; (açıklama olarak işle)](operator-semicolons.md)|[&lt; &gt; (tek bir sabit değer olarak işle)](operator-literal.md)|[& & (değiştirme parametre değeri)](operator-logical-and-masm.md)|

## <a name="miscellaneous"></a>Çeşitli

||||
|-|-|-|
|[' ' (dize olarak değerlendir)](operator-single-quote.md)|["" (dize olarak değerlendir)](operator-double-quote.md)||
|: (yerel etiket tanımı)|:: (segmenti ve sapmayı Kaydet)|:: (genel etiket tanımı)|
|[; (açıklama olarak işle)](operator-semicolon.md)|[DUP (yineleme bildirimi)](operator-dup.md)||

## <a name="record"></a>Kayıt

|||
|-|-|
|[MASKE (kayıt veya alan bit maskesini al)](operator-mask.md)|[GENIŞLIK (kayıt veya alan genişliğini al)](operator-width.md)|

## <a name="relational"></a>İlişkisel

||||
|-|-|-|
|[EQ (eşittir)](operator-eq.md)|[GE (büyük veya eşittir)](operator-ge.md)|[GT (büyüktür)](operator-gt.md)|
|[LE (daha az veya eşit)](operator-le.md)|[LT (küçüktür)](operator-lt.md)|[NE (eşit değildir)](operator-ne.md)|

## <a name="segment"></a>Deki

|||
|-|-|
|[: (kesim geçersiz kılma)](operator-colon.md)|:: (segmenti ve sapmayı Kaydet)|
|[IMAGEREL (görüntü göreli boşluğu)](operator-imagerel.md)|[LROFFSET (yükleyici tarafından çözümlenen fark)](operator-lroffset.md)|
|[FARK (kesim göreli boşluğu)](operator-offset.md)|[SECTIONREL (Bölüm göreli boşluğu)](operator-sectionrel.md)|
|[SEG (segmenti al)](operator-seg.md)||

## <a name="type"></a>Type

||||
|-|-|-|
|[YÜKSEK (yüksek 8 bit en düşük 16 bit)](operator-high.md)|[HıGH32 (yüksek 32 bit 64 bit)](operator-high32.md)|[HIGHWORD (yüksek 16 bit en düşük 32 bit)](operator-highword.md)|
|[Uzunluk (dizideki öğelerin sayısı)](operator-length.md)|[LENGTHOF (dizideki öğe sayısı)](operator-lengthof.md)|[DÜŞÜK (düşük 8 bit)](operator-low.md)|
|[LOW32 (düşük 32 bit)](operator-low32.md)|[LOWWORD (düşük 16 bit)](operator-lowword.md)|[OPATTR (bağımsız değişken türü bilgisi al)](operator-opattr.md)|
|[PTR (türe göre veya tür işaretçisi)](operator-ptr.md)|[SHORT (kısa etiket türünü işaretle)](operator-short.md)|[Boyut (tür veya değişken boyutu)](operator-size.md)|
|[SIZEOF (tür veya değişken boyutu)](operator-sizeof.md)|[Bu (geçerli konum)](operator-this.md)|[TÜR (Get ifadesi Type)](operator-type.md)|
|[. TÜR (bağımsız değişken türü bilgisi al)](operator-dot-type.md)|||

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Macro Assembler Başvurusu](microsoft-macro-assembler-reference.md)<br/>
