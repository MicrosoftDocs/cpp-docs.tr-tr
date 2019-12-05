---
title: Ön işlemci işleçleri
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor operators
- operators [C++], preprocessor
ms.assetid: 884126d1-0ce2-48b6-9e06-8a2d7c4a9656
ms.openlocfilehash: 5dd252fb495a05efe6eef45674f9ecd601a298a7
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857950"
---
# <a name="preprocessor-operators"></a>Ön işlemci işleçleri

`#define` yönergesinin bağlamında, Önişlemciye özgü dört işleç kullanılır. Her birinin Özeti için aşağıdaki tabloya bakın. Dize haline getirme, karakter haline getirme ve belirteç yapıştırma işleçleri sonraki üç bölümde ele alınmıştır. `defined` işleci hakkında daha fazla bilgi için, bkz. [#if, #elif, #else ve #endif yönergeleri](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).

|İşleç|Eylem|
|--------------|------------|
|[Stringize işleci (#)](../preprocessor/stringizing-operator-hash.md)|Karşılık gelen gerçek bağımsız değişkenin çift tırnak içine alınmasına neden olur|
|[Charize işleci (# @)](../preprocessor/charizing-operator-hash-at.md)|İlgili bağımsız değişkenin tek tırnak işaretleri içine alınmasına ve bir karakter (Microsoft 'a özgü) olarak kabul edilmesine neden olur|
|[Belirteç yapıştırma işleci (# #)](../preprocessor/token-pasting-operator-hash-hash.md)|Gerçek bağımsız değişken olarak kullanılan belirteçlerin başka belirteçler oluşturacak şekilde birleştirilmesine olanak verir|
|[tanımlı işleç](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|Bazı makro yönergelerinde bileşik ifadelerin yazımını basitleştirir|

## <a name="see-also"></a>Ayrıca bkz.

[Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md)\
[Önceden tanımlanmış makrolar](../preprocessor/predefined-macros.md)\
[c/c++ Önişlemci Başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)
