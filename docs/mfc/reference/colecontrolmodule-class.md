---
title: COleControlModule sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- OleControlModule
dev_langs:
- C++
helpviewer_keywords:
- OLE control modules [MFC]
- MFC ActiveX controls [MFC], OLE control modules
- COleControlModule class [MFC]
- control modules [MFC]
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 597639145385f4aabcba0e83fef855f7a0779f9b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="colecontrolmodule-class"></a>COleControlModule sınıfı
OLE denetim modülü nesnesi türetilen temel sınıf.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleControlModule : public CWinApp  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, denetim modülü başlatma için üye işlevleri sağlar. Microsoft Foundation sınıfları kullanan her bir OLE denetim modülü yalnızca türetilmiş bir nesne içerebilir `COleControlModule`. Diğer C++ genel nesneler oluşturulduğunda bu nesnesi oluşturulur. Türetilmiş bildirme `COleControlModule` genel düzeyde nesne.  
  
 Kullanma hakkında daha fazla bilgi için `COleControlModule` sınıfı için bkz: [CWinApp](../../mfc/reference/cwinapp-class.md) sınıfı ve makale [ActiveX denetimlerini](../../mfc/mfc-activex-controls.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 `COleControlModule`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxctl.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek TESTHELP](../../visual-cpp-samples.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



