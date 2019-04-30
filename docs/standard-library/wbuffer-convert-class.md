---
title: wbuffer_convert Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocmon/stdext::cvt::wbuffer_convert
helpviewer_keywords:
- wbuffer_convert class
ms.assetid: 4a56f9bf-4138-4612-b516-525fea401358
ms.openlocfilehash: d19abf74bd9f794bc39ce04e5ed22e360cde75b4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410895"
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
