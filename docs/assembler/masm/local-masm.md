---
title: LOCAL (MASM)
ms.date: 08/30/2018
f1_keywords:
- Local
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
ms.openlocfilehash: c8ea49b9862159a5a56bfb3d2c3cd0c1f4cd7413
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596878"
---
# <a name="local-masm"></a>LOCAL (MASM)

Makro içinde ilk yönergesinde **yerel** her makro örneği için benzersiz olan etiketlerden tanımlar.

## <a name="syntax"></a>Sözdizimi

> YEREL *localname* [[, *localname*]]...

> YEREL *etiket* [[[*sayısı*]]] [[:*türü*]] [[, *etiket* [[[*sayısı*]]] [[ *tür*]]]]...

## <a name="remarks"></a>Açıklamalar

Yordam tanımındaki ikinci yönergesi (**PROC**), **yerel** yordam boyunca mevcut yığın tabanlı değişkenler oluşturur. *Etiket* basit bir değişken ya da içeren bir dizi olabilir *sayısı* öğeleri.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>