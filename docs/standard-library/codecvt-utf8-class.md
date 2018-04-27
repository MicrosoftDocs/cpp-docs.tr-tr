---
title: codecvt_utf8 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- codecvt/std::codecvt_utf8
dev_langs:
- C++
helpviewer_keywords:
- codecvt_utf8 class
ms.assetid: 2a87478f-e2d4-4b8d-ad9c-00add01d1bb0
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0aeb05c5868c1d97713e81f6f09430f64ded9d8b
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="codecvtutf8"></a>codecvt_utf8

Temsil eden bir [yerel](../standard-library/locale-class.md) UCS-2 veya 4 UCS olarak kodlanmış uluslararası karakterler ve UTF-8 olarak kodlanmış bir bayt akış arasında dönüştürür modeli.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf8 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>Parametreler

`Elem` Joker karakter öğe türü.
`Maxcode` Yerel ayar model karakter sayısı.
`Mode` Yerel ayar modeli için yapılandırma bilgileri.

## <a name="remarks"></a>Açıklamalar

Bayt akışı, ikili dosya veya bir metin dosyası için yazılabilir.

## <a name="requirements"></a>Gereksinimler

Başlık: <codecvt> Namespace: std
