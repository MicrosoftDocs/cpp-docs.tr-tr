---
title: wbuffer_convert sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocmon/stdext::cvt::wbuffer_convert
dev_langs:
- C++
helpviewer_keywords:
- wbuffer_convert class
ms.assetid: 4a56f9bf-4138-4612-b516-525fea401358
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36df93b54accbfdc3ff8f486c41a47af72032c3f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854616"
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
