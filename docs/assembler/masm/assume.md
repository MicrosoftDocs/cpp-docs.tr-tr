---
title: ASSUME
ms.date: 08/30/2018
f1_keywords:
- ASSUME
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
ms.openlocfilehash: 97a57cc8a1acccf70572ff963e496aa79fa3ab43
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166470"
---
# <a name="assume"></a>ASSUME

YAZMAÇ değerlerini için denetleme hatası sağlar.

## <a name="syntax"></a>Sözdizimi

> VARSAY *segregister*:*adı* [[, *segregister*:*adı*]]...<br/>
> VARSAY *dataregister*:*türü* [[, *dataregister*:*türü*]]...<br/>
> ASSUME *register*:ERROR [[, *register*:ERROR]]...<br/>
> VARSAY [[*kaydetme*:]] hiçbir şey [[, *kaydetme*: hiçbir şey]]...

## <a name="remarks"></a>Açıklamalar

Sonra bir `ASSUME` yürürlüğe, derleyici belirli kayıtları değerlerine değişiklikleri izleyen konur. **HATA** kayıt kullanılıyorsa bir hata oluşturur. **Hiçbir şey** kaldırır kaydetme hatası denetleniyor. Farklı türde bir deyiminde varsayımlar birleştirebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>