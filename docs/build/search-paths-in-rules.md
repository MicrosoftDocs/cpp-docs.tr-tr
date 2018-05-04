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
ms.openlocfilehash: 25127377f20de3cb7c7b55e275692eefbf077067
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="search-paths-in-rules"></a>Yolları Kurallarda Ara
```  
{frompath}.fromext{topath}.toext:  
   commands  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Yalnızca bağımlılığı tam olarak belirtilen yollar çıkarım kuralı yolları eşleşiyorsa çıkarım kuralı için bir bağımlılık geçerlidir. Bağımlı öğenin dizini belirtin *frompath* ve hedef dizinde *topath*; boşluk izin verilir. Her bir uzantı için yalnızca bir yol belirtin. Bir uzantı yola diğer bir yolu gerektirir. Geçerli dizin belirtmek için bir nokta (.) veya boş kaşlı ayraçlar kullanın. Makrolar temsil *frompath* ve *topath*; ön işleme sırasında çağrılır.  
  
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