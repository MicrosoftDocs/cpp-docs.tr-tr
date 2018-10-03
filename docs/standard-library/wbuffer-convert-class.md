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
ms.openlocfilehash: 56f7a4bffc557e473299b7f57266def87bf0cfc3
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235847"
---
# <a name="wbufferconvert-class"></a>wbuffer_convert Sınıfı

Bir bayt akış arabelleği gelen ve giden öğeleri aktarımını denetleyen bir akış arabelleğinin açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Codecvt, class Elem = wchar_t, class Traits = std::char_traits<Elem>>
class wbuffer_convert
    : public std::basic_streambuf<Elem, Traits>
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*codecvt*|[Yerel ayar](../standard-library/locale-class.md) dönüştürme nesneyi temsil eden bir model.|
|*Elem*|Geniş karakter öğe türü.|
|*Nitelikler*|İle ilişkili nitelikler *Elem*.|

## <a name="remarks"></a>Açıklamalar

Bu şablon sınıfının türünde öğeler aktarımını denetleyen bir akış arabelleğinin açıklar `_Elem`, olan karakter nitelikleri sınıfı tarafından açıklanan `Traits`, gelen ve Giden bayt Akış Arabellek türü `std::streambuf`.

Bir dizi arasında dönüştürme `Elem` değerleri ve çok baytlı dizileri sınıfın bir nesnesi tarafından gerçekleştirilen `Codecvt<Elem, char, std::mbstate_t>`, standart kod dönüştürme modeli gereksinimlerini karşılayan `std::codecvt<Elem, char, std::mbstate_t>`.

Bu şablon sınıfının bir nesnesi depolar:

- Temel alınan bayt akış arabelleği için bir işaretçi

- Ayrılmış dönüştürme nesneye bir işaretçi (olduğu zaman serbest [wbuffer_convert](../standard-library/wbuffer-convert-class.md)
