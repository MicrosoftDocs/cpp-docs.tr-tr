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
ms.openlocfilehash: 04c4ac6b599e294f5514f8a2f487ed9072f3f875
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44099570"
---
# <a name="codecvtutf8utf16"></a>codecvt_utf8_utf16

Temsil eden bir [yerel ayar](../standard-library/locale-class.md) UTF-16 olarak kodlanmış geniş karakterler ve UTF-8 olarak kodlanmış bir bayt akışı arasında dönüştürür modeli.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf8_utf16 : public _STD codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>Parametreler

*Elem*<br/>
Geniş karakter öğe türü.
*Maxcode*<br/>
Yerel ayar modeli için karakter sayısı.
*Modu*<br/>
Yerel ayar modeli için yapılandırma bilgileri.

## <a name="remarks"></a>Açıklamalar

Bayt akışı, ikili dosya ya da bir metin dosyası yazılabilir.

## <a name="requirements"></a>Gereksinimler

Başlık: \<codecvt >  
Namespace: std
