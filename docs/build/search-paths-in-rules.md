---
title: Yolları kurallarda Ara | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- search paths in NMAKE inference rules
- inference rules in NMAKE
- rules, inference
ms.assetid: 38feded6-536d-425d-bf40-fff3173a5506
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c96ee89367c3ac289dffde9029cb2b5d3cdc3e89
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703982"
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