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
ms.openlocfilehash: 11804c48631659b84006abb824837efea3902416
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188643"
---
# <a name="how-catch-blocks-are-evaluated-c"></a>Catch Blokları Nasıl Değerlendirilir (C++)

Genel olarak std::exception'dan türetilen türler oluşturulması önerilse de, C++ her türden özel durumlar oluşturmanıza olanak tanır. C++ Özel durum, oluşturulan özel durumla aynı türü belirten bir **catch** işleyicisi veya herhangi bir özel durum türünü yakalayabilirler.

Oluşturulan özel durumun türü temel sınıfı (veya sınıfları) da olan bir sınıfsa, özel durum türünün temel sınıflarını kabul eden işleyiciler ve özel durum türünün başvuruları tarafından yakalanabilir. Özel durum bir başvuru tarafından yakalandığında oluşturulan gerçek özel durum nesnesine bağlanır; aksi takdirde bir kopya (işlevin bağımsız değişkeniyle hemen hemen aynı) olur.

Bir özel durum oluştuğunda, bu, aşağıdaki **catch** işleyicileri türleri tarafından yakalanmayabilir:

- Herhangi bir türü kabul edebilen bir işleyici (üç nokta sözdizimini kullanarak).

- Özel durum nesnesiyle aynı türü kabul eden bir işleyici; bir kopya olduğundan, **const** ve **volatile** değiştiricileri yok sayılır.

- Özel durum nesnesiyle aynı türe yapılan başvuruyu kabul eden bir işleyici.

- Özel durum nesnesiyle aynı türde bir **const** veya **volatile** biçimine başvuruyu kabul eden bir işleyici.

- Özel durum nesnesiyle aynı türden temel bir sınıfı kabul eden bir işleyici; bir kopya olduğundan, **const** ve **volatile** değiştiricileri yok sayılır. Bir temel sınıf için **catch** işleyicisi, türetilmiş sınıf için **catch** işleyicisinden önce gelmelidir.

- Özel durum nesnesiyle aynı türden temel sınıf başvurusunu kabul eden bir işleyici.

- Özel durum nesnesiyle aynı türdeki bir temel sınıfın **const** veya **volatile** biçimine başvuruyu kabul eden bir işleyici.

- Oluşturulan bir işaretçi nesnesinin standart işaretçi dönüştürme kurallarıyla dönüştürülebileceği bir işaretçiyi kabul eden bir işleyici.

Belirli bir **TRY** bloğunun işleyicileri görünümü sırasıyla incelenmediği için, **catch** işleyicilerinin görünme sırası önemlidir. Örneğin, temel sınıfa yönelik bir işleyicisi türetilmiş sınıfa yönelik bir işleyiciden önce yerleştirmek hatadır. Eşleşen bir **catch** işleyicisi bulduktan sonra, sonraki işleyiciler incelenmez. Sonuç olarak, üç nokta **catch** işleyicisi **TRY** bloğunun son işleyicisi olmalıdır. Örneğin:

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

Bu örnekte, üç nokta **catch** işleyicisi incelenen tek işleyicidir.

## <a name="see-also"></a>Ayrıca bkz.

[Özel C++ durumlar ve hata işleme için modern en iyi uygulamalar](../cpp/errors-and-exception-handling-modern-cpp.md)
