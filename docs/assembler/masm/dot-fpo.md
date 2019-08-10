---
title: .FPO
ms.date: 08/30/2018
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: 3bdb6af98aa71fef3d4af24091dc7463d917ce15
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915957"
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
Çerçeve türünü gösterir.  Daha fazla bilgi için bkz. [FPO_DATA](/windows/desktop/api/winnt/ns-winnt-fpo_data) .

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>
