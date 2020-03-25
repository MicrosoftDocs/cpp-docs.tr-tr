---
title: codecvt_utf16
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_utf16
helpviewer_keywords:
- codecvt_utf16 class
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
ms.openlocfilehash: 73177985727f4da5cf3ca4eb9e3cc3fb5976f76d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80215286"
---
# <a name="codecvt_utf16"></a>codecvt_utf16

UCS-2 veya UCS-4 olarak kodlanmış geniş karakterler ve UTF-16LE veya UTF-16AS olarak kodlanmış bir bayt akışı arasında dönüştürme yapan bir [yerel ayar](../standard-library/locale-class.md) modeli temsil eder.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>Parametreler

*Eled*\
Geniş karakterli öğe türü.

*Maxcode*\
Yerel ayar modeli için en fazla karakter sayısı.

*Mod*\
Yerel ayar modeli için yapılandırma bilgileri.

## <a name="remarks"></a>Açıklamalar

Bu sınıf şablonu, UCS-2 veya UCS-4 olarak kodlanan geniş karakterler arasında ve UTF-16LE olarak kodlanmış bir bayt akışı, mod & little_endian veya UTF-16' i değilse

Bayt akışı ikili bir dosyaya yazılmalıdır; bir metin dosyasına yazılmışsa bozulmuş olabilir.

## <a name="requirements"></a>Gereksinimler

Üstbilgi: \<codecvt >

Ad alanı: std
