---
title: Yolları Kurallarda Ara
ms.date: 11/04/2016
helpviewer_keywords:
- search paths in NMAKE inference rules
- inference rules in NMAKE
- rules, inference
ms.assetid: 38feded6-536d-425d-bf40-fff3173a5506
ms.openlocfilehash: eab6e9d32940aaf5729ce82c4e8258a3a3132208
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57824088"
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

## <a name="see-also"></a>Ayrıca bkz.

[Kural Tanımlama](defining-a-rule.md)
