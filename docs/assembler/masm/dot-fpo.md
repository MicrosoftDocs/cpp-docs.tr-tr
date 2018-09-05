---
title: . FPO | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .FPO
dev_langs:
- C++
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be5e20716ff414eea3eddc8490e2a3f82adeb777
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43687751"
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