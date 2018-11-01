---
title: COleControlModule sınıfı
ms.date: 11/04/2016
f1_keywords:
- OleControlModule
helpviewer_keywords:
- OLE control modules [MFC]
- MFC ActiveX controls [MFC], OLE control modules
- COleControlModule class [MFC]
- control modules [MFC]
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
ms.openlocfilehash: a2480407ddb9f937b0691f3e07103eb159fea8b6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50556396"
---
# <a name="colecontrolmodule-class"></a>COleControlModule sınıfı

Bir OLE denetim modülü nesnesi türettiğiniz taban sınıfı.

## <a name="syntax"></a>Sözdizimi

```
class COleControlModule : public CWinApp
```

## <a name="remarks"></a>Açıklamalar

Bu sınıf, denetim modülü başlatmak için üye işlevleri sağlar. Microsoft Foundation sınıfları kullanan her bir OLE denetim modülü yalnızca türetilen bir nesne içerebilir `COleControlModule`. Diğer C++ genel nesneler oluşturulduğunda bu nesne oluşturulur. Türetilmiş bildirmek `COleControlModule` genel düzeyde nesne.

Kullanma hakkında daha fazla bilgi için `COleControlModule` sınıfı [CWinApp](../../mfc/reference/cwinapp-class.md) sınıfı ve makale [ActiveX denetimlerini](../../mfc/mfc-activex-controls.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWinThread](../../mfc/reference/cwinthread-class.md)

[CWinApp](../../mfc/reference/cwinapp-class.md)

`COleControlModule`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxctl.h

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek TESTHELP](../../visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

