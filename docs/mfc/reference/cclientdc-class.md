---
title: CClientDC sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CClientDC
- AFXWIN/CClientDC
- AFXWIN/CClientDC::CClientDC
- AFXWIN/CClientDC::m_hWnd
dev_langs:
- C++
helpviewer_keywords:
- CClientDC [MFC], CClientDC
- CClientDC [MFC], m_hWnd
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c51e252157b90423b35152c10a85f972feace72
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348913"
---
# <a name="cclientdc-class"></a>CClientDC sınıfı
Windows işlevlerini çağırma mvc'deki [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871) oluşturma zamanında ve [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920) yok etme zaman.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CClientDC : public CDC  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CClientDC::CClientDC](#cclientdc)|Oluşturan bir `CClientDC` bağlı nesne `CWnd`.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CClientDC::m_hWnd](#m_hwnd)|`HWND` Bu penceresinin `CClientDC` geçerlidir.|  
  
## <a name="remarks"></a>Açıklamalar  
 İle ilişkili cihaz bağlamı buna bir `CClientDC` penceresinin istemci alanını nesnesidir.  
  
 Daha fazla bilgi için `CClientDC`, bkz: [cihaz bağlamları](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CClientDC`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="cclientdc"></a>  CClientDC::CClientDC  
 Oluşturan bir `CClientDC` istemci alanını erişen nesne [CWnd](../../mfc/reference/cwnd-class.md) gösterdiği `pWnd`.  
  
```  
explicit CClientDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWnd`  
 Pencere istemci alanını aygıt bağlam nesnesi erişim sağlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturucu Windows işlevini çağırır [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871).  
  
 Bir özel durum (tür `CResourceException`), oluşturulan Windows `GetDC` çağrısı başarısız. Windows zaten tüm kullanılabilir cihaz bağlamları ayrılmış sahip değilse, bir cihaz bağlamı kullanılamayabilir. Görüntü bağlamları beş ortak herhangi bir zamanda Windows altında bulunabilir için uygulamanızı rekabet.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#42](../../mfc/codesnippet/cpp/cclientdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>  CClientDC::m_hWnd  
 `HWND` , `CWnd` Oluşturmak için kullanılan işaretçi `CClientDC` nesnesi.  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `m_hWnd` korumalı bir değişkendir.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CClientDC::CClientDC](#cclientdc).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek MDI](../../visual-cpp-samples.md)   
 [CDC sınıfı](../../mfc/reference/cdc-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CDC Sınıfı](../../mfc/reference/cdc-class.md)
