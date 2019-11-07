---
title: ASSUME
ms.date: 11/05/2019
f1_keywords:
- ASSUME
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
ms.openlocfilehash: 4bf8f0c41e9ce3e296cf201efd4fd9be2033cbdb
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/06/2019
ms.locfileid: "73702473"
---
# <a name="assume-32-bit-masm"></a>VARSAY (32-bit Masz)

Kayıt değerlerinin hata denetimini sunar. (yalnızca 32-bit masa.)

## <a name="syntax"></a>Sözdizimi

> *Segregister*:*Name* [[, *segregister*:*Name*]]...<br/>
> *Dataregister*türü varsayın:*Type* [[, *dataregister*:*Type*]]...<br/>
> *Kayıt*varsay: hata [[, *kayıt*: hata]]...<br/>
> [[*Register*:]] nothıng [[, *yazmaç*: nothıng]] olduğunu varsayın...

## <a name="remarks"></a>Açıklamalar

Bir `ASSUME` yürürlüğe girdikten sonra, derleyici verilen yazmaçların değerlerine yapılan değişiklikleri izler. Kayıt kullanılırsa **hata** oluşturur. **Hiçbir şey** kaydetme hata denetimini siler. Tek bir ifadede farklı tür varsayımları birleştirebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>