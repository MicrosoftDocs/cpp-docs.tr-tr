---
title: Yolları Kurallarda Ara
ms.date: 11/04/2016
helpviewer_keywords:
- search paths in NMAKE inference rules
- inference rules in NMAKE
- rules, inference
ms.assetid: 38feded6-536d-425d-bf40-fff3173a5506
ms.openlocfilehash: 26b02fa76920f0d0ff380dacd5aa76cfe8e92c79
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649975"
---
# <a name="search-paths-in-rules"></a>Yolları Kurallarda Ara

```
{frompath}.fromext{topath}.toext:
   commands
```

## <a name="remarks"></a>Açıklamalar

Bağımlılığı tam olarak belirtilen yollar çıkarım kuralı yolları eşleşiyorsa çıkarım kuralı bir bağımlılık için geçerlidir. Belirtin bağımlı öğenin dizininde *frompath* ve hedef dizinde *topath*; boşluk izin verilir. Her bir uzantı için yalnızca bir yol belirtin. Bir uzantı bir yolu diğer bir yolu gerektirir. Geçerli dizini belirlemek için bir nokta (.) ya da boş küme ayraçları ({}) kullanın. Makrolar temsil edebilir *frompath* ve *topath*; ön işleme sırasında çağrılır.

## <a name="example"></a>Örnek

### <a name="code"></a>Kod

```
{dbi\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUDBI) $<

{ilstore\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<

{misc\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{misc\}.c{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<

{msf\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<

{bsc\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{mre\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{namesrvr\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{src\cvr\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<
```

## <a name="see-also"></a>Ayrıca Bkz.

[Kural Tanımlama](../build/defining-a-rule.md)