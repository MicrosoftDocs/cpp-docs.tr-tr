---
title: VARSAYAR | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- ASSUME
dev_langs:
- C++
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8a0e43548292d2ffecbebdaead6aa12d6dacc352
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693814"
---
# <a name="assume"></a>ASSUME

YAZMAÇ değerlerini için denetleme hatası sağlar.

## <a name="syntax"></a>Sözdizimi

> VARSAY *segregister*:*adı* [[, *segregister*:*adı*]]...<br/>
> VARSAY *dataregister*:*türü* [[, *dataregister*:*türü*]]...<br/>
> VARSAY *kaydetme*: hata [[, *kaydetme*: hata]]...<br/>
> VARSAY [[*kaydetme*:]] hiçbir şey [[, *kaydetme*: hiçbir şey]]...


## <a name="remarks"></a>Açıklamalar

Sonra bir `ASSUME` yürürlüğe, derleyici belirli kayıtları değerlerine değişiklikleri izleyen konur. **HATA** kayıt kullanılıyorsa bir hata oluşturur. **Hiçbir şey** kaldırır kaydetme hatası denetleniyor. Farklı türde bir deyiminde varsayımlar birleştirebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>