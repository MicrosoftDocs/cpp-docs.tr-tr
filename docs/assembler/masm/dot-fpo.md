---
title: .FPO
ms.date: 11/05/2019
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: 3938d9194c35d567ea670e0b92a731193ccd2254
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703791"
---
# <a name="fpo-32-bit-masm"></a>. D (32-bit masa)

İçin. IBU yönergesi, hata ayıklama $ F segmentine veya bölümüne hata ayıklama kayıtlarını denetler. (yalnızca 32-bit masa.)

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
