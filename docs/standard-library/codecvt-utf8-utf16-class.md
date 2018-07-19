---
title: codecvt_utf8_utf16 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- codecvt/std::cvt_utf8_utf16
dev_langs:
- C++
helpviewer_keywords:
- codecvt_utf8_utf16 class
ms.assetid: 4c12c881-5dba-4e39-b338-0b9caff5af29
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 545fda08a027b1610f82d17c89ae98241ee5502b
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38958136"
---
# <a name="codecvtutf8utf16"></a>codecvt_utf8_utf16

Temsil eden bir [yerel ayar](../standard-library/locale-class.md) UTF-16 olarak kodlanmış geniş karakterler ve UTF-8 olarak kodlanmış bir bayt akışı arasında dönüştürür modeli.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf8_utf16 : public _STD codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>Parametreler

*Elem* geniş karakter öğe türü.
*Maxcode* yerel ayar modeli için karakter sayısı.
*Modu* yerel ayar modeli için yapılandırma bilgileri.

## <a name="remarks"></a>Açıklamalar

Bayt akışı, ikili dosya ya da bir metin dosyası yazılabilir.

## <a name="requirements"></a>Gereksinimler

Başlık: <codecvt> Namespace: std
