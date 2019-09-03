---
title: Ön işlemci işleçleri
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor operators
- operators [C++], preprocessor
ms.assetid: 884126d1-0ce2-48b6-9e06-8a2d7c4a9656
ms.openlocfilehash: 1c556e4af5913ba8d0dc7efc9648e0d0004d9d7e
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222243"
---
# <a name="preprocessor-operators"></a>Ön işlemci işleçleri

`#define` Yönergesinin bağlamında, Önişlemciye özgü dört işleç kullanılır. Her birinin Özeti için aşağıdaki tabloya bakın. Dize haline getirme, karakter haline getirme ve belirteç yapıştırma işleçleri sonraki üç bölümde ele alınmıştır. `defined` İşleci hakkında daha fazla bilgi için [#if, #elif, #else ve #endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)yönergelerine bakın.

|İşleç|Eylem|
|--------------|------------|
|[Stringize işleci (#)](../preprocessor/stringizing-operator-hash.md)|Karşılık gelen gerçek bağımsız değişkenin çift tırnak içine alınmasına neden olur|
|[Charize işleci (# @)](../preprocessor/charizing-operator-hash-at.md)|Karşılık gelen bağımsız değişkenin tek tırnak içine alınmasına ve karakter (Microsoft'a Özel) olarak kabul edilmesine neden olur|
|[Belirteç yapıştırma işleci (# #)](../preprocessor/token-pasting-operator-hash-hash.md)|Gerçek bağımsız değişken olarak kullanılan belirteçlerin başka belirteçler oluşturacak şekilde birleştirilmesine olanak verir|
|[tanımlı işleç](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|Bazı makro yönergelerinde bileşik ifadelerin yazımını basitleştirir|

## <a name="see-also"></a>Ayrıca bkz.

[Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md)\
[Önceden tanımlanmış makrolar](../preprocessor/predefined-macros.md)\
[c/c++ Önişlemci Başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)
