---
description: 'Daha fazla bilgi edinin: Cotacontrolmodule sınıfı'
title: Cotacontrolmodule sınıfı
ms.date: 11/04/2016
f1_keywords:
- OleControlModule
helpviewer_keywords:
- OLE control modules [MFC]
- MFC ActiveX controls [MFC], OLE control modules
- COleControlModule class [MFC]
- control modules [MFC]
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
ms.openlocfilehash: f88296b7c0e897f82227343b31ca2f639902256e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227487"
---
# <a name="colecontrolmodule-class"></a>Cotacontrolmodule sınıfı

OLE denetim modülü nesnesi türettiğiniz temel sınıf.

## <a name="syntax"></a>Syntax

```
class COleControlModule : public CWinApp
```

## <a name="remarks"></a>Açıklamalar

Bu sınıf, denetim modülünüzü başlatmak için üye işlevleri sağlar. Microsoft Foundation sınıflarını kullanan her OLE denetim modülü, öğesinden türetilmiş bir nesne içerebilir `COleControlModule` . Bu nesne, diğer C++ Global nesneleri oluşturulduğunda oluşturulur. Türetilmiş `COleControlModule` nesneniz genel düzeyde bildirin.

Sınıfını kullanma hakkında daha fazla bilgi için `COleControlModule` bkz. [CWinApp](../../mfc/reference/cwinapp-class.md) sınıfı ve [ActiveX denetimleri](../../mfc/mfc-activex-controls.md)makalesi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWinThread](../../mfc/reference/cwinthread-class.md)

[CWinApp](../../mfc/reference/cwinapp-class.md)

`COleControlModule`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxctl. h

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek TESTHELP](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
