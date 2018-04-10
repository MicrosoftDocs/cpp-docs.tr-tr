---
title: CWndClassInfo sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- CWndClassInfo
- ATLWIN/ATL::CWndClassInfo
- ATLWIN/ATL::Register
- ATLWIN/ATL::m_atom
- ATLWIN/ATL::m_bSystemCursor
- ATLWIN/ATL::m_lpszCursorID
- ATLWIN/ATL::m_lpszOrigName
- ATLWIN/ATL::m_szAutoName
- ATLWIN/ATL::m_wc
- ATLWIN/ATL::pWndProc
dev_langs:
- C++
helpviewer_keywords:
- CWndClassInfo class
ms.assetid: c36fe7e1-75f1-4cf5-a06f-9f59c43fe6fb
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b07f6b12914e18f3f83abedf59742a8b7c7867b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cwndclassinfo-class"></a>CWndClassInfo sınıfı
Bu sınıf için bir pencere sınıfı bilgileri kaydetmek için yöntemleri sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CWndClassInfo
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|||  
|-|-|  
|[Kaydetme](#register)|Pencere sınıfı kaydeder.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|[m_atom](#m_atom)|Kayıtlı pencere sınıfı benzersiz olarak tanımlar.|  
|[m_bSystemCursor](#m_bsystemcursor)|İmleç kaynak sistem imleç veya modülü kaynağında bulunan bir imleç başvuruda olup olmadığını belirtir.|  
|[m_lpszCursorID](#m_lpszcursorid)|İmleç kaynağın adını belirtir.|  
|[m_lpszOrigName](#m_lpszorigname)|Varolan bir pencere sınıfı adını içerir.|  
|[m_szAutoName](#m_szautoname)|ATL oluşturulan bir pencere sınıfı adını içerir.|  
|[m_wc](#m_wc)|Pencere sınıfı bilgileri tutan bir **WNDCLASSEX** yapısı.|  
|[pWndProc](#pwndproc)|Pencere yordamı noktalarına mevcut bir pencere sınıfın.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CWndClassInfo`pencere sınıfı bilgilerini yönetir. Tipik olarak kullandığınız `CWndClassInfo` üç makroları biri aracılığıyla `DECLARE_WND_CLASS`, `DECLARE_WND_CLASS_EX`, veya `DECLARE_WND_SUPERCLASS`aşağıdaki tabloda açıklandığı gibi:  
  
|Makrosu|Açıklama|  
|-----------|-----------------|  
|[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)|`CWndClassInfo`Yeni bir pencere sınıfı için bilgileri kaydeder.|  
|[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)|`CWndClassInfo`bilgi sınıfı parametreleri de dahil olmak üzere yeni bir pencere sınıfı için kaydeder.|  
|[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)|`CWndClassInfo`Varolan bir sınıfına dayalı ancak farklı pencere yordamı kullanan bir pencere sınıfı için bilgileri kaydeder. Bu teknik üst Sınıflama adı verilir.|  
  
 Varsayılan olarak, [CWindowImpl](../../atl/reference/cwindowimpl-class.md) içeren `DECLARE_WND_CLASS` makrosu bir pencere oluşturmak için temel üzerinde yeni bir pencere sınıfı. DECLARE_WND_CLASS varsayılan stillerini ve arka plan rengi için denetim sağlar. Stil belirtin ve kendiniz arka plan rengi istiyorsanız, sınıfından türetilen `CWindowImpl` ve dahil `DECLARE_WND_CLASS_EX` makrosu sınıf tanımında.  
  
 Varolan bir pencere sınıfına dayalı bir pencere oluşturmak istiyorsanız, sınıfından türetilen `CWindowImpl` ve dahil `DECLARE_WND_SUPERCLASS` makrosu sınıf tanımında. Örneğin:  
  
 [!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwndclassinfo-class_1.h)]  
  
 Pencere sınıfları hakkında daha fazla bilgi için bkz: [pencere sınıfları](http://msdn.microsoft.com/library/windows/desktop/ms632596) Windows SDK'sındaki.  
  
 ATL Windows'da kullanma hakkında daha fazla bilgi için bkz: [ATL pencere sınıfları](../../atl/atl-window-classes.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
  
##  <a name="m_atom"></a>CWndClassInfo::m_atom  
 Kayıtlı pencere sınıfı için benzersiz tanımlayıcı içerir.  
  
```
ATOM m_atom;
```  
  
##  <a name="m_bsystemcursor"></a>CWndClassInfo::m_bSystemCursor  
 Varsa **doğru**, pencere sınıfı kaydedildikten sonra sistem imleç kaynak yüklenecek.  
  
```
BOOL m_bSystemCursor;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Aksi takdirde, modülünde yer alan imleç kaynak yüklenecektir.  
  
 `CWndClassInfo`kullanan `m_bSystemCursor` yalnızca [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (varsayılan olarak [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) veya [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) makrosu belirtilir. Bu durumda, `m_bSystemCursor` için başlatılan **doğru**. Daha fazla bilgi için bkz: [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) genel bakış.  
  
##  <a name="m_lpszcursorid"></a>CWndClassInfo::m_lpszCursorID  
 Düşük düzey word ve yüksek düzey Word'de sıfır imleç kaynağın adını ya da kaynak tanımlayıcı belirtir.  
  
```
LPCTSTR m_lpszCursorID;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Pencere sınıfı kaydettirildiğini, imleci tarafından tanımlanan tanıtıcısını `m_lpszCursorID` alınır ve tarafından depolanan [m_wc](#m_wc).  
  
 `CWndClassInfo`kullanan `m_lpszCursorID` yalnızca [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (varsayılan olarak [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) veya [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) makrosu belirtilir. Bu durumda, `m_lpszCursorID` için başlatılan **IDC_ARROW**. Daha fazla bilgi için bkz: [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) genel bakış.  
  
##  <a name="m_lpszorigname"></a>CWndClassInfo::m_lpszOrigName  
 Varolan bir pencere sınıfı adını içerir.  
  
```
LPCTSTR m_lpszOrigName;
```  
  
### <a name="remarks"></a>Açıklamalar  
 `CWndClassInfo`kullanan `m_lpszOrigName` yalnızca dahil ettiğinizde [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) makrosu sınıf tanımında. Bu durumda, `CWndClassInfo` pencere sınıfı tarafından adlı sınıf temel kayıtları `m_lpszOrigName`. Daha fazla bilgi için bkz: [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) genel bakış.  
  
##  <a name="m_szautoname"></a>CWndClassInfo::m_szAutoName  
 Pencere sınıfı adını içerir.  
  
```
TCHAR m_szAutoName[13];
```  
  
### <a name="remarks"></a>Açıklamalar  
 `CWndClassInfo`kullanan `m_szAutoName` yalnızca **NULL** geçirilen `WndClassName` parametresi [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class), [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) veya [ DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass). Pencere sınıfı kaydedildiğinde ATL bir ad oluşturun.  
  
##  <a name="m_wc"></a>CWndClassInfo::m_wc  
 Pencere sınıfı bilgileri tutan bir [WNDCLASSEX](http://msdn.microsoft.com/library/windows/desktop/ms633577) yapısı.  
  
```
WNDCLASSEX m_wc;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Belirttiyseniz [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (varsayılan olarak [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) veya [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) makrosu, `m_wc` hakkında bilgi içeren bir Yeni pencere sınıfı.  
  
 Belirttiyseniz [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) makrosu, `m_wc` bir üst sınıf hakkında bilgi içerir — varolan bir sınıfına dayalı ancak farklı pencere yordamı kullanan bir pencere sınıfı. [m_lpszOrigName](#m_lpszorigname) ve [pWndProc](#pwndproc) varolan penceresi sınıfın adını ve pencere yordamı, sırasıyla kaydedin.  
  
##  <a name="pwndproc"></a>CWndClassInfo::pWndProc  
 Pencere yordamı noktalarına mevcut bir pencere sınıfın.  
  
```
WNDPROC pWndProc;
```  
  
### <a name="remarks"></a>Açıklamalar  
 `CWndClassInfo`kullanan `pWndProc` yalnızca dahil ettiğinizde [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) makrosu sınıf tanımında. Bu durumda, `CWndClassInfo` var olan bir sınıfına dayalı ancak farklı pencere yordamı kullanan bir pencere sınıfı kaydeder. Varolan penceresi sınıfının pencere yordamı kaydedilir `pWndProc`. Daha fazla bilgi için bkz: [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) genel bakış.  
  
##  <a name="register"></a>CWndClassInfo::Register  
 Tarafından çağrılır [CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create) henüz kayıtlı değilse, pencere sınıfı kaydetmek için.  
  
```
ATOM Register(WNDPROC* pProc);
```  
  
### <a name="parameters"></a>Parametreler  
 `pProc`  
 [out] Mevcut bir pencere sınıfın özgün pencere yordamı belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, atom, benzersiz olarak Kaydedilmekte pencere sınıfı tanımlar. Aksi takdirde, 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirttiyseniz [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (varsayılan olarak [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) veya [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) makrosu, `Register` yeni bir pencere sınıfı kaydeder. Bu durumda, `pProc` parametresi kullanılmaz.  
  
 Belirttiyseniz [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) makrosu, `Register` bir üst sınıf kaydeder — varolan bir sınıfına dayalı ancak farklı pencere yordamı kullanan bir pencere sınıfı. Varolan penceresi sınıfının pencere yordamı döndürülür `pProc`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComControl sınıfı](../../atl/reference/ccomcontrol-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)