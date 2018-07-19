---
title: codecvt_utf16 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- codecvt/std::codecvt_utf16
dev_langs:
- C++
helpviewer_keywords:
- codecvt_utf16 class
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cdfcf3c6a562f7aab0164e3d63d468ba39ec0023
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954105"
---
# <a name="codecvtutf16"></a>codecvt_utf16

Temsil eden bir [yerel ayar](../standard-library/locale-class.md) UCS-2 veya UCS-4 olarak kodlanmış geniş karakterler ve UTF-16LE veya UTF-16BE türlerinden olarak kodlanmış bir bayt akışı arasında dönüştürür modeli.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>Parametreler

*Elem* geniş karakter öğe türü.
*Maxcode* yerel ayar modeli için karakter sayısı.
*Modu* yerel ayar modeli için yapılandırma bilgileri.

## <a name="remarks"></a>Açıklamalar

Bu şablon sınıfının UCS-2 veya UCS-4 olarak kodlanmış geniş karakterler ve UTF-16LE kodlanmış bir bayt akışı arasında dönüştürür modu & little_endian veya UTF-16BE türlerinden Aksi takdirde.

Bayt akışından bir ikili dosyaya yazılması gerekir; bir metin dosyasına yazılmış bozulabilir.

## <a name="requirements"></a>Gereksinimler

Başlık: \<codecvt > Namespace: std