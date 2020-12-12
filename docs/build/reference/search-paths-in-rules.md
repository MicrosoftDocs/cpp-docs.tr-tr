---
description: 'Hakkında daha fazla bilgi edinin: kurallar içinde arama yolları'
title: Yolları Kurallarda Ara
ms.date: 11/04/2016
helpviewer_keywords:
- search paths in NMAKE inference rules
- inference rules in NMAKE
- rules, inference
ms.assetid: 38feded6-536d-425d-bf40-fff3173a5506
ms.openlocfilehash: bf070fc57907b68eb458b8a5276698282ef30f9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224887"
---
# <a name="search-paths-in-rules"></a>Yolları Kurallarda Ara

```
{frompath}.fromext{topath}.toext:
   commands
```

## <a name="remarks"></a>Açıklamalar

Bir çıkarım kuralı, yalnızca bağımlılıkta belirtilen yollar, çıkarım kuralı yollarıyla tam olarak eşleşiyorsa bir bağımlılık için geçerlidir. Bağımsız olarak, *frompath* ve hedefin dizinini *toPath* içinde belirtin; boşluklara izin verilmez. Her uzantı için yalnızca bir yol belirtin. Bir uzantıdaki yol, diğeri için bir yol gerektirir. Geçerli dizini belirtmek için, nokta (.) veya boş küme ayraçları ({}) kullanın. Makrolar *frompath* ve *toPath*'i temsil edebilir. Bunlar ön işleme sırasında çağırılır.

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

[Kural tanımlama](defining-a-rule.md)
