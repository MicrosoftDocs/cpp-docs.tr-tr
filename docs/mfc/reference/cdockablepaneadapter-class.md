---
title: CDockablePaneAdapter sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDockablePaneAdapter
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::GetWrappedWnd
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::LoadState
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::SaveState
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::SetWrappedWnd
dev_langs:
- C++
helpviewer_keywords:
- CDockablePaneAdapter [MFC], GetWrappedWnd
- CDockablePaneAdapter [MFC], LoadState
- CDockablePaneAdapter [MFC], SaveState
- CDockablePaneAdapter [MFC], SetWrappedWnd
ms.assetid: 6ed6cf82-f39c-4d0c-bf7c-8641495cf8f3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 196264f417874904e0aba4df815d42e4e50d690d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43205047"
---
# <a name="cdockablepaneadapter-class"></a>CDockablePaneAdapter sınıfı
İçin yerleştirme desteği sağlar `CWnd`-bölmeler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDockablePaneAdapter : public CDockablePane  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDockablePaneAdapter::GetWrappedWnd](#getwrappedwnd)|Sarmalanan pencereyi döndürür.|  
|[CDockablePaneAdapter::LoadState](#loadstate)|(Geçersiz kılmaları [CDockablePane::LoadState](https://msdn.microsoft.com/96110136-4f46-4764-8a76-3b4abaf77917).)|  
|[CDockablePaneAdapter::SaveState](#savestate)|(Geçersiz kılmaları [CDockablePane::SaveState](https://msdn.microsoft.com/c5c24249-8d0d-46cb-96d9-9f5c6dc191db).)|  
|[CDockablePaneAdapter::SetWrappedWnd](#setwrappedwnd)||  
  
## <a name="remarks"></a>Açıklamalar  
 Genellikle, framework kullandığınızda bu sınıfın nesneleri başlatır [CMFCBaseTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) veya [CMFCBaseTabCtrl::InsertTab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab) yöntemleri.  
  
 Özelleştirmek istiyorsanız `CDockablePaneAdapter` davranışı, yalnızca yeni bir sınıf türetmeniz ve çalışma zamanı sınıf bilgileri kullanarak sekmeli pencere ayarlamak [CMFCBaseTabCtrl::SetDockingBarWrapperRTC](../../mfc/reference/cmfcbasetabctrl-class.md#setdockingbarwrapperrtc).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxDockablePaneAdapter.h  
  
##  <a name="getwrappedwnd"></a>  CDockablePaneAdapter::GetWrappedWnd  
 Yerleştirilebilir bölmesinde bağdaştırıcısı için temel alınan pencereyi döndürür.  
  
```  
virtual CWnd* GetWrappedWnd() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sarmalanan penceresine bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Sarmalanan penceresine erişmek için bu işlevi kullanın.  
  
##  <a name="loadstate"></a>  CDockablePaneAdapter::LoadState  
 Kayıt defterinden bölmesinde durumunu yükler.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszProfileName*  
 Profil adı.  
  
 [in] *nIndex*  
 Profili dizini.  
  
 [in] *uiID*  
 Bölmesinde kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="savestate"></a>  CDockablePaneAdapter::SaveState  
 Kayıt defterine bölmesinde durumunu kaydeder.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszProfileName*  
 Profil adı.  
  
 [in] *nIndex*  
 Profili dizini (varsayılan pencere denetim kimliği olarak).  
  
 [in] *uiID*  
 Bölmesinde kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setwrappedwnd"></a>  CDockablePaneAdapter::SetWrappedWnd  
 Alttaki pencerenin yerleştirilebilir bölmesinde bağdaştırıcı için ayarlar.  
  
```  
virtual BOOL SetWrappedWnd(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pWnd*  
 Sarılacak bölmesinde bağdaştırıcısı penceresine bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CDockablePane Sınıfı](../../mfc/reference/cdockablepane-class.md)
