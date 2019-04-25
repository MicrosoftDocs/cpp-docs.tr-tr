---
title: .FPO
ms.date: 08/30/2018
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: 83d6e81ea7dd35038f27f2721f3cc41fe49ef1bc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62204064"
---
# <a name="fpo"></a>.FPO

. FPO yönergesi, hata ayıklama kayıtlarını .debug$ F segment veya bölüm yayımlanmasını denetler.

## <a name="syntax"></a>Sözdizimi

> FPO (*cdwLocals*, *cdwParams*, *cbProlog*, *cbRegs*, *fUseBP*, *cbFrame*)

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