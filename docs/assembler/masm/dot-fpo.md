---
title: .FPO
ms.date: 08/30/2018
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: b793b3efa72a676b800c10b98ea06001ddcf10d5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491430"
---
# <a name="fpo"></a>.FPO

İçin. IBU yönergesi, hata ayıklama $ F segmentine veya bölümüne hata ayıklama kayıtlarını denetler.

## <a name="syntax"></a>Sözdizimi

> Mı (*Cdwyereller*, *cdwparams*, *cbprolog*, *cbregs*, *fusebp*, *cbframe*)

### <a name="parameters"></a>Parametreler

*Cdwyereller*<br/>
İşaretsiz 32 bitlik bir değer olan yerel değişkenlerin sayısı.

*cdwParams*<br/>
DWORD içindeki parametrelerin boyutu, işaretsiz 16 bit değeri.

*cbProlog*<br/>
İşlev giriş kodundaki bayt sayısı, işaretsiz 8 bit değeri.

*cbRegs*<br/>
Numara kayıtları kaydedildi.

*fUseBP*<br/>
EBP kaydının ayrılıp ayrılmadığını belirtir. 0 ya da 1.

*cbFrame*<br/>
Çerçeve türünü gösterir.  Daha fazla bilgi için bkz. [FPO_DATA](/windows/win32/api/winnt/ns-winnt-fpo_data) .

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>
