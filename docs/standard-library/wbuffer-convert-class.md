---
title: wbuffer_convert Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocmon/stdext::cvt::wbuffer_convert
helpviewer_keywords:
- wbuffer_convert class
ms.assetid: 4a56f9bf-4138-4612-b516-525fea401358
ms.openlocfilehash: 8de0091af93120290105ce7603fae5acff257b76
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688537"
---
# <a name="wbuffer_convert-class"></a>wbuffer_convert Sınıfı

Bir bayt akışı arabelleğine ve bu öğeden öğelerin aktarılmasını denetleyen bir akış arabelleği tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Codecvt, class Elem = wchar_t, class Traits = std::char_traits<Elem>>
class wbuffer_convert
    : public std::basic_streambuf<Elem, Traits>
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Codecvt*|Dönüştürme nesnesini temsil eden [yerel ayar](../standard-library/locale-class.md) modeli.|
|*Elem*|Geniş karakterli öğe türü.|
|*Lerdir*|*Eled*ile ilişkili nitelikler.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf şablonu, `_Elem` türünde öğelerin aktarımını denetleyen bir akış arabelleği tanımlar. Bu, karakter nitelikleri, `std::streambuf` türündeki bir bayt akışı arabelleğine ve bu `Traits` sınıftan açıklanacaktır.

Bir dizi `Elem` değeri ve çok baytlı diziler arasında dönüştürme, standart kod dönüştürme modeli `std::codecvt<Elem, char, std::mbstate_t>` gereksinimlerini karşılayan `Codecvt<Elem, char, std::mbstate_t>` sınıfının bir nesnesi tarafından gerçekleştirilir.

Bu sınıf şablonunun bir nesnesi şunları depolar:

- Temel alınan bayt akışı arabelleğine yönelik bir işaretçi

- Ayrılmış dönüştürme nesnesine yönelik bir işaretçi ( [wbuffer_convert](../standard-library/wbuffer-convert-class.md) olduğunda serbest bırakılır
