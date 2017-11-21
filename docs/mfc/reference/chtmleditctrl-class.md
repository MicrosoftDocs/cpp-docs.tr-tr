---
title: "CHtmlEditCtrl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl::CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl::Create
- AFXHTML/CHtmlEditCtrl::GetDHtmlDocument
- AFXHTML/CHtmlEditCtrl::GetStartDocument
dev_langs: C++
helpviewer_keywords:
- CHtmlEditCtrl [MFC], CHtmlEditCtrl
- CHtmlEditCtrl [MFC], Create
- CHtmlEditCtrl [MFC], GetDHtmlDocument
- CHtmlEditCtrl [MFC], GetStartDocument
ms.assetid: 0fc4a238-b05f-4874-9edc-6a6701f064d9
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e18c2b38215e75d6fe12b1c78c93d3d9fe147df9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="chtmleditctrl-class"></a>CHtmlEditCtrl sınıfı
Bir MFC penceresinde WebBrowser ActiveX denetiminin işlevsellik sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CHtmlEditCtrl: public CWnd,   
    public CHtmlEditCtrlBase<CHtmlEditCtrl>  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHtmlEditCtrl::CHtmlEditCtrl](#chtmleditctrl)|Oluşturan bir `CHtmlEditCtrl` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHtmlEditCtrl::Create](#create)|WebBrowser ActiveX denetimi oluşturur ve ona ekler `CHtmlEditCtrl` nesnesi. Bu işlev, otomatik olarak WebBrowser ActiveX denetimini düzenleme moduna geçirir.|  
|[CHtmlEditCtrl::GetDHtmlDocument](#getdhtmldocument)|Alır [Ihtmldocument2](https://msdn.microsoft.com/library/aa752574.aspx) belge arabirimde, içerilen WebBrowser denetimi şu anda yüklü.|  
|[CHtmlEditCtrl::GetStartDocument](#getstartdocument)|Kapsanan WebBrowser denetimi yüklemek için varsayılan bir belge için URL alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Oluşturulduktan sonra barındırılan WebBrowser denetimi otomatik olarak içine konur düzenleme modunda.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHtmlEditCtrl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxhtml.h  
  
##  <a name="chtmleditctrl"></a>CHtmlEditCtrl::CHtmlEditCtrl  
 Oluşturan bir `CHtmlEditCtrl` nesnesi.  
  
```  
CHtmlEditCtrl();
```  
  
##  <a name="create"></a>CHtmlEditCtrl::Create  
 WebBrowser ActiveX denetimi oluşturur ve ona ekler `CHtmlEditCtrl` nesnesi. Bu işlev tarafından WebBrowser denetimi otomatik olarak bir varsayılan belge gider ve ardından yerleştirilir ActiveX düzenleme modunda.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszWindowName`  
 Bu parametre kullanılmıyor.  
  
 `dwStyle`  
 Bu parametre kullanılmıyor.  
  
 `rect`  
 Denetimin boyutunu ve konumunu belirtir.  
  
 `pParentWnd`  
 Denetimin üst penceresi belirtir. Değil olmalıdır **NULL**.  
  
 `nID`  
 Denetimin kimliğini belirtir.  
  
 `pContext`  
 Bu parametre kullanılmıyor.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
##  <a name="getdhtmldocument"></a>CHtmlEditCtrl::GetDHtmlDocument  
 Alır [Ihtmldocument2](https://msdn.microsoft.com/library/aa752574.aspx) arabirimi belge üzerinde şu anda yüklü, içerilen WebBrowser denetimi  
  
```  
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `ppDocument`  
 Belge arabirimi.  
  
##  <a name="getstartdocument"></a>CHtmlEditCtrl::GetStartDocument  
 Kapsanan WebBrowser denetimi yüklemek için varsayılan bir belge için URL alır.  
  
```  
virtual LPCTSTR GetStartDocument();
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)

