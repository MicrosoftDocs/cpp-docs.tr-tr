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
ms.openlocfilehash: d916d2e2f8f42a4162966a1d0ddc7de55eb6bd4b
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883586"
---
# <a name="ipointerinactiveimpl-class"></a>Ipointerınactiveımpl sınıfı
Bu sınıfın uyguladığı `IUnknown` ve [Ipointerınactive'i](http://msdn.microsoft.com/library/windows/desktop/ms693712) arabirim yöntemleri.  
  
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
  
 [Ipointerınactive'i](http://msdn.microsoft.com/library/windows/desktop/ms693712) nesnenin en düşük düzeyde etkin olmayan kalan sırasında fare etkileşimi desteklemek arabirim sağlar. Bu işlev, denetimler için özellikle yararlıdır.  
  
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
 Bkz: [IPointerInactive::GetActivationPolicy](http://msdn.microsoft.com/library/windows/desktop/ms692470) Windows SDK içinde.  
  
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
 Bkz: [IPointerInactive::OnInactiveMouseMove](http://msdn.microsoft.com/library/windows/desktop/ms693374) Windows SDK içinde.  
  
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
 Bkz: [IPointerInactive::OnInactiveSetCursor](http://msdn.microsoft.com/library/windows/desktop/ms694336) Windows SDK içinde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
