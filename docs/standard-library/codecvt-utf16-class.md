---
title: codecvt_utf16 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: codecvt/std::codecvt_utf16
dev_langs: C++
helpviewer_keywords: codecvt_utf16 class
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b84e12815483b2d2caff35d024c8efa21d183025
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="codecvtutf16"></a>codecvt_utf16
Temsil eden bir [yerel](../standard-library/locale-class.md) UCS-2 veya 4 UCS olarak kodlanmış uluslararası karakterler ve UTF-16LE veya UTF-16BE olarak kodlanmış bir bayt akış arasında dönüştürür modeli.

```
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>
```
## <a name="parameters"></a>Parametreler
`Elem`  
Joker karakter öğe türü.  
`Maxcode`  
Yerel ayar model karakter sayısı.  
`Mode`  
Yerel ayar modeli için yapılandırma bilgileri.  

## <a name="remarks"></a>Açıklamalar
Bu şablon sınıfı UCS-2 veya 4 UCS olarak kodlanmış uluslararası karakterler ve UTF-16LE kodlanmış bir bayt akış arasında dönüştürür modu & little_endian veya UTF-16BE Aksi takdirde.

Bir ikili dosya bayt akışı yazılmalıdır; bir metin dosyasına yazılmış bozulmuş.

## <a name="requirements"></a>Gereksinimler
Başlık: \<codecvt > Namespace: std