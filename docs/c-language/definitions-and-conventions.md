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

Terminaller bir söz dizimi tanımı noktalarıdır. Herhangi bir çözüm mümkündür. Terminaller ayrılmış sözcükler ve kullanıcı tanımlı tanımlayıcıları kümesi içerir.

Terminal dışı sözdizimi içindeki yer tutucuları olan ve bu sözdizimi özeti başka bir yerde tanımlanır. Tanımları özyinelemeli olabilir.

İsteğe bağlı bir bileşen belirtilen tarafından da simgeli <sub>iyileştirilmiş</sub>. Örneğin,

> **{** *ifade*<sub>iyileştirilmiş</sub> **}**

Küme ayraçları içine alınmış bir isteğe bağlı ifade gösterir.

Sözdizimi kurallarının, sözdiziminin farklı bileşenleri için farklı yazı tipi özniteliklerini kullanın. Simgeler ve yazı tipleri aşağıdaki gibidir:

|Öznitelik|Açıklama|
|---------------|-----------------|
|*bildirimlere*|İtalik tür terminal olmayanları gösterir.|
|**const**|Kalın türdeki terminaller, gösterildiği gibi girilmesi gereken sabit ayrılmış sözcükler ve simgelerdir. Bu bağlamdaki karakterler, her zaman büyük/küçük harfe duyarlıdır.|
|<sub>iyileştirilmiş</sub>|Terminal dışı arkasından <sub>iyileştirilmiş</sub> her zaman isteğe bağlıdır.|
|varsayılan yazı tipi|Açıklanan veya listelenen bu yazı kümesindeki C deyimlerde terminaller olarak kullanılabilir.|

Bir iki nokta üst üste (**:**) bir Terminal olmayanın tanımını tanıtır. Alternatif tanımlar listelenen ayrı satırlarda dışında kelimelerinizle başında, "birini."

## <a name="see-also"></a>Ayrıca bkz.

[C Dili Sözdizimi Özeti](../c-language/c-language-syntax-summary.md)
