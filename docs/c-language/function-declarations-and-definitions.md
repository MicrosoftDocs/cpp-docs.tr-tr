---
title: İşlev bildirimlerinin ve tanımlarının | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- local declarations
- function definitions, function declarations
- declaring functions, function definitions
- internal declarations
- external declarations
- function prototypes, basics
- external linkage, function declarations
- declaring functions
ms.assetid: 43fd98eb-7441-4473-a5d9-fc88c75577f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2bb5a6b1f184775b3e67a03b9544e609b33673ba
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106135"
---
# <a name="function-declarations-and-definitions"></a>İşlev Bildirimleri ve Tanımlar (C++)

İşlev prototipleri; işlevin türünü, dönüş türünü ve biçimsel parametrelerinin türünü ve sayısını belirler. İşlev tanımı işlev gövdesini içerir.

## <a name="remarks"></a>Açıklamalar

İşlev tanımının içinde veya dışında hem işlev hem de değişken bildirimleri görünebilir. Bir işlev tanımı içerisindeki herhangi bir bildirimin "iç" veya "yerel" düzeyde göründüğü bildirilir. Tüm işlev tanımlarının dışında yer alan bir bildirimin, "dış", "genel" veya "dosya kapsamı" düzeyinde olduğu bildirilir. Bildirimler gibi değişken tanımlar, iç düzeyde (işlev tanımı içerisinde) veya dış düzeyde (tüm işlev tanımlarının dışında) görünebilir. İşlev tanımları her zaman dış düzeyde ortaya çıkar. İşlev tanımları açıklanmıştır daha ayrıntılı olarak [işlev tanımları](../c-language/c-function-definitions.md). İşlev prototipleri kapsamdaki [işlev prototipleri](../c-language/function-prototypes.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Dosyalar ve Kaynak Programlar](../c-language/source-files-and-source-programs.md)