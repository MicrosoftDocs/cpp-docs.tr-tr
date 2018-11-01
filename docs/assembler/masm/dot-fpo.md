---
title: .FPO
ms.date: 08/30/2018
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: 83d6e81ea7dd35038f27f2721f3cc41fe49ef1bc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570518"
---
# <a name="fpo"></a>.FPO

. FPO yönergesi, hata ayıklama kayıtlarını .debug$ F segment veya bölüm yayımlanmasını denetler.

## <a name="syntax"></a>Sözdizimi

> FPO (*cdwLocals*, *cdwParams*, *cbProlog*, *cbRegs*, *fUseBP*,  *cbFrame*)

### <a name="parameters"></a>Parametreler

*cdwLocals*<br/>
Yerel değişkenler, bir işaretsiz 32 bit değeri sayısı.

*cdwParams*<br/>
DWORD, işaretsiz 16 bit değeri parametrelerinde boyutu.

*cbProlog*<br/>
İmzalanmamış 8 bit bir değer işlev giriş kodunun bayt sayısı.

*cbRegs*<br/>
Kaydedilmiş Yazmaçlar numarası.

*fUseBP*<br/>
EBP kayıt ayrılmış olup olmadığını gösterir. 0 veya 1.

*cbFrame*<br/>
Çerçeve türünü gösterir.  Bkz: [FPO_DATA](/windows/desktop/api/winnt/ns-winnt-_fpo_data) daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>