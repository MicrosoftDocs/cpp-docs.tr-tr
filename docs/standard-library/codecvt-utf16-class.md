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
ms.workload: cplusplus
ms.openlocfilehash: e6d7746369c5ecb559cae3b787b8bbf2f475ba28
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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