---
title: ATL kodlama başvurusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- encoding
- encoding, functions
ms.assetid: 82d4fdf3-3c4a-4fe2-b297-8ffb4714406f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1d8cbb23c390a47b1bbfb7b1a78b327f07b06869
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358634"
---
# <a name="atl-encoding-reference"></a>ATL Kodlama Başvurusu
Ortak Internet standartları uuencode, onaltılık gibi bir dizi ve UTF8 Kodlaması atlenc.h içinde bulunan kodu tarafından desteklenir.  
  
### <a name="functions"></a>İşlevler  
  
|||  
|-|-|  
|[AtlGetHexValue](reference/atl-text-encoding-functions.md#atlgethexvalue)|Onaltılık basamağın sayısal değerini almak için bu işlevi çağırın.|  
|[AtlHexDecode](reference/atl-text-encoding-functions.md#atlhexdecode)|Onaltılık metin olarak gibi önceki çağrısıyla kodlandıktan veri dizesi kodunu çözer [AtlHexEncode](reference/atl-text-encoding-functions.md#atlhexencode).|  
|[AtlHexDecodeGetRequiredLength](reference/atl-text-encoding-functions.md#atlhexdecodegetrequiredlength)|Belirtilen uzunlukta onaltılık kodlanmış bir dizeden çözülmüş verileri içerebilen bir arabelleğin bayt cinsinden boyutunu almak için bu işlevi çağırın.|  
|[AtlHexEncode](reference/atl-text-encoding-functions.md#atlhexencode)|Herhangi bir veriyi onaltılık bir metin dizesi olarak kodlamak için bu işlevi çağırın.|  
|[AtlHexEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#atlhexencodegetrequiredlength)|Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.|  
|[AtlUnicodeToUTF8](reference/atl-text-encoding-functions.md#atlunicodetoutf8)|Unicode dizesini UTF-8'e dönüştürmek için bu işlevi çağırın.|  
|[BEncode](reference/atl-text-encoding-functions.md#bencode)|Bazı verileri "B" kodlama kullanarak dönüştürmek için bu işlevi çağırın.|  
|[BEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#bencodegetrequiredlength)|Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.|  
|[EscapeXML](reference/atl-text-encoding-functions.md#escapexml)|XML'de kullanılması güvenli olmayan karakterleri güvenli eşdeğerlerine dönüştürmek için bu işlevi çağırın.|  
|[GetExtendedChars](reference/atl-text-encoding-functions.md#getextendedchars)|Bir dizede genişletilmiş karakter sayısını almak için bu işlevi çağırın.|  
|[IsExtendedChar](reference/atl-text-encoding-functions.md#isextendedchar)|Belirli bir karakterin genişletilmiş bir karakter (32 den küçük, 126'dan büyük ve sekme, satır besleme veya satır başı değil) olup olmadığını öğrenmek için bu işlevi çağırın.|  
|[QEncode](reference/atl-text-encoding-functions.md#qencode)|Bazı verileri "Q" kodlama kullanarak dönüştürmek için bu işlevi çağırın.|  
|[QEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#qencodegetrequiredlength)|Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.|  
|[QPDecode](reference/atl-text-encoding-functions.md#qpdecode)|Tırnak içine alınmış-yazdırılabilir biçiminde gibi önceki çağrısıyla kodlandıktan veri dizesi kodunu çözer [QPEncode](reference/atl-text-encoding-functions.md#qpencode).|  
|[QPDecodeGetRequiredLength](reference/atl-text-encoding-functions.md#qpdecodegetrequiredlength)|Belirtilen uzunlukta sınırlandırılmış yazdırılabilir biçimde kodlanmış bir dizeden çözülmüş verileri içerebilen bir arabelleğin bayt cinsinden boyutunu almak için bu işlevi çağırın.|  
|[QPEncode](reference/atl-text-encoding-functions.md#qpencode)|Bazı verileri sınırlandırılmış yazdırılabilir biçimde kodlamak için bu işlevi çağırın.|  
|[QPEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#qpencodegetrequiredlength)|Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.|  
|[UUDecode](reference/atl-text-encoding-functions.md#uudecode)|Uuencoded gibi önceki bir çağrı tarafından kaldırıldı veri dizesi kodunu çözer [UUEncode](reference/atl-text-encoding-functions.md#uuencode).|  
|[UUDecodeGetRequiredLength](reference/atl-text-encoding-functions.md#uudecodegetrequiredlength)|Belirtilen uzunlukta uuencoded olarak kodlanmış bir dizeden çözülmüş verileri içerebilen bir arabelleğin bayt cinsinden boyutunu almak için bu işlevi çağırın.|  
|[UUEncode](reference/atl-text-encoding-functions.md#uuencode)|Bazı verileri uuencode olarak kodlamak için bu işlevi çağırın.|  
|[UUEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#uuencodegetrequiredlength)|Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../atl/active-template-library-atl-concepts.md)   
 [ATL COM Masaüstü Bileşenleri](../atl/atl-com-desktop-components.md)

