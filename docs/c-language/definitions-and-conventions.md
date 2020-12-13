---
description: 'Daha fazla bilgi edinin: tanımlar ve kurallar'
title: Tanımlar ve Kurallar
ms.date: 11/04/2016
helpviewer_keywords:
- nonterminals definition
ms.assetid: f9b3cf5f-6a7c-4a10-9b18-9d4a43efdaeb
ms.openlocfilehash: 892f14bfc3059406bbc192640e04c0181d06eee2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186876"
---
# <a name="definitions-and-conventions"></a>Tanımlar ve Kurallar

Terminal, bir sözdizimi tanımındaki uç noktalardır. Başka bir çözüm mümkün değildir. Terminal, ayrılmış sözcükler ve Kullanıcı tanımlı tanımlayıcılar kümesini içerir.

Terminallerin sözdizimi, söz dizimi içindeki yer tutuculardır ve bu söz dizimi özetinde başka bir yerde tanımlanır. Tanımlar özyinelemeli olabilir.

İsteğe bağlı bir bileşen, alt indisli <sub>opt</sub>tarafından gösterilir. Örneğin,

> **{** *Expression*<sub>opt</sub> **}**

küme ayraçları içine alınmış bir isteğe bağlı ifadeyi gösterir.

Söz dizimi kuralları, sözdiziminin farklı bileşenleri için farklı yazı tipi öznitelikleri kullanır. Simgeler ve yazı tipleri aşağıdaki gibidir:

|Öznitelik|Açıklama|
|---------------|-----------------|
|*& gt*|İtalik tür terminal olmayanları gösterir.|
|**`const`**|Kalın türdeki terminaller, gösterildiği gibi girilmesi gereken sabit ayrılmış sözcükler ve simgelerdir. Bu bağlamdaki karakterler, her zaman büyük/küçük harfe duyarlıdır.|
|<sub>opt</sub>|Terminal olmayan ve <sub>opt</sub> tarafından izlenen, her zaman isteğe bağlıdır.|
|varsayılan yazı tipi|Bu yazı tipi içinde açıklanan veya listelenen küme karakterleri C deyimlerinde Terminal olarak kullanılabilir.|

Terminalden sonraki bir iki nokta üst üste (**:**) tanımı tanıtılmıştır. Alternatif tanımlar, "One" kelimesine göre ön ödeme dışında ayrı satırlarda listelenir.

## <a name="see-also"></a>Ayrıca bkz.

[C dili sözdizimi özeti](../c-language/c-language-syntax-summary.md)
