---
title: Ipointerınactiveımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl::GetActivationPolicy
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveMouseMove
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveSetCursor
dev_langs:
- C++
helpviewer_keywords:
- IPointerInactive ATL implementation
- inactive objects
- IPointerInactiveImpl class
ms.assetid: e1fe9ea6-d38a-4527-9112-eb344771e0b7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5d7c4ed7634cc1818250d8945a057f97c53edffc
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43223205"
---
# <a name="ipointerinactiveimpl-class"></a>Ipointerınactiveımpl sınıfı
Bu sınıfın uyguladığı `IUnknown` ve [Ipointerınactive'i](/windows/desktop/api/ocidl/nn-ocidl-ipointerinactive) arabirim yöntemleri.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>
class IPointerInactiveImpl
```  
  
#### <a name="parameters"></a>Parametreler  
 *T*  
 Sınıfınız, türetilen `IPointerInactiveImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IPointerInactiveImpl::GetActivationPolicy](#getactivationpolicy)|Nesne için geçerli etkinleştirme ilkesini alır. ATL uygulamasını E_NOTIMPL döndürür.|  
|[IPointerInactiveImpl::OnInactiveMouseMove](#oninactivemousemove)|Fareyi üzerine nesneyi gösteren taşındı nesne fare olayları tetikleyebilir bildirir. ATL uygulamasını E_NOTIMPL döndürür.|  
|[IPointerInactiveImpl::OnInactiveSetCursor](#oninactivesetcursor)|Etkin olmayan bir nesne için fare işaretçisini ayarlar. ATL uygulamasını E_NOTIMPL döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 Etkin olmayan bir nesne yalnızca yüklenen veya çalışmıyor biridir. Etkin bir nesne, etkin olmayan bir nesne Windows fare ve klavye mesajlarının alamaz. Bu nedenle, etkin olmayan nesneler daha az kaynak kullanın ve genellikle daha verimlidir.  
  
 [Ipointerınactive'i](/windows/desktop/api/ocidl/nn-ocidl-ipointerinactive) nesnenin en düşük düzeyde etkin olmayan kalan sırasında fare etkileşimi desteklemek arabirim sağlar. Bu işlev, denetimler için özellikle yararlıdır.  
  
 Sınıf `IPointerInactiveImpl` uygulayan `IPointerInactive` E_NOTIMPL yalnızca döndürerek yöntemleri. Ancak, bunu uygulayan `IUnknown` dökümünü almak için bilgi göndererek hata ayıklama cihazı oluşturur.  
  
 **İle ilgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IPointerInactive`  
  
 `IPointerInactiveImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
##  <a name="getactivationpolicy"></a>  IPointerInactiveImpl::GetActivationPolicy  
 Nesne için geçerli etkinleştirme ilkesini alır.  
  
```
HRESULT GetActivationPolicy(DWORD* pdwPolicy);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 E_NOTIMPL döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPointerInactive::GetActivationPolicy](/windows/desktop/api/ocidl/nf-ocidl-ipointerinactive-getactivationpolicy) Windows SDK içinde.  
  
##  <a name="oninactivemousemove"></a>  IPointerInactiveImpl::OnInactiveMouseMove  
 Fareyi üzerine nesneyi gösteren taşındı nesne fare olayları tetikleyebilir bildirir.  
  
```
HRESULT OnInactiveMouseMove(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 E_NOTIMPL döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPointerInactive::OnInactiveMouseMove](/windows/desktop/api/ocidl/nf-ocidl-ipointerinactive-oninactivemousemove) Windows SDK içinde.  
  
##  <a name="oninactivesetcursor"></a>  IPointerInactiveImpl::OnInactiveSetCursor  
 Etkin olmayan bir nesne için fare işaretçisini ayarlar.  
  
```
HRESULT OnInactiveSetCursor(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg,
    BOOL fSetAlways);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 E_NOTIMPL döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPointerInactive::OnInactiveSetCursor](/windows/desktop/api/ocidl/nf-ocidl-ipointerinactive-oninactivesetcursor) Windows SDK içinde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
