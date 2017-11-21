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
ms.openlocfilehash: 0153adbae458d0f4ab432c2c7cb8c71621d76418
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)



