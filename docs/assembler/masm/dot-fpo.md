---
title: .FPO
ms.date: 11/05/2019
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: 650c69be17c9271c343360edbb90f093841a1047
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398252"
---
# <a name="fpo-32-bit-masm"></a>. D (32-bit masa)

**. IBU yönergesi,** hata ayıklama $ F segmentine veya bölümüne hata ayıklama kayıtlarını denetler. (yalnızca 32-bit masa.)

## <a name="syntax"></a>Sözdizimi

> **.** Mı (*cdwyereller*, *cdwparams*, *cbprolog*, *cbregs*, *fusebp*, *cbframe*)

### <a name="parameters"></a>Parametreler

*Cdwyereller*\
İşaretsiz 32 bitlik bir değer olan yerel değişkenlerin sayısı.

*Cdwparams*\
DWORD içindeki parametrelerin boyutu, işaretsiz 16 bit değeri.

*Cbprolog*\
İşlev giriş kodundaki bayt sayısı, işaretsiz 8 bit değeri.

*Cbregs*\
Numara kayıtları kaydedildi.

*Fusebp*\
EBP kaydının ayrılıp ayrılmadığını belirtir. 0 ya da 1.

*Cbframe*\
Çerçeve türünü gösterir.  Daha fazla bilgi için bkz. [FPO_DATA](/windows/win32/api/winnt/ns-winnt-fpo_data) .

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)
