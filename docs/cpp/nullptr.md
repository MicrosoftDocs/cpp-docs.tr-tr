---
title: nullptr
ms.date: 11/04/2016
f1_keywords:
- nullptr_cpp
helpviewer_keywords:
- nullptr keyword [C++]
ms.assetid: e9d80ea6-2506-4eb5-b47b-2349df085832
ms.openlocfilehash: 223f4c3e8c838698f9716e241543db405c9394af
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177774"
---
# <a name="nullptr"></a>nullptr

Herhangi bir ham işaretçi türüne dönüştürülebilir `std::nullptr_t`türünde boş bir işaretçi sabiti belirler.  Herhangi bir başlık dahil etmeden **nullptr** anahtar sözcüğünü kullanabilirsiniz, ancak kodunuz `std::nullptr_t`türünü kullanıyorsa, üstbilgiyi `<cstddef>`ekleyerek tanımlamanız gerekir.

> [!NOTE]
>  **Nullptr** anahtar sözcüğü, yönetilen kod uygulamaları C++için/CLI ' da tanımlanmıştır ve ISO standardı C++ anahtar sözcüğüyle birlikte kullanılamaz. Kodunuz, yönetilen kodu hedefleyen [/clr](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği kullanılarak derleniyorsa, derleyicinin yerel C++ yorumu kullandığından emin olmanız gereken herhangi bir kod satırında `__nullptr` kullanın. Daha fazla bilgi için bkz. [nullptr](../extensions/nullptr-cpp-component-extensions.md).

## <a name="remarks"></a>Açıklamalar

Null veya sıfır (`0`) boş bir işaretçi sabiti ile kullanmaktan kaçının; **nullptr** kötüye kullanımı azaltır ve çoğu durumda daha iyi çalışabilir.  Örneğin, `func(std::pair<const char *, double>)`verildiğinde `func(std::make_pair(NULL, 3.14))` çağırma bir derleyici hatasına neden olur.  Makronun NULL değeri `0`olarak genişletilir, böylece çağrı `std::make_pair(0, 3.14)` Func () işlevinin `std::pair<const char *, double>` parametre türüne dönüştürülebilir olmayan `std::pair<int, double>`döndürür.  `std::make_pair(nullptr, 3.14)` `func(std::make_pair(nullptr, 3.14))` çağrısı başarıyla derlenir çünkü bu, `std::pair<const char *, double>`dönüştürülebilir `std::pair<std::nullptr_t, double>`döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[nullptr](../extensions/nullptr-cpp-component-extensions.md)(C++/CLI)
