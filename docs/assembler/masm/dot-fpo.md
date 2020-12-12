---
description: Hakkında daha fazla bilgi edinin:. D (32-bit masa)
title: .FPO
ms.date: 11/05/2019
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: 058189329cbe849086a3b1540ac7883ecac4d026
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97131709"
---
# <a name="fpo-32-bit-masm"></a>. D (32-bit masa)

**. IBU yönergesi,** hata ayıklama $ F segmentine veya bölümüne hata ayıklama kayıtlarını denetler. (yalnızca 32-bit masa.)

## <a name="syntax"></a>Syntax

> **.** Mı (*cdwyereller*, *cdwparams*, *cbprolog*, *cbregs*, *fusebp*, *cbframe*)

### <a name="parameters"></a>Parametreler

*Cdwyereller*\
İşaretsiz 32 bitlik bir değer olan yerel değişkenlerin sayısı.

*cdwParams*\
DWORD içindeki parametrelerin boyutu, işaretsiz 16 bit değeri.

*cbProlog*\
İşlev giriş kodundaki bayt sayısı, işaretsiz 8 bit değeri.

*cbRegs*\
Numara kayıtları kaydedildi.

*fUseBP*\
EBP kaydının ayrılıp ayrılmadığını belirtir. 0 ya da 1.

*cbFrame*\
Çerçeve türünü gösterir.  Daha fazla bilgi için bkz. [FPO_DATA](/windows/win32/api/winnt/ns-winnt-fpo_data) .

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
