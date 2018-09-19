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
ms.openlocfilehash: e34b6d3764c0096e30c0e1f27c36194fd5d44110
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088832"
---
# <a name="atl-encoding-reference"></a>ATL Kodlama Başvurusu

Bir dizi onaltılık uuencode gibi ortak Internet standartları ve UTF8 Kodlaması atlenc.h içinde bulunan bir kodu tarafından desteklenir.

### <a name="functions"></a>İşlevler

|||
|-|-|
|[AtlGetHexValue](reference/atl-text-encoding-functions.md#atlgethexvalue)|Onaltılık basamağın sayısal değerini almak için bu işlevi çağırın.|
|[AtlHexDecode](reference/atl-text-encoding-functions.md#atlhexdecode)|Onaltılı metin olarak önceki bir çağrı tarafından kodlanmış veri dizisinin kodunu çözer [AtlHexEncode](reference/atl-text-encoding-functions.md#atlhexencode).|
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
|[QPDecode](reference/atl-text-encoding-functions.md#qpdecode)|Sınırlandırılmış Yazdırılabilir biçimde gibi önceki bir çağrı tarafından kodlanmış veri dizisinin kodunu çözer [QPEncode](reference/atl-text-encoding-functions.md#qpencode).|
|[QPDecodeGetRequiredLength](reference/atl-text-encoding-functions.md#qpdecodegetrequiredlength)|Belirtilen uzunlukta sınırlandırılmış yazdırılabilir biçimde kodlanmış bir dizeden çözülmüş verileri içerebilen bir arabelleğin bayt cinsinden boyutunu almak için bu işlevi çağırın.|
|[QPEncode](reference/atl-text-encoding-functions.md#qpencode)|Bazı verileri sınırlandırılmış yazdırılabilir biçimde kodlamak için bu işlevi çağırın.|
|[QPEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#qpencodegetrequiredlength)|Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.|
|[UUDecode](reference/atl-text-encoding-functions.md#uudecode)|Önceki bir çağrı uuencoded olarak bırakıldı veri dizisinin kodunu çözer [UUEncode](reference/atl-text-encoding-functions.md#uuencode).|
|[UUDecodeGetRequiredLength](reference/atl-text-encoding-functions.md#uudecodegetrequiredlength)|Belirtilen uzunlukta uuencoded olarak kodlanmış bir dizeden çözülmüş verileri içerebilen bir arabelleğin bayt cinsinden boyutunu almak için bu işlevi çağırın.|
|[UUEncode](reference/atl-text-encoding-functions.md#uuencode)|Bazı verileri uuencode olarak kodlamak için bu işlevi çağırın.|
|[UUEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#uuencodegetrequiredlength)|Belirtilen boyutta veriyle kodlanmış bir dizeyi içerebilen bir arabelleğin karakter cinsinden boyutunu almak için bu işlevi çağırın.|

## <a name="see-also"></a>Ayrıca Bkz.

[Kavramları](../atl/active-template-library-atl-concepts.md)<br/>
[ATL COM Masaüstü Bileşenleri](../atl/atl-com-desktop-components.md)

