---
title: "CPaintDC sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPaintDC
- AFXWIN/CPaintDC
- AFXWIN/CPaintDC::CPaintDC
- AFXWIN/CPaintDC::m_ps
- AFXWIN/CPaintDC::m_hWnd
dev_langs: C++
helpviewer_keywords:
- CPaintDC [MFC], CPaintDC
- CPaintDC [MFC], m_ps
- CPaintDC [MFC], m_hWnd
ms.assetid: 7e245baa-bf9b-403e-a637-7218adf28fab
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 58d1c1ec052c399cf56cd145e7ee06f52483661e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cpaintdc-class"></a>CPaintDC sınıfı
Bir cihaz bağlamı sınıfın türetildiği [CDC](../../mfc/reference/cdc-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CPaintDC : public CDC  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPaintDC::CPaintDC](#cpaintdc)|Oluşturan bir `CPaintDC` belirtilen bağlı [CWnd](../../mfc/reference/cwnd-class.md).|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPaintDC::m_ps](#m_ps)|İçeren [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) istemci alanını boyamak için kullanılan.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPaintDC::m_hWnd](#m_hwnd)|`HWND` Bu `CPaintDC` nesne eklenmiş olmasıdır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Gerçekleştirdiği bir [CWnd::BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint) oluşturma zamanında ve [CWnd::EndPaint](../../mfc/reference/cwnd-class.md#endpaint) yok etme zaman.  
  
 A `CPaintDC` nesnesi, yalnızca için yanıt verirken kullanılabilir bir [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) iletisi, genellikle, `OnPaint` ileti işleyicisi üye işlevi.  
  
 Kullanma hakkında daha fazla bilgi için `CPaintDC`, bkz: [cihaz bağlamları](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CPaintDC`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="cpaintdc"></a>CPaintDC::CPaintDC  
 Oluşturan bir `CPaintDC` nesne, uygulama penceresi boyama için hazırlar ve depolar [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) içinde yapısı [m_ps](#m_ps) üye değişkeni.  
  
```  
explicit CPaintDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWnd`  
 İşaret `CWnd` hangi nesnesine `CPaintDC` nesnesi aittir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir özel durum (tür `CResourceException`), oluşturulan Windows [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871) çağrısı başarısız. Windows zaten tüm kullanılabilir cihaz bağlamları ayrılmış sahip değilse, bir cihaz bağlamı kullanılamayabilir. Görüntü bağlamları beş ortak herhangi bir zamanda Windows altında bulunabilir için uygulamanızı rekabet.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#97](../../mfc/codesnippet/cpp/cpaintdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>CPaintDC::m_hWnd  
 `HWND` Bu `CPaintDC` nesne eklenmiş olmasıdır.  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `m_hWnd`korumalı bir değişken türü `HWND`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#98](../../mfc/codesnippet/cpp/cpaintdc-class_2.cpp)]  
  
##  <a name="m_ps"></a>CPaintDC::m_ps  
 `m_ps`bir ortak üye değişkeni türü [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md).  
  
```  
PAINTSTRUCT m_ps;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu `PAINTSTRUCT` için geçirilen ve tarafından doldurulan [CWnd::BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint).  
  
 `PAINTSTRUCT` Uygulama ile ilişkili penceresinin istemci alanı boyamak için kullandığı bilgileri içeren bir `CPaintDC` nesnesi.  
  
 Cihaz bağlamı tanıtıcısı üzerinden erişebilirsiniz Not `PAINTSTRUCT`. Ancak, tanıtıcı aracılığıyla doğrudan erişebilirsiniz `m_hDC` üye değişkeni, `CPaintDC` devraldığı `CDC`.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPaintDC::m_hWnd](#m_hwnd).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek MDI](../../visual-cpp-samples.md)   
 [CDC sınıfı](../../mfc/reference/cdc-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)



