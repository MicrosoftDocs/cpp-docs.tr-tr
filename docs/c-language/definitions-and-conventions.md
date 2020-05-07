---
title: Tanımlar ve Kurallar
ms.date: 11/04/2016
helpviewer_keywords:
- nonterminals definition
ms.assetid: f9b3cf5f-6a7c-4a10-9b18-9d4a43efdaeb
ms.openlocfilehash: 0ff3f8b447e29f0da59405a7c0286d7a696b4613
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62234443"
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
|**const**|Kalın türdeki terminaller, gösterildiği gibi girilmesi gereken sabit ayrılmış sözcükler ve simgelerdir. Bu bağlamdaki karakterler, her zaman büyük/küçük harfe duyarlıdır.|
|<sub>opt</sub>|Terminal olmayan ve <sub>opt</sub> tarafından izlenen, her zaman isteğe bağlıdır.|
|varsayılan yazı tipi|Bu yazı tipi içinde açıklanan veya listelenen küme karakterleri C deyimlerinde Terminal olarak kullanılabilir.|

Terminalden sonraki bir iki nokta üst üste (**:**) tanımı tanıtılmıştır. Alternatif tanımlar, "One" kelimesine göre ön ödeme dışında ayrı satırlarda listelenir.

## <a name="see-also"></a>Ayrıca bkz.

[C Dili Sözdizimi Özeti](../c-language/c-language-syntax-summary.md)
