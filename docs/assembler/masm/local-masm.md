---
title: YEREL (MASM) | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- Local
dev_langs:
- C++
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e8105bc8168ce28d468a1378c5cf7889907a7c9f
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43685069"
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