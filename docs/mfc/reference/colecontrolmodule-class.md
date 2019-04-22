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
ms.openlocfilehash: f6d486c7bacb897d70d85414ac3d0bd0d13e447b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58780294"
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

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek TESTHELP](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
