---
title: Ön işlemci İşleçleri
ms.date: 11/04/2016
helpviewer_keywords:
- preprocessor operators
- operators [C++], preprocessor
ms.assetid: 884126d1-0ce2-48b6-9e06-8a2d7c4a9656
ms.openlocfilehash: 0b105cc2039e2aa50c11b796e5474a97d8c5c702
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179899"
---
# <a name="preprocessor-operators"></a>Ön işlemci İşleçleri
`#define` yönergesi bağlamında, önişlemciye özgü dört işleç kullanılır (her birinin özeti için aşağıdaki listeye bakın). Dize haline getirme, karakter haline getirme ve belirteç yapıştırma işleçleri sonraki üç bölümde ele alınmıştır. Hakkında bilgi için `defined` işleci bkz [#if, #elif, #else ve #endif yönergeleri](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).

|İşleç|Eylem|
|--------------|------------|
|[Dizeleyen işleç (#)](../preprocessor/stringizing-operator-hash.md)|Karşılık gelen gerçek bağımsız değişkenin çift tırnak içine alınmasına neden olur|
|[Charizing operator (#@)](../preprocessor/charizing-operator-hash-at.md)|Karşılık gelen bağımsız değişkenin tek tırnak içine alınmasına ve karakter (Microsoft'a Özel) olarak kabul edilmesine neden olur|
|[Belirteç yapıştıran işleç (#)](../preprocessor/token-pasting-operator-hash-hash.md)|Gerçek bağımsız değişken olarak kullanılan belirteçlerin başka belirteçler oluşturacak şekilde birleştirilmesine olanak verir|
|[Defined işleci](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|Bazı makro yönergelerinde bileşik ifadelerin yazımını basitleştirir|

## <a name="see-also"></a>Ayrıca bkz.

[Ön işlemci Yönergeleri](../preprocessor/preprocessor-directives.md)<br/>
[Önceden Tanımlanmış Makrolar](../preprocessor/predefined-macros.md)<br/>
[C/C++ Ön İşlemci Başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)