---
title: wbuffer_convert sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xlocmon/stdext::cvt::wbuffer_convert
dev_langs:
- C++
helpviewer_keywords:
- wbuffer_convert class
ms.assetid: 4a56f9bf-4138-4612-b516-525fea401358
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5234e7c85bc522b1ad0a97b58ac4a70528495ea0
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="wbufferconvert-class"></a>wbuffer_convert Sınıfı

Öğeleri baytlık bir Akış Arabellek gelen ve giden iletimini denetleyen bir Akış Arabellek açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Codecvt, class Elem = wchar_t, class Traits = std::char_traits<Elem>>
class wbuffer_convert
 : public std::basic_streambuf<Elem, Traits>
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`Codecvt`|[Yerel](../standard-library/locale-class.md) dönüştürme nesneyi temsil eden modeli.|
|`Elem`|Joker karakter öğe türü.|
|`Traits`|İle ilişkili olarak nitelikler *Elem*.|

## <a name="remarks"></a>Açıklamalar

Bu şablon sınıfı türündeki öğeler iletimini denetleyen bir Akış Arabellek açıklar `_Elem`, olan karakter nitelikler sınıfı tarafından açıklanan `Traits`, gelen ve giden türünde baytlık bir Akış Arabellek `std::streambuf`.

Bir dizi arasında dönüştürme `Elem` değerleri ve çok baytlı sıraları sınıfın bir nesnesi tarafından gerçekleştirilen `Codecvt<Elem, char, std::mbstate_t>`, standart kod dönüştürme modeli gereksinimlerini karşılayan `std::codecvt<Elem, char, std::mbstate_t>`.

Bu şablon sınıfın bir nesnesi depolar:

- Temel alınan bayt akışı arabelleğini gösteren bir işaretçi

- Ayrılmış dönüştürme nesnesine bir işaretçi (olduğu zaman serbest [wbuffer_convert](../standard-library/wbuffer-convert-class.md)
