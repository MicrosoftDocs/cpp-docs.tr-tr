---
title: codecvt_utf8_utf16 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: codecvt/std::cvt_utf8_utf16
dev_langs: C++
helpviewer_keywords: codecvt_utf8_utf16 class
ms.assetid: 4c12c881-5dba-4e39-b338-0b9caff5af29
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a3c97bf0e27e1772a18cbdf1ad15bd8993925215
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="codecvtutf8utf16"></a>codecvt_utf8_utf16
Temsil eden bir [yerel](../standard-library/locale-class.md) UTF-16 kodlanmış uluslararası karakterler ve UTF-8 olarak kodlanmış bir bayt akış arasında dönüştürür modeli.

```
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf8_utf16 : public _STD codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>Parametreler

`Elem`  
Joker karakter öğe türü.  
`Maxcode`  
Yerel ayar model karakter sayısı.  
`Mode`  
Yerel ayar modeli için yapılandırma bilgileri.  

## <a name="remarks"></a>Açıklamalar

Bayt akışı, ikili dosya veya bir metin dosyası için yazılabilir.  

## <a name="requirements"></a>Gereksinimler

Başlık: <codecvt> Namespace: std
