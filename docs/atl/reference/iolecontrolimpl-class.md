---
title: IOleControlImpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IOleControlImpl
- ATLCTL/ATL::IOleControlImpl
- ATLCTL/ATL::IOleControlImpl::FreezeEvents
- ATLCTL/ATL::IOleControlImpl::GetControlInfo
- ATLCTL/ATL::IOleControlImpl::OnAmbientPropertyChange
- ATLCTL/ATL::IOleControlImpl::OnMnemonic
dev_langs:
- C++
helpviewer_keywords:
- IOleControlImpl class
ms.assetid: 5a4255ad-ede4-49ca-ba9a-07c2e919fa85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a54067f53e83d78f063ae5f3694460452e24b26
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="iolecontrolimpl-class"></a>IOleControlImpl sınıfı
Bu sınıf, bir varsayılan uygulamasını sağlar **IOleControl** arabirimi ve uygulayan **IUnknown**.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>
class IOleControlImpl
```   
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `IOleControlImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IOleControlImpl::FreezeEvents](#freezeevents)|Kapsayıcı yoksayar veya denetim olayları kabul olup olmadığını gösterir.|  
|[IOleControlImpl::GetControlInfo](#getcontrolinfo)|Denetimin klavye davranışı hakkında bilgi doldurur. ATL uygulamasını döndürür **E_NOTIMPL**.|  
|[IOleControlImpl::OnAmbientPropertyChange](#onambientpropertychange)|Bir denetim, bir veya daha fazla kapsayıcının ortam özelliklerine değiştiğini bildirir. ATL uygulamasını döndürür `S_OK`.|  
|[IOleControlImpl::OnMnemonic](#onmnemonic)|Denetimi, bir kullanıcının belirtilen bir tuş vuruşu bastığı bildirir. ATL uygulamasını döndürür **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıf `IOleControlImpl` bir varsayılan uygulamayı sağlar [IOleControl](http://msdn.microsoft.com/library/windows/desktop/ms694320) arabirimi ve uygulayan **IUnknown** aygıt hata ayıklama dökümü bilgileri göndererek oluşturur.  
  
 **İlgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [bir ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IOleControl`  
  
 `IOleControlImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
##  <a name="freezeevents"></a>  IOleControlImpl::FreezeEvents  
 ATL'ın uygulamasında `FreezeEvents` denetim sınıfının artırır `m_nFreezeEvents` veri üyesi ise `bFreeze` olan **TRUE**ve azaltır `m_nFreezeEvents` varsa `bFreeze` olan **yanlış**.  
  
```
HRESULT FreezeEvents(BOOL bFreeze);
```  
  
### <a name="remarks"></a>Açıklamalar  
 `FreezeEvents` ardından döndürür `S_OK`.  
  
 Bkz: [IOleControl::FreezeEvents](http://msdn.microsoft.com/library/windows/desktop/ms678482) Windows SDK.  
  
##  <a name="getcontrolinfo"></a>  IOleControlImpl::GetControlInfo  
 Denetimin klavye davranışı hakkında bilgi doldurur.  
  
```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleControl:GetControlInfo](http://msdn.microsoft.com/library/windows/desktop/ms693730) Windows SDK.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **E_NOTIMPL**.  
  
##  <a name="onambientpropertychange"></a>  IOleControlImpl::OnAmbientPropertyChange  
 Bir denetim, bir veya daha fazla kapsayıcının ortam özelliklerine değiştiğini bildirir.  
  
```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleControl::OnAmbientPropertyChange](http://msdn.microsoft.com/library/windows/desktop/ms690175) Windows SDK.  
  
##  <a name="onmnemonic"></a>  IOleControlImpl::OnMnemonic  
 Denetimi, bir kullanıcının belirtilen bir tuş vuruşu bastığı bildirir.  
  
```
HRESULT OnMnemonic(LPMSG pMsg);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **E_NOTIMPL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleControl::OnMnemonic](http://msdn.microsoft.com/library/windows/desktop/ms680699) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IOleObjectImpl sınıfı](../../atl/reference/ioleobjectimpl-class.md)   
 [Arabirimleri ActiveX denetimleri](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
