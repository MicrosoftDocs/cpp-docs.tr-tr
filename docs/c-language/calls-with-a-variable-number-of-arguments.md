---
title: Değişken Sayıda Bağımsız Değişkenli Çağrılar
ms.date: 11/04/2016
helpviewer_keywords:
- arguments [C++], function
- arguments [C++], variable number of
- VARARGS.H
- ellipsis (...), variable number of arguments
- STDARGS.H
- function calls, arguments
- '... ellipsis'
- function calls, variable number of arguments
ms.assetid: 8808fb26-4822-42f5-aba3-ac64b54e151b
ms.openlocfilehash: 9fee0c214b697126708ae36b4daee082ac0171e9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227939"
---
# <a name="calls-with-a-variable-number-of-arguments"></a>Değişken Sayıda Bağımsız Değişkenli Çağrılar

Kısmi bir parametre listesi, üç nokta (,...) ve ardından üç nokta (**,...**) ile sona erer, ancak bu işleve daha fazla bağımsız değişken verildiğini belirten bir virgül, ancak bunlarla ilgili daha fazla bilgi verilmeyebilir. Tür denetleme bu tür bağımsız değişkenler üzerinde gerçekleştirilmez. Üç nokta gösteriminden önce en az bir parametre gelmeli ve üç nokta gösterimi parametre listesindeki son belirteç olmalıdır. Üç nokta gösterimi olmadan, bir işlevin davranışı (parametre listesinde bildirilenlere ek olarak başka parametreler de alırsa) tanımlanmış olmaz.

Çeşitli sayıda bağımsız değişken içeren bir işlevi çağırmak için yapmanız gereken sadece istenen sayıda bağımsız değişkeni işlev çağrısında belirtmektir. C çalışma zamanı kitaplığından `printf` işlevi buna bir örnektir. İşlev çağrısı, parametre listesinde veya bağımsız değişken türleri listesinde bildirilen her tür adı için bir bağımsız değişken eklemelidir.

İşlev çağrısında belirtilen tüm bağımsız değişkenler, **`__fastcall`** çağırma kuralı belirtilmediği takdirde yığına yerleştirilir. İşlev için bildirilen parametre sayısı yığından kaç tane bağımsız değişken alınacağını ve parametrelere atanacağını belirler. Kaç tane bağımsız değişken bulunduğunu belirlemek için, ek bağımsız değişkenleri yığından alma sorumluluğu size aittir. STDARG.H dosyası, çeşitli sayıda bağımsız değişken alan işlevlerin bağımsız değişkenlerine erişmek için ANSI tarzı makrolar içerir. Ayrıca, VARARGS.H içinde XENIX tarzı makrolar da desteklenmektedir.

Bu örnek bildirim, çeşitli sayıda bağımsız çağıran bir işlev içindir:

```
int average( int first, ...);
```

## <a name="see-also"></a>Ayrıca bkz.

[İşlev çağrıları](../c-language/function-calls.md)
