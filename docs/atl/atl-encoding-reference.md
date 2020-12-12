---
description: 'Daha fazla bilgi edinin: ATL kodlama başvurusu'
title: ATL Kodlama Başvurusu
ms.date: 11/04/2016
helpviewer_keywords:
- encoding
- encoding, functions
ms.assetid: 82d4fdf3-3c4a-4fe2-b297-8ffb4714406f
ms.openlocfilehash: 309c4cbf695b5f40e58116c9422f8da481799cbc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148674"
---
# <a name="atl-encoding-reference"></a>ATL Kodlama Başvurusu

UUENCODE, onaltılı ve UTF8 gibi yaygın Internet standartları aralığında kodlama, içinde bulunan kod tarafından desteklenir *`atlenc.h`* .

### <a name="functions"></a>İşlevler

| İşlev | Kullanım örneği |
|--|--|
| [AtlGetHexValue](reference/atl-text-encoding-functions.md#atlgethexvalue) | Onaltılık basamağın sayısal değerini almak için bu işlevi çağırın. |
| [Atlonaltık kodu çözme](reference/atl-text-encoding-functions.md#atlhexdecode) | Bir önceki [Atlonaltıl kodlaması](reference/atl-text-encoding-functions.md#atlhexencode)çağrısıyla gibi onaltılık metin olarak kodlanmış bir veri dizesinin kodunu çözer. |
| [Atlonaltıdecodegetrequiredlength](reference/atl-text-encoding-functions.md#atlhexdecodegetrequiredlength) | Belirtilen uzunlukta onaltılık kodlanmış bir dizeden çözülmüş verileri içerebilen bir arabelleğin bayt cinsinden boyutunu almak için bu işlevi çağırın. |
| [Atlonaltıl kodlama](reference/atl-text-encoding-functions.md#atlhexencode) | Herhangi bir veriyi onaltılık bir metin dizesi olarak kodlamak için bu işlevi çağırın. |
| [Atlonaltıencodegetrequiredlength](reference/atl-text-encoding-functions.md#atlhexencodegetrequiredlength) | Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın. |
| [AtlUnicodeToUTF8](reference/atl-text-encoding-functions.md#atlunicodetoutf8) | Unicode dizesini UTF-8'e dönüştürmek için bu işlevi çağırın. |
| [BEncode](reference/atl-text-encoding-functions.md#bencode) | Bazı verileri "B" kodlama kullanarak dönüştürmek için bu işlevi çağırın. |
| [BEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#bencodegetrequiredlength) | Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın. |
| [Çıkar Exml](reference/atl-text-encoding-functions.md#escapexml) | XML'de kullanılması güvenli olmayan karakterleri güvenli eşdeğerlerine dönüştürmek için bu işlevi çağırın. |
| [Gebir Dedchars](reference/atl-text-encoding-functions.md#getextendedchars) | Bir dizede genişletilmiş karakter sayısını almak için bu işlevi çağırın. |
| [IsExtendedChar](reference/atl-text-encoding-functions.md#isextendedchar) | Belirli bir karakterin genişletilmiş bir karakter olup olmadığını bulmak için bu işlevi çağırın (32 ' dan az, 126 ' den büyük olan ve sekme, satır besleme veya satır başı değil) |
| [QEncode](reference/atl-text-encoding-functions.md#qencode) | Bazı verileri "Q" kodlama kullanarak dönüştürmek için bu işlevi çağırın. |
| [QEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#qencodegetrequiredlength) | Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın. |
| [Qpkodunu çöz](reference/atl-text-encoding-functions.md#qpdecode) | Daha önceki bir [QPEncode](reference/atl-text-encoding-functions.md#qpencode)çağrısıyla gibi tırnaklı yazdırılabilir biçimde kodlanmış bir veri dizesinin kodunu çözer. |
| [QPDecodeGetRequiredLength](reference/atl-text-encoding-functions.md#qpdecodegetrequiredlength) | Belirtilen uzunlukta sınırlandırılmış yazdırılabilir biçimde kodlanmış bir dizeden çözülmüş verileri içerebilen bir arabelleğin bayt cinsinden boyutunu almak için bu işlevi çağırın. |
| [QPEncode](reference/atl-text-encoding-functions.md#qpencode) | Bazı verileri sınırlandırılmış yazdırılabilir biçimde kodlamak için bu işlevi çağırın. |
| [QPEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#qpencodegetrequiredlength) | Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın. |
| [UUDecode](reference/atl-text-encoding-functions.md#uudecode) | Daha önceki [uuencode](reference/atl-text-encoding-functions.md#uuencode)çağrısıyla gibi uuencoded bir veri dizesinin kodunu çözer. |
| [UUDecodeGetRequiredLength](reference/atl-text-encoding-functions.md#uudecodegetrequiredlength) | Belirtilen uzunlukta uuencoded olarak kodlanmış bir dizeden çözülmüş verileri içerebilen bir arabelleğin bayt cinsinden boyutunu almak için bu işlevi çağırın. |
| [UUEncode](reference/atl-text-encoding-functions.md#uuencode) | Bazı verileri uuencode olarak kodlamak için bu işlevi çağırın. |
| [UUEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#uuencodegetrequiredlength) | Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın. |

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../atl/active-template-library-atl-concepts.md)<br/>
[ATL COM Masaüstü bileşenleri](../atl/atl-com-desktop-components.md)
