---
title: "CWindowDC sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWindowDC
- AFXWIN/CWindowDC
- AFXWIN/CWindowDC::CWindowDC
- AFXWIN/CWindowDC::m_hWnd
dev_langs:
- C++
helpviewer_keywords:
- CWindowDC [MFC], CWindowDC
- CWindowDC [MFC], m_hWnd
ms.assetid: 876a3641-4cde-471c-b0d1-fe58b32af79c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9bc3219ff6570fab18b19f350f7dca3171ab4832
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cwindowdc-class"></a>CWindowDC sınıfı
Türetilmiş `CDC`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CWindowDC : public CDC  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWindowDC::CWindowDC](#cwindowdc)|Oluşturan bir `CWindowDC` nesnesi.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWindowDC::m_hWnd](#m_hwnd)|`HWND` Bu `CWindowDC` eklenir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Windows işlev çağrılarını [GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947\(v=vs.85\).aspx)oluşturma zamanında ve [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920\(v=vs.85\).aspx) yok etme zaman. Bunun anlamı bir `CWindowDC` nesne erişen tüm ekran alanını bir [CWnd](../../mfc/reference/cwnd-class.md) (hem istemci hem de nonclient alanlar).  
  
 Kullanma hakkında daha fazla bilgi için `CWindowDC`, bkz: [cihaz bağlamları](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CWindowDC`  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: afxwin.h  
  
##  <a name="cwindowdc"></a>CWindowDC::CWindowDC  
 Oluşturan bir `CWindowDC` (hem istemci hem de nonclient) tüm ekran alanını erişen nesne `CWnd` tarafından için nesne işaret `pWnd`.  
  
```  
explicit CWindowDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWnd`  
 Pencere istemci alanını cihaz bağlamı nesne erişim sağlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturucu Windows işlevini çağırır [GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947).  
  
 Bir özel durum (tür `CResourceException`), oluşturulan Windows `GetWindowDC` çağrısı başarısız. Windows zaten tüm kullanılabilir cihaz bağlamları ayrılmış sahip değilse, bir cihaz bağlamı kullanılamayabilir. Görüntü bağlamları beş ortak herhangi bir zamanda Windows altında bulunabilir için uygulamanızı rekabet.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#188](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>CWindowDC::m_hWnd  
 `HWND` , `CWnd` İşaretçi oluşturmak için kullanılan `CWindowDC` nesnesi.  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `m_hWnd`korumalı bir değişken türü `HWND`.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CWindowDC::CWindowDC](#cwindowdc).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDC sınıfı](../../mfc/reference/cdc-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CDC Sınıfı](../../mfc/reference/cdc-class.md)
