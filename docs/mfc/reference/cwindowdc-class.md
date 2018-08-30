---
title: CWindowDC sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 40566ab94c9708d7b31f88de0f96b4fc33675534
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43212527"
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
|[CWindowDC::CWindowDC](#cwindowdc)|Oluşturur bir `CWindowDC` nesne.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWindowDC::m_hWnd](#m_hwnd)|Bu HWND `CWindowDC` eklenir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Windows işlevini çağıran [GetWindowDC](/windows/desktop/api/winuser/nf-winuser-getwindowdc)oluşturma zamanında ve [ReleaseDC](/windows/desktop/api/winuser/nf-winuser-releasedc) yok etme. Diğer bir deyişle bir `CWindowDC` nesne tüm ekran alanına eriştiği bir [CWnd](../../mfc/reference/cwnd-class.md) (hem istemci hem de istemci dışı alanlar).  
  
 Kullanma hakkında daha fazla bilgi için `CWindowDC`, bkz: [cihaz bağlamları](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CWindowDC`  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: afxwin.h  
  
##  <a name="cwindowdc"></a>  CWindowDC::CWindowDC  
 Oluşturur bir `CWindowDC` erişen tüm ekran alanına (hem istemci hem de istemci olmayan) nesne `CWnd` nesne tarafından işaret edilen *pWnd*.  
  
```  
explicit CWindowDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 *pWnd*  
 Penceresinin istemci alanını cihaz bağlamındaki nesne erişim sağlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Windows işlevi oluşturucuyu çağırır [GetWindowDC](/windows/desktop/api/winuser/nf-winuser-getwindowdc).  
  
 Bir özel durum (tür `CResourceException`) oluşturulur Windows `GetWindowDC` çağrısı başarısız olur. Bir cihaz bağlamı Windows zaten tüm kendi kullanılabilir cihaz bağlamları ayırdığı kullanılabilir olmayabilir. Uygulamanız için beş ortak görüntü bağlamlarında kullanılabilir Windows altında herhangi bir belirli zamanda rekabet.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#188](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>  CWindowDC::m_hWnd  
 HWND, `CWnd` işaretçi oluşturmak için kullanılan `CWindowDC` nesne.  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `m_hWnd` HWND türündeki korumalı bir değişkendir.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CWindowDC::CWindowDC](#cwindowdc).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDC sınıfı](../../mfc/reference/cdc-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CDC Sınıfı](../../mfc/reference/cdc-class.md)
