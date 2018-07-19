---
title: Ispecifypropertypagesımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl::GetPages
dev_langs:
- C++
helpviewer_keywords:
- property pages, CLSIDs associated with
- ISpecifyPropertyPages
- ISpecifyPropertyPagesImpl class
ms.assetid: 4e4b9795-b656-4d56-9b8c-85941e7731f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b54b8e4fdfbbfd282475ed0ca6e221d826953cad
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879578"
---
# <a name="ispecifypropertypagesimpl-class"></a>Ispecifypropertypagesımpl sınıfı
Bu sınıfın uyguladığı `IUnknown` ve varsayılan bir uygulama sağlar [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217) arabirimi.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>  
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl 
   : public ISpecifyPropertyPages
```  
  
#### <a name="parameters"></a>Parametreler  
 *T*  
 Sınıfınız, türetilen `ISpecifyPropertyPagesImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ISpecifyPropertyPagesImpl::GetPages](#getpages)|Bir dizi UUID, sayılan değerleri doldurur. Her UUID CLSID nesnenin özellik sayfasında görüntülenen özelliği sayfalardan birine karşılık gelir.|  
  
## <a name="remarks"></a>Açıklamalar  
 [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217) arabirimi sağlayan bir nesne tarafından desteklenen özellik sayfaları için CLSID listesini almak bir istemci. Sınıf `ISpecifyPropertyPagesImpl` bu arabirimin bir varsayılan uygulamasını sağlar ve uygulayan `IUnknown` dökümünü almak için bilgi göndererek hata ayıklama cihazı oluşturur.  
  
> [!NOTE]
>  Kullanıma `ISpecifyPropertyPages` nesnenizin özellik sayfaları desteklemiyorsa arabirim.  
  
 **İle ilgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ISpecifyPropertyPages`  
  
 `ISpecifyPropertyPagesImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="getpages"></a>  ISpecifyPropertyPagesImpl::GetPages  
 Dizi doldurur [CAUUID](http://msdn.microsoft.com/library/windows/desktop/ms680048) CLSID nesnenin özellik sayfasında görüntülenen özellik sayfaları için yapıya sahiptir.  
  
```
STDMETHOD(GetPages)(CAUUID* pPages);
```  
  
### <a name="remarks"></a>Açıklamalar  
 ATL nesnenin özellik eşlemesi her CLSID almak için kullanır.  
  
 Bkz: [ISpecifyPropertyPages::GetPages](http://msdn.microsoft.com/library/windows/desktop/ms687276) Windows SDK içinde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ipropertypageımpl sınıfı](../../atl/reference/ipropertypageimpl-class.md)   
 [Iperpropertybrowsingımpl sınıfı](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
