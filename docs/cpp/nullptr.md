---
title: nullptr
ms.date: 11/04/2016
f1_keywords:
- nullptr_cpp
helpviewer_keywords:
- nullptr keyword [C++]
ms.assetid: e9d80ea6-2506-4eb5-b47b-2349df085832
ms.openlocfilehash: 57be8d71f1dac4f347ea6567c02a385719bb7306
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781087"
---
# <a name="nullptr"></a>nullptr

Bir boş işaretçi sabiti türü belirler `std::nullptr_t`, olan herhangi bir ham işaretçi türüne dönüştürülebilir.  Anahtar sözcüğünü kullanmanız mümkün olmakla birlikte **nullptr** kodunuzu türü kullanıyorsa, tüm üst bilgiler dahil olmadan `std::nullptr_t`, üst bilgisi ekleyerek tanımlamalıdır sonra `<cstddef>`.

> [!NOTE]
>  **Nullptr** anahtar sözcüğü de tanımlanan C + +/ CLI için yönetilen kod uygulamaları ve ISO Standard C++ anahtar sözcüğü ile değiştirilebilir değildir. Kodunuzu kullanılarak derlenmiş, [/CLR](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği, yönetilen kod hedefler, ardından kullanmak `__nullptr` herhangi bir satırında kod burada gerekir garanti derleyici yerel C++ yorumu kullanır. Daha fazla bilgi için [nullptr](../extensions/nullptr-cpp-component-extensions.md).

## <a name="remarks"></a>Açıklamalar

NULL veya sıfır kullanmaktan kaçının (`0`) olarak; boş işaretçi sabiti **nullptr** kötüye kullanımı için daha az savunmasızdır ve çoğu durumda daha iyi çalışır.  Örneğin, verilen `func(std::pair<const char *, double>)`, ardından arama `func(std::make_pair(NULL, 3.14))` bir derleyici hatasına neden olur.  NULL genişletilir makrosu `0`, böylece çağrı `std::make_pair(0, 3.14)` döndürür `std::pair<int, double>`, func () olarak ın dönüştürülebilir değil `std::pair<const char *, double>` parametre türü.  Çağırma `func(std::make_pair(nullptr, 3.14))` başarıyla derlenir çünkü `std::make_pair(nullptr, 3.14)` döndürür `std::pair<std::nullptr_t, double>`, dönüştürülebilir olduğu `std::pair<const char *, double>`.

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[nullptr](../extensions/nullptr-cpp-component-extensions.md)(C + +/ CLI)