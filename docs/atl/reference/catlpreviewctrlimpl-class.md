---
title: "CAtlPreviewCtrlImpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Create
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Destroy
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Focus
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::OnPaint
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Redraw
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetHost
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetPreviewVisuals
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetRect
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::DoPaint
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_plf
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_clrBack
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_clrText
dev_langs: C++
helpviewer_keywords: CAtlPreviewCtrlImpl class
ms.assetid: 39b3299e-07e4-4abc-9b6e-b54bfa3b0802
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 281bc00e46cf28f7cc7d5f1e072fd41ad4cce61a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="catlpreviewctrlimpl-class"></a>CAtlPreviewCtrlImpl sınıfı
Bu sınıf bir kabuk tarafından sağlanan Zengin Önizleme için bir konak pencereyi yerleştirildiği bir pencere ATL uygulamasıdır.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CAtlPreviewCtrlImpl : public CWindowImpl<CAtlPreviewCtrlImpl>, public IPreviewCtrl;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl:: ~ CAtlPreviewCtrlImpl](#dtor)|Önizleme denetim nesnesi destructs.|  
|[CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl](#catlpreviewctrlimpl)|Önizleme denetim nesnesi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::Create](#create)|Windows penceresi oluşturmak için Zengin Önizleme işleyicisi tarafından çağrılır.|  
|[CAtlPreviewCtrlImpl::Destroy](#destroy)|Bu denetim yok etmek gerektiğinde bir Zengin Önizleme işleyicisi tarafından çağrılır.|  
|[CAtlPreviewCtrlImpl::Focus](#focus)|Ayarlar, bu denetim odağı girin.|  
|[CAtlPreviewCtrlImpl::OnPaint](#onpaint)|WM_PAINT yapılacak işler.|  
|[CAtlPreviewCtrlImpl::Redraw](#redraw)|Bu denetim yeniden boyutlandırmaya söyler.|  
|[CAtlPreviewCtrlImpl::SetHost](#sethost)|Bu denetim için yeni bir üst öğe olarak ayarlar.|  
|[CAtlPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|Zengin Önizleme görselleri ayarlamak gerektiğinde bir Zengin Önizleme işleyicisi tarafından içerik çağrılır.|  
|[CAtlPreviewCtrlImpl::SetRect](#setrect)|Bu denetim için yeni bir sınırlayıcı dikdörtgenini ayarlar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::DoPaint](#dopaint)|Önizleme işlemek için çerçevesi tarafından çağrılır.|  
  
### <a name="protected-constants"></a>Korumalı sabitleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::m_plf](#m_plf)|Metni Önizleme penceresinde görüntülemek için kullanılan yazıtipi.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::m_clrBack](#m_clrback)|Önizleme penceresi arka plan rengi.|  
|[CAtlPreviewCtrlImpl::m_clrText](#m_clrtext)|Önizleme penceresi metin rengi.|  

  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `TBase`  
  
 `ATL::CMessageMap`  
  
 `ATL::CWindowImplRoot<TBase>`  
  
 `ATL::CWindowImplBaseT<TBase,TWinTraits>`  
  
 [ATL::CWindowImpl\<CAtlPreviewCtrlImpl >](../../atl/reference/cwindowimpl-class.md)  
  
 `IPreviewCtrl`  
  
 `ATL::CAtlPreviewCtrlImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlpreviewctrlimpl.h  
  
##  <a name="catlpreviewctrlimpl"></a>CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl  
 Önizleme denetim nesnesi oluşturur.  
  
```
CAtlPreviewCtrlImpl(void) : m_clrText(0),
   m_clrBack(RGB(255, 255, 255)), m_plf(NULL);
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="dtor"></a>CAtlPreviewCtrlImpl:: ~ CAtlPreviewCtrlImpl  
 Önizleme denetim nesnesi destructs.  
  
```
virtual ~CAtlPreviewCtrlImpl(void);
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="create"></a>CAtlPreviewCtrlImpl::Create  
 Windows penceresi oluşturmak için Zengin Önizleme işleyicisi tarafından çağrılır.  
  
```
virtual BOOL Create(HWND hWndParent, const RECT* prc);
```  
  
### <a name="parameters"></a>Parametreler  
 `hWndParent`  
 Kabuk tarafından sağlanan Zengin Önizleme için konak penceresi için bir tanıtıcı.  
  
 `prc`  
 Başlangıç boyutu ve pencere konumunu belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="destroy"></a>CAtlPreviewCtrlImpl::Destroy  
 Bu denetim yok etmek gerektiğinde bir Zengin Önizleme işleyicisi tarafından çağrılır.  
  
```
virtual void Destroy();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="dopaint"></a>CAtlPreviewCtrlImpl::DoPaint  
 Önizleme işlemek için çerçevesi tarafından çağrılır.  
  
```
virtual void DoPaint(HDC hdc);
```  
  
### <a name="parameters"></a>Parametreler  
 `hdc`  
 Boyama için cihaz bağlamı için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="focus"></a>CAtlPreviewCtrlImpl::Focus  
 Ayarlar, bu denetim odağı girin.  
  
```
virtual void Focus();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_clrback"></a>CAtlPreviewCtrlImpl::m_clrBack  
 Önizleme penceresi arka plan rengi.  
  
```
COLORREF m_clrBack;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_clrtext"></a>CAtlPreviewCtrlImpl::m_clrText  
 Önizleme penceresi metin rengi.  
  
```
COLORREF m_clrText;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_plf"></a>CAtlPreviewCtrlImpl::m_plf  
 Metni Önizleme penceresinde görüntülemek için kullanılan yazıtipi.  
  
```
const LOGFONTW* m_plf;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onpaint"></a>CAtlPreviewCtrlImpl::OnPaint  
 WM_PAINT yapılacak işler.  
  
```
LRESULT OnPaint(  
    UINT nMsg,
    WPARAM wParam,
    LPARAM lParam,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>Parametreler  
 `nMsg`  
 WM_PAINT için ayarlayın.  
  
 `wParam`  
 Bu parametre kullanılmaz.  
  
 `lParam`  
 Bu parametre kullanılmaz.  
  
 `bHandled`  
 Bu işlev geri döndüğünde, içerdiği `TRUE`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman 0 döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="redraw"></a>CAtlPreviewCtrlImpl::Redraw  
 Bu denetim yeniden boyutlandırmaya söyler.  
  
```
virtual void Redraw();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="sethost"></a>CAtlPreviewCtrlImpl::SetHost  
 Bu denetim için yeni bir üst öğe olarak ayarlar.  
  
```
virtual void SetHost(HWND hWndParent);
```  
  
### <a name="parameters"></a>Parametreler  
 `hWndParent`  
 Yeni üst pencere için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setpreviewvisuals"></a>CAtlPreviewCtrlImpl::SetPreviewVisuals  
 Zengin Önizleme görselleri ayarlamak gerektiğinde bir Zengin Önizleme işleyicisi tarafından içerik çağrılır.  
  
```
virtual void SetPreviewVisuals(
    COLORREF clrBack,
    COLORREF clrText,
    const LOGFONTW* plf);
```  
  
### <a name="parameters"></a>Parametreler  
 `clrBack`  
 Önizleme penceresi arka plan rengi.  
  
 `clrText`  
 Önizleme penceresi metin rengi.  
  
 `plf`  
 Metni Önizleme penceresinde görüntülemek için kullanılan yazıtipi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setrect"></a>CAtlPreviewCtrlImpl::SetRect  
 Bu denetim için yeni bir sınırlayıcı dikdörtgenini ayarlar.  
  
```
virtual void SetRect(const RECT* prc, BOOL bRedraw);
```  
  
### <a name="parameters"></a>Parametreler  
 `prc`  
 Önizleme denetimin konumunu ve yeni boyutunu belirtir.  
  
 `bRedraw`  
 Denetim yeniden olup olmadığını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL COM Masaüstü bileşenleri](../../atl/atl-com-desktop-components.md)
