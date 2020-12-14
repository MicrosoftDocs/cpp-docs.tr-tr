---
description: 'Daha fazla bilgi edinin: Önişlemci işleçleri'
title: Ön işlemci işleçleri
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor operators
- operators [C++], preprocessor
ms.assetid: 884126d1-0ce2-48b6-9e06-8a2d7c4a9656
ms.openlocfilehash: 960531a32dd8b4f834117fb01272e2ed45fecf92
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202099"
---
# <a name="preprocessor-operators"></a>Ön işlemci işleçleri

Yönergesinin bağlamında, Önişlemciye özgü dört işleç kullanılır `#define` . Her birinin Özeti için aşağıdaki tabloya bakın. Dize haline getirme, karakter haline getirme ve belirteç yapıştırma işleçleri sonraki üç bölümde ele alınmıştır. İşleci hakkında daha fazla bilgi için `defined` [#if, #elif, #else ve #endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)yönergelerine bakın.

|Operatör|Eylem|
|--------------|------------|
|[Dizeleyen işleç (#)](../preprocessor/stringizing-operator-hash.md)|Karşılık gelen gerçek bağımsız değişkenin çift tırnak içine alınmasına neden olur|
|[Karakter haline getirme işleci (#@)](../preprocessor/charizing-operator-hash-at.md)|İlgili bağımsız değişkenin tek tırnak işaretleri içine alınmasına ve bir karakter (Microsoft 'a özgü) olarak kabul edilmesine neden olur|
|[Belirteç yapıştıran işleç (##)](../preprocessor/token-pasting-operator-hash-hash.md)|Gerçek bağımsız değişken olarak kullanılan belirteçlerin başka belirteçler oluşturacak şekilde birleştirilmesine olanak verir|
|[tanımlı işleç](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|Bazı makro yönergelerinde bileşik ifadelerin yazımını basitleştirir|

## <a name="see-also"></a>Ayrıca bkz.

[Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md)\
[Önceden tanımlanmış makrolar](../preprocessor/predefined-macros.md)\
[c/c++ Önişlemci Başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)
