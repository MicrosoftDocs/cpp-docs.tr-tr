---
description: 'Hakkında daha fazla bilgi edinin: codecvt_utf8_utf16'
title: codecvt_utf8_utf16
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::cvt_utf8_utf16
helpviewer_keywords:
- codecvt_utf8_utf16 class
ms.assetid: 4c12c881-5dba-4e39-b338-0b9caff5af29
ms.openlocfilehash: e80cdaa01ef77b9ce28a773eb4e05056220718a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325081"
---
# <a name="codecvt_utf8_utf16"></a>codecvt_utf8_utf16

UTF-16 olarak kodlanmış geniş karakterler ve UTF-8 olarak kodlanmış bir bayt akışı arasında dönüştüren bir [yerel ayar](../standard-library/locale-class.md) modeli temsil eder.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf8_utf16 : public _STD codecvt<Elem, char, StateType>
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
