---
title: Masz Işleçleri başvurusu
ms.date: 07/15/2020
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), operators reference
- operators [MASM]
ms.assetid: c069cab7-d6b0-4f82-a6ce-0ca3fc7e6428
ms.openlocfilehash: c29b173a1dcf29c297e41f136044599fbd5218a5
ms.sourcegitcommit: e15b46ea7888dbdd7e0bb47da76aeed680c3c1f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/17/2020
ms.locfileid: "86446469"
---
# <a name="masm-operators-reference"></a>Masz Işleçleri başvurusu

## <a name="arithmetic"></a>Tiğinin

:::row:::
   :::column span="":::
      [`*`Bilirsiniz](operator-multiply.md)<br/>[`+`ekleyemiyorum](operator-add.md)<br/>[`-`(çıkart veya Negate)](operator-subtract-2.md)
   :::column-end:::
   :::column span="":::
      [`.`alanla](operator-dot.md)<br/>[`/`sayısına](operator-subtract-1.md)
   :::column-end:::
   :::column span="":::
      [`[]`indeks](operator-brackets.md)<br/>[`MOD`geri kalanında](operator-mod.md)
   :::column-end:::
:::row-end:::

## <a name="control-flow"></a>Denetim Akışı

:::row:::
   :::column span="":::
      [`!`(çalışma zamanı mantıksal değil)](operator-logical-not-masm-run-time.md)<br/>[`!=`(çalışma zamanı eşit değildir)](operator-not-equal-masm.md)<br/>[`||`(çalışma zamanı mantıksal veya)](operator-logical-or.md)<br/>[`&&`(çalışma zamanı mantıksal ve)](operator-logical-and-masm-run-time.md)<br/>[`<`(çalışma zamanı şundan küçüktür)](operator-less-than-masm-run-time.md)
   :::column-end:::
   :::column span="":::
      [`<=`(çalışma zamanı daha az veya eşit)](operator-less-or-equal-masm-run-time.md)<br/>[`==`(çalışma zamanı eşittir)](operator-equal-masm-run-time.md)<br/>[`>`(çalışma zamanı büyüktür)](operator-greater-than-masm-run-time.md)<br/>[`>=`(çalışma zamanı daha büyük veya eşit)](operator-greater-or-equal-masm-run-time.md)<br/>[`&`(çalışma zamanı bit düzeyinde and)](operator-bitwise-and.md)
   :::column-end:::
   :::column span="":::
      [`CARRY?`(çalışma zamanı testi testi)](operator-carry-q.md)<br/>[`OVERFLOW?`(çalışma zamanı taşması testi)](operator-overflow-q.md)<br/>[`PARITY?`(çalışma zamanı eşlik testi)](operator-parity-q.md)<br/>[`SIGN?`(çalışma zamanı imza testi)](operator-sign-q.md)<br/>[`ZERO?`(çalışma zamanı sıfır testi)](operator-zero-q.md)
   :::column-end:::
:::row-end:::

## <a name="logical-and-shift"></a>Mantıksal ve kaydırma

:::row:::
   :::column span="":::
      [`AND`(bit düzeyinde and)](operator-and.md)<br/>[`NOT`(bit düzeyinde değil)](operator-not.md)
   :::column-end:::
   :::column span="":::
      [`OR`(bit düzeyinde OR)](operator-or.md)<br/>[`SHL`(bit kaydır sol)](operator-shl.md)
   :::column-end:::
   :::column span="":::
      [`SHR`(Shift bitleri sağ)](operator-shr.md)<br/>[`XOR`(bit düzeyinde dışlamalı veya)](operator-xor.md)
   :::column-end:::
:::row-end:::

## <a name="macro"></a>Makroya

:::row:::
   :::column span="":::
      [`!`(karakter sabit değeri)](operator-logical-not-masm.md)<br/>[`%`(metin olarak işle)](operator-percent.md)
   :::column-end:::
   :::column span="":::
      [`;;`(açıklama olarak işle)](operator-semicolons.md)<br/>[`< >`(bir sabit değer olarak davran)](operator-literal.md)
   :::column-end:::
   :::column span="":::
      [`& &`(alternatif parametre değeri)](operator-logical-and-masm.md)
   :::column-end:::
:::row-end:::

## <a name="miscellaneous"></a>Çeşitli

:::row:::
   :::column span="":::
      [`' '`(dize olarak işle)](operator-single-quote.md)<br/>[`" "`(dize olarak işle)](operator-double-quote.md)<br/>`:`(yerel etiket tanımı)
   :::column-end:::
   :::column span="":::
      `::`(segmenti ve sapmayı Kaydet)<br/>`::`(genel etiket tanımı)
   :::column-end:::
   :::column span="":::
      [`;`(açıklama olarak işle)](operator-semicolon.md)<br/>[`DUP`(yineleme bildirimi)](operator-dup.md)
   :::column-end:::
:::row-end:::

## <a name="record"></a>Kayıt

:::row:::
   :::column span="":::
      [`MASK`(kayıt veya alan bit maskesini al)](operator-mask.md)
   :::column-end:::
   :::column span="2":::
      [`WIDTH`(kayıt veya alan genişliğini al)](operator-width.md)
   :::column-end:::
:::row-end:::

## <a name="relational"></a>İlişkisel

:::row:::
   :::column span="":::
      [`EQ`sıfıra](operator-eq.md)<br/>[`GE`(büyük veya eşittir)](operator-ge.md)
   :::column-end:::
   :::column span="":::
      [`GT`(büyüktür)](operator-gt.md)<br/>[`LE`(Less veya eşittir)](operator-le.md)
   :::column-end:::
   :::column span="":::
      [`LT`(küçüktür)](operator-lt.md)<br/>[`NE`(eşit değildir)](operator-ne.md)
   :::column-end:::
:::row-end:::

## <a name="segment"></a>Segment

:::row:::
   :::column span="":::
      [`:`(kesim geçersiz kılma)](operator-colon.md)<br/>`::`(segmenti ve sapmayı Kaydet)<br/>[`IMAGEREL`(görüntü göreli boşluğu)](operator-imagerel.md)
   :::column-end:::
   :::column span="":::
      [`LROFFSET`(yükleyici tarafından çözümlenen fark)](operator-lroffset.md)<br/>[`OFFSET`(kesim göreli kayması)](operator-offset.md)
   :::column-end:::
   :::column span="":::
      [`SECTIONREL`(Bölüm göreli boşluğu)](operator-sectionrel.md)<br/>[`SEG`(segmenti al)](operator-seg.md)
   :::column-end:::
:::row-end:::

## <a name="type"></a>Tür

:::row:::
   :::column span="":::
      [`HIGH`(yüksek 8 bit en düşük 16 bit)](operator-high.md)<br/>[`HIGH32`(yüksek 32 bit 64 bit)](operator-high32.md)<br/>[`HIGHWORD`(yüksek 16 bit en düşük 32 bit)](operator-highword.md)<br/>[`LENGTH`(dizideki öğelerin sayısı)](operator-length.md)<br/>[`LENGTHOF`(dizideki öğelerin sayısı)](operator-lengthof.md)<br/>[`LOW`(düşük 8 bit)](operator-low.md)
   :::column-end:::
   :::column span="":::
      [`LOW32`(düşük 32 bit)](operator-low32.md)<br/>[`LOWWORD`(düşük 16 bit)](operator-lowword.md)<br/>[`OPATTR`(bağımsız değişken türü bilgisi al)](operator-opattr.md)<br/>[`PTR`(tür işaretçisi veya türü)](operator-ptr.md)<br/>[`SHORT`(kısa etiket türünü işaretle)](operator-short.md)
   :::column-end:::
   :::column span="":::
      [`SIZE`(türün veya değişkenin boyutu)](operator-size.md)<br/>[`SIZEOF`(türün veya değişkenin boyutu)](operator-sizeof.md)<br/>[`THIS`(geçerli konum)](operator-this.md)<br/>[`TYPE`(ifade türünü al)](operator-type.md)<br/>[`.TYPE`(bağımsız değişken türü bilgisi al)](operator-dot-type.md)
   :::column-end:::
:::row-end:::

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Macro Assembler başvurusu](microsoft-macro-assembler-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
