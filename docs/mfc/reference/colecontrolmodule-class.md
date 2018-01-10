---
title: "COleControlModule sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: OleControlModule
dev_langs: C++
helpviewer_keywords:
- OLE control modules [MFC]
- MFC ActiveX controls [MFC], OLE control modules
- COleControlModule class [MFC]
- control modules [MFC]
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 196b69a0d86c3809415e030adb567c8642051f40
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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



