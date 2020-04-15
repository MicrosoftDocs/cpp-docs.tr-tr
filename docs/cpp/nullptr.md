---
title: nullptr
ms.date: 11/04/2016
f1_keywords:
- nullptr_cpp
helpviewer_keywords:
- nullptr keyword [C++]
ms.assetid: e9d80ea6-2506-4eb5-b47b-2349df085832
ms.openlocfilehash: 51df20ea00e5dd77ab1fc1a2a01253b8f788ad0a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358848"
---
# <a name="nullptr"></a>nullptr

Herhangi bir ham işaretçi `std::nullptr_t`türüne dönüştürülebilen null işaretçi sabiti türüne atar.  Herhangi bir üstbilgi dahil etmeden anahtar kelime **nullptr** kullanabilirsiniz rağmen, kodunuzu türü `std::nullptr_t`kullanıyorsa , `<cstddef>`o zaman üstbilgi ekleyerek tanımlamanız gerekir.

> [!NOTE]
> **Nullptr** anahtar kelimesi yönetilen kod uygulamaları için C++/CLI dilinde de tanımlanır ve ISO Standart C++ anahtar kelimesi ile değiştirilemez. Kodunuzu yönetilen kodu hedefleyen [/clr](../build/reference/clr-common-language-runtime-compilation.md) derleyici sebunu kullanarak derlenebilirse, derleyicinin yerel C++ yorumunu kullandığını garanti etmeniz gereken herhangi bir kod satırında kullanın. `__nullptr` Daha fazla bilgi için [nullptr' a](../extensions/nullptr-cpp-component-extensions.md)bakın.

## <a name="remarks"></a>Açıklamalar

NULL veya sıfır`0`() () bir null işaretçi sabiti olarak kullanmaktan kaçının; **nullptr** kötüye kullanıma karşı daha az savunmasızdır ve çoğu durumda daha iyi çalışır.  Örneğin, verilen `func(std::pair<const char *, double>)`, `func(std::make_pair(NULL, 3.14))` sonra arama derleyici hatasına neden olur.  Makro NULL genişletir `0`, böylece `std::make_pair(0, 3.14)` çağrı `std::pair<int, double>`döner , hangi func()'s `std::pair<const char *, double>` parametre türüne dönüştürülebilir değildir.  Arama `func(std::make_pair(nullptr, 3.14))` başarıyla derlenir çünkü `std::make_pair(nullptr, 3.14)` döndürür `std::pair<std::nullptr_t, double>`, hangi dönüştürülebilir `std::pair<const char *, double>`.

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[nullptr](../extensions/nullptr-cpp-component-extensions.md)(C++/CLI)
