---
description: 'Hakkında daha fazla bilgi edinin: wbuffer_convert sınıfı'
title: wbuffer_convert Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocmon/stdext::cvt::wbuffer_convert
helpviewer_keywords:
- wbuffer_convert class
ms.assetid: 4a56f9bf-4138-4612-b516-525fea401358
ms.openlocfilehash: 1aa7258c3cc0a4f78a749f655e9cfb7cd4957378
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187851"
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

*Codecvt*\
Dönüştürme nesnesini temsil eden [yerel ayar](../standard-library/locale-class.md) modeli.

*Elem*\
Geniş karakterli öğe türü.

*Lerdir*\
*Eled* ile ilişkili nitelikler.

## <a name="remarks"></a>Açıklamalar

Bu sınıf şablonu, türündeki öğelerin aktarımını denetleyen bir akış arabelleği tanımlar `_Elem` . Bu, karakter nitelikleri sınıf tarafından `Traits` , türü bir bayt akışı arabelleğine, ve öğesinden açıklanmıştır `std::streambuf` .

Bir `Elem` değerler dizisi ve çok baytlı diziler arasında dönüştürme, `Codecvt<Elem, char, std::mbstate_t>` standart kod dönüştürme modelinin gereksinimlerini karşılayan sınıfının bir nesnesi tarafından gerçekleştirilir `std::codecvt<Elem, char, std::mbstate_t>` .

Bu sınıf şablonunun bir nesnesi şunları depolar:

- Temel alınan bayt akışı arabelleğine yönelik bir işaretçi

- Ayrılmış dönüştürme nesnesine yönelik bir işaretçi ( [wbuffer_convert](../standard-library/wbuffer-convert-class.md) serbest bırakılır
