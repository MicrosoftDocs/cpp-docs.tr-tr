---
title: LOCAL (MASM)
ms.date: 08/30/2018
f1_keywords:
- Local
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
ms.openlocfilehash: 94af498865151ff5c49fac9dbc03de65c4ecb934
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51327609"
---
# <a name="local-masm"></a>LOCAL (MASM)

Makro içinde ilk yönergesinde **yerel** her makro örneği için benzersiz olan etiketlerden tanımlar.

## <a name="syntax"></a>Sözdizimi

> YEREL *localname* \[, *localname*]...
>
> YEREL *etiket* \[ __\[__ *sayısı*__]__ ] \[ __:__  *tür*] \[ __,__ *etiket* \[ __\[__ *sayısı* __]__  ] \[ *türü*]]...

## <a name="remarks"></a>Açıklamalar

Yordam tanımındaki ikinci yönergesi (**PROC**), **yerel** yordam boyunca mevcut yığın tabanlı değişkenler oluşturur. *Etiket* basit bir değişken ya da içeren bir dizi olabilir *sayısı* öğeleri.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>