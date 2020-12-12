---
description: 'Hakkında daha fazla bilgi edinin: codecvt_utf16'
title: codecvt_utf16
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_utf16
helpviewer_keywords:
- codecvt_utf16 class
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
ms.openlocfilehash: 264324d0f827e8999b065205010874ebf62ca501
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325094"
---
# <a name="codecvt_utf16"></a>codecvt_utf16

UCS-2 veya UCS-4 olarak kodlanmış geniş karakterler ve UTF-16LE veya UTF-16AS olarak kodlanmış bir bayt akışı arasında dönüştürme yapan bir [yerel ayar](../standard-library/locale-class.md) modeli temsil eder.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>Parametreler

*Elem*\
Geniş karakterli öğe türü.

*Maxcode*\
Yerel ayar modeli için en fazla karakter sayısı.

*Modundaysa*\
Yerel ayar modeli için yapılandırma bilgileri.

## <a name="remarks"></a>Açıklamalar

Bu sınıf şablonu, UCS-2 veya UCS-4 olarak kodlanan geniş karakterler arasında ve UTF-16LE olarak kodlanmış bir bayt akışı, mod & little_endian veya UTF-16' i değilse

Bayt akışı ikili bir dosyaya yazılmalıdır; bir metin dosyasına yazılmışsa bozulmuş olabilir.

## <a name="requirements"></a>Gereksinimler

Üst bilgi \<codecvt>

Ad alanı: std
