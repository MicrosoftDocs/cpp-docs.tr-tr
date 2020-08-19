---
title: wbuffer_convert Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocmon/stdext::cvt::wbuffer_convert
helpviewer_keywords:
- wbuffer_convert class
ms.assetid: 4a56f9bf-4138-4612-b516-525fea401358
ms.openlocfilehash: ba8c98075741ae6cb8db0ecdfcb1e18cf4f4f89c
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561121"
---
# <a name="wbuffer_convert-class"></a>wbuffer_convert Sınıfı

Bir bayt akışı arabelleğine ve bu öğeden öğelerin aktarılmasını denetleyen bir akış arabelleği tanımlar.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Codecvt, class Elem = wchar_t, class Traits = std::char_traits<Elem>>
class wbuffer_convert
    : public std::basic_streambuf<Elem, Traits>
```

### <a name="parameters"></a>Parametreler

*Codecvt*\
Dönüştürme nesnesini temsil eden [yerel ayar](../standard-library/locale-class.md) modeli.

*Elem*\
Geniş karakterli öğe türü.

*Lerdir*\
*Eled*ile ilişkili nitelikler.

## <a name="remarks"></a>Açıklamalar

Bu sınıf şablonu, türündeki öğelerin aktarımını denetleyen bir akış arabelleği tanımlar `_Elem` . Bu, karakter nitelikleri sınıf tarafından `Traits` , türü bir bayt akışı arabelleğine, ve öğesinden açıklanmıştır `std::streambuf` .

Bir `Elem` değerler dizisi ve çok baytlı diziler arasında dönüştürme, `Codecvt<Elem, char, std::mbstate_t>` standart kod dönüştürme modelinin gereksinimlerini karşılayan sınıfının bir nesnesi tarafından gerçekleştirilir `std::codecvt<Elem, char, std::mbstate_t>` .

Bu sınıf şablonunun bir nesnesi şunları depolar:

- Temel alınan bayt akışı arabelleğine yönelik bir işaretçi

- Ayrılmış dönüştürme nesnesine yönelik bir işaretçi ( [wbuffer_convert](../standard-library/wbuffer-convert-class.md) serbest bırakılır
