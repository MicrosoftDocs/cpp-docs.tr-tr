---
title: Değişken sayıda bağımsız değişkenli çağrılar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- arguments [C++], function
- arguments [C++], variable number of
- VARARGS.H
- ellipses (...), variable number of arguments
- STDARGS.H
- function calls, arguments
- '... ellipsis'
- function calls, variable number of arguments
ms.assetid: 8808fb26-4822-42f5-aba3-ac64b54e151b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec70da7259ce0b04334bf9c0e1f529e76b46c6c3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028226"
---
# <a name="calls-with-a-variable-number-of-arguments"></a>Değişken Sayıda Bağımsız Değişkenli Çağrılar

Kısmi parametre listesi, üç nokta gösterimi, üç nokta bir virgül tarafından sonlandırılabilir (**,...** ), işleve geçirilen daha fazla bağımsız değişken olabileceğini göstermek için ancak bunlar hakkında daha fazla bilgi verilir. Tür denetleme bu tür bağımsız değişkenler üzerinde gerçekleştirilmez. Üç nokta gösteriminden önce en az bir parametre gelmeli ve üç nokta gösterimi parametre listesindeki son belirteç olmalıdır. Üç nokta gösterimi olmadan, bir işlevin davranışı (parametre listesinde bildirilenlere ek olarak başka parametreler de alırsa) tanımlanmış olmaz.

Çeşitli sayıda bağımsız değişken içeren bir işlevi çağırmak için yapmanız gereken sadece istenen sayıda bağımsız değişkeni işlev çağrısında belirtmektir. C çalışma zamanı kitaplığından `printf` işlevi buna bir örnektir. İşlev çağrısı, parametre listesinde veya bağımsız değişken türleri listesinde bildirilen her tür adı için bir bağımsız değişken eklemelidir.

`__fastcall` çağırma kuralı belirtilmediği takdirde, işlevde belirtilen tüm bağımsız değişkenler yığına yerleştirilir. İşlev için bildirilen parametre sayısı yığından kaç tane bağımsız değişken alınacağını ve parametrelere atanacağını belirler. Kaç tane bağımsız değişken bulunduğunu belirlemek için, ek bağımsız değişkenleri yığından alma sorumluluğu size aittir. STDARG.H dosyası, çeşitli sayıda bağımsız değişken alan işlevlerin bağımsız değişkenlerine erişmek için ANSI tarzı makrolar içerir. Ayrıca, VARARGS.H içinde XENIX tarzı makrolar da desteklenmektedir.

Bu örnek bildirim, çeşitli sayıda bağımsız çağıran bir işlev içindir:

```
int average( int first, ...);
```

## <a name="see-also"></a>Ayrıca Bkz.

[İşlev Çağrıları](../c-language/function-calls.md)