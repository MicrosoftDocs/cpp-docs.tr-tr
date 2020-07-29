---
title: Catch Blokları Nasıl Değerlendirilir (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- try-catch keyword [C++], catchable types
- catch keyword [C++], types of catch handlers
- C++ exception handling, catch handlers
- exception handling, catching and deleting exceptions
- types [C++], exception handling
ms.assetid: 202dbf07-8ace-4b3b-b3ae-4b45c275e0b4
ms.openlocfilehash: 21d68b25fa3695a9b5637dcace081424f99911d8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87188108"
---
# <a name="how-catch-blocks-are-evaluated-c"></a>Catch Blokları Nasıl Değerlendirilir (C++)

Genel olarak std::exception'dan türetilen türler oluşturulması önerilse de, C++ her türden özel durumlar oluşturmanıza olanak tanır. C++ özel durumu **`catch`** , oluşturulan özel durumla aynı türü belirten bir işleyici tarafından veya herhangi bir özel durum türünü yakalayabilirler.

Oluşturulan özel durumun türü temel sınıfı (veya sınıfları) da olan bir sınıfsa, özel durum türünün temel sınıflarını kabul eden işleyiciler ve özel durum türünün başvuruları tarafından yakalanabilir. Özel durum bir başvuru tarafından yakalandığında oluşturulan gerçek özel durum nesnesine bağlanır; aksi takdirde bir kopya (işlevin bağımsız değişkeniyle hemen hemen aynı) olur.

Bir özel durum oluştuğunda, bu, aşağıdaki işleyici türleri tarafından yakalanmayabilir **`catch`** :

- Herhangi bir türü kabul edebilen bir işleyici (üç nokta sözdizimini kullanarak).

- Özel durum nesnesiyle aynı türü kabul eden bir işleyici; bir kopya olduğundan **`const`** ve **`volatile`** değiştiriciler yoksayıldı.

- Özel durum nesnesiyle aynı türe yapılan başvuruyu kabul eden bir işleyici.

- **`const`** **`volatile`** Özel durum nesnesiyle aynı türde bir veya daha fazla başvuruyu kabul eden bir işleyici.

- Özel durum nesnesiyle aynı türden temel bir sınıfı kabul eden bir işleyici; Bu bir kopya olduğundan **`const`** ve **`volatile`** değiştiriciler yok sayılır. **`catch`** Bir temel sınıf için işleyici, **`catch`** türetilmiş sınıf için işleyicinin önünde olmamalıdır.

- Özel durum nesnesiyle aynı türden temel sınıf başvurusunu kabul eden bir işleyici.

- **`const`** **`volatile`** Özel durum nesnesiyle aynı türdeki bir temel sınıfın bir veya biçimine başvuruyu kabul eden bir işleyici.

- Oluşturulan bir işaretçi nesnesinin standart işaretçi dönüştürme kurallarıyla dönüştürülebileceği bir işaretçiyi kabul eden bir işleyici.

**`catch`** Belirli bir **`try`** bloğun işleyicileri görünümü sırasıyla incelenmediğinden, işleyicilerin ne kadar önemli olduğunu gösteren sıra. Örneğin, temel sınıfa yönelik bir işleyicisi türetilmiş sınıfa yönelik bir işleyiciden önce yerleştirmek hatadır. Eşleşen bir işleyici bulduktan sonra **`catch`** , sonraki işleyiciler incelenmez. Sonuç olarak, üç nokta **`catch`** işleyicisi bloğunun son işleyicisi olmalıdır **`try`** . Örnek:

```cpp
// ...
try
{
    // ...
}
catch( ... )
{
    // Handle exception here.
}
// Error: the next two handlers are never examined.
catch( const char * str )
{
    cout << "Caught exception: " << str << endl;
}
catch( CExcptClass E )
{
    // Handle CExcptClass exception here.
}
```

Bu örnekte, üç nokta **`catch`** işleyicisi incelenen tek işleyicidir.

## <a name="see-also"></a>Ayrıca bkz.

[Özel durumlar ve hata işleme için modern C++ en iyi uygulamaları](../cpp/errors-and-exception-handling-modern-cpp.md)
