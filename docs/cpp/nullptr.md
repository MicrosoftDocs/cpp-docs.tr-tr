---
title: nullptr
ms.date: 07/22/2020
f1_keywords:
- nullptr_cpp
helpviewer_keywords:
- nullptr keyword [C++]
ms.assetid: e9d80ea6-2506-4eb5-b47b-2349df085832
ms.openlocfilehash: 801ae927d6c9fb70c3187d10269e87097a879bfc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223635"
---
# <a name="nullptr"></a>nullptr

**`nullptr`** Anahtar sözcüğü `std::nullptr_t` , türünün herhangi bir ham işaretçi türüne dönüştürülebilir bir null işaretçi sabiti belirtir.  **`nullptr`** Herhangi bir başlık dahil etmeden anahtar sözcüğünü kullanabilseniz de, kodunuz türü kullanıyorsa, `std::nullptr_t` üstbilgiyi ekleyerek tanımlamanız gerekir `<cstddef>` .

> [!NOTE]
> **`nullptr`** Anahtar sözcüğü, yönetilen kod uygulamaları Için C++/CLI ' da tanımlanır ve ISO standart C++ anahtar sözcüğü ile birlikte değiştirilebilir. Kodunuz [`/clr`](../build/reference/clr-common-language-runtime-compilation.md) yönetilen kodu hedefleyen derleyici seçeneği kullanılarak derleniyorsa, `__nullptr` derleyicinin yerel C++ yorumunu kullandığından emin olmanız gereken herhangi bir kod satırında kullanın. Daha fazla bilgi için bkz. [ `nullptr` (c++/CLI ve c++/cx)](../extensions/nullptr-cpp-component-extensions.md).

## <a name="remarks"></a>Açıklamalar

`NULL` `0` Null işaretçi sabiti olarak veya sıfır () kullanmaktan kaçının; **`nullptr`** kötüye kullanımı daha az ve çoğu durumda daha iyi çalışabilir.  Örneğin, verilen, `func(std::pair<const char *, double>)` çağırma `func(std::make_pair(NULL, 3.14))` bir derleyici hatasına neden olur.  Makro, ' `NULL` `0` `std::make_pair(0, 3.14)` `std::pair<int, double>` `std::pair<const char *, double>` deki parametre türüne dönüştürülebilir olmayan olarak öğesini döndürür `func` .  `func(std::make_pair(nullptr, 3.14))` `std::make_pair(nullptr, 3.14)` `std::pair<std::nullptr_t, double>` ' A dönüştürülebilir olan döndürüyor, için başarıyla derlenir `std::pair<const char *, double>` .

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[`nullptr`(C++/CLı ve C++/CX)](../extensions/nullptr-cpp-component-extensions.md)
