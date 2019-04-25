---
title: LOCAL (MASM)
ms.date: 08/30/2018
f1_keywords:
- Local
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
ms.openlocfilehash: 94af498865151ff5c49fac9dbc03de65c4ecb934
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62178013"
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