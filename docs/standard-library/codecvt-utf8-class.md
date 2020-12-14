---
description: 'Hakkında daha fazla bilgi edinin: codecvt_utf8'
title: codecvt_utf8
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_utf8
helpviewer_keywords:
- codecvt_utf8 class
ms.assetid: 2a87478f-e2d4-4b8d-ad9c-00add01d1bb0
ms.openlocfilehash: b0da37607d563786285564d17b2c8a49e9e064bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234039"
---
# <a name="codecvt_utf8"></a>codecvt_utf8

UCS-2 veya UCS-4 olarak kodlanan geniş karakterler arasında dönüştürme yapan bir [yerel ayar](../standard-library/locale-class.md) MODELI ve UTF-8 olarak kodlanmış bir bayt akışı temsil eder.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf8 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>Parametreler

*Elem*\
Geniş karakterli öğe türü.

*Maxcode*\
Yerel ayar modeli için en fazla karakter sayısı.

*Modundaysa*\
Yerel ayar modeli için yapılandırma bilgileri.

## <a name="remarks"></a>Açıklamalar

Bayt akışı bir ikili dosyaya veya bir metin dosyasına yazılabilir.

## <a name="requirements"></a>Gereksinimler

Üst bilgi \<codecvt>

Ad alanı: std
