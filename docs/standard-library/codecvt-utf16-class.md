---
title: codecvt_utf16
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_utf16
helpviewer_keywords:
- codecvt_utf16 class
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
ms.openlocfilehash: 18b95884bb673305398739968ef2530e8c4778d1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649143"
---
# <a name="codecvtutf16"></a>codecvt_utf16

Temsil eden bir [yerel ayar](../standard-library/locale-class.md) UCS-2 veya UCS-4 olarak kodlanmış geniş karakterler ve UTF-16LE veya UTF-16BE türlerinden olarak kodlanmış bir bayt akışı arasında dönüştürür modeli.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>Parametreler

*Elem*<br/>
Geniş karakter öğe türü.

*Maxcode*<br/>
Yerel ayar modeli için karakter sayısı.

*Modu*<br/>
Yerel ayar modeli için yapılandırma bilgileri.

## <a name="remarks"></a>Açıklamalar

Bu şablon sınıfının UCS-2 veya UCS-4 olarak kodlanmış geniş karakterler ve UTF-16LE kodlanmış bir bayt akışı arasında dönüştürür modu & little_endian veya UTF-16BE türlerinden Aksi takdirde.

Bayt akışından bir ikili dosyaya yazılması gerekir; bir metin dosyasına yazılmış bozulabilir.

## <a name="requirements"></a>Gereksinimler

Başlık: \<codecvt >

Namespace: std