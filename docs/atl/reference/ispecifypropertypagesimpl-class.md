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
ms.openlocfilehash: eb4611c52f65595eb84248507dfb3a85d1ab26fa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035974"
---
# <a name="ispecifypropertypagesimpl-class"></a>Ispecifypropertypagesımpl sınıfı

Bu sınıfın uyguladığı `IUnknown` ve varsayılan bir uygulama sağlar [ISpecifyPropertyPages](/windows/desktop/api/ocidl/nn-ocidl-ispecifypropertypages) arabirimi.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl 
   : public ISpecifyPropertyPages
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, türetilen `ISpecifyPropertyPagesImpl`.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ISpecifyPropertyPagesImpl::GetPages](#getpages)|Bir dizi UUID, sayılan değerleri doldurur. Her UUID CLSID nesnenin özellik sayfasında görüntülenen özelliği sayfalardan birine karşılık gelir.|

## <a name="remarks"></a>Açıklamalar

[ISpecifyPropertyPages](/windows/desktop/api/ocidl/nn-ocidl-ispecifypropertypages) arabirimi sağlayan bir nesne tarafından desteklenen özellik sayfaları için CLSID listesini almak bir istemci. Sınıf `ISpecifyPropertyPagesImpl` bu arabirimin bir varsayılan uygulamasını sağlar ve uygulayan `IUnknown` dökümünü almak için bilgi göndererek hata ayıklama cihazı oluşturur.

> [!NOTE]
>  Kullanıma `ISpecifyPropertyPages` nesnenizin özellik sayfaları desteklemiyorsa arabirim.

**İle ilgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ISpecifyPropertyPages`

`ISpecifyPropertyPagesImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="getpages"></a>  ISpecifyPropertyPagesImpl::GetPages

Dizi doldurur [CAUUID](/windows/desktop/api/ocidl/ns-ocidl-tagcauuid) CLSID nesnenin özellik sayfasında görüntülenen özellik sayfaları için yapıya sahiptir.

```
STDMETHOD(GetPages)(CAUUID* pPages);
```

### <a name="remarks"></a>Açıklamalar

ATL nesnenin özellik eşlemesi her CLSID almak için kullanır.

Bkz: [ISpecifyPropertyPages::GetPages](/windows/desktop/api/ocidl/nf-ocidl-ispecifypropertypages-getpages) Windows SDK içinde.

## <a name="see-also"></a>Ayrıca Bkz.

[IPropertyPageImpl Sınıfı](../../atl/reference/ipropertypageimpl-class.md)<br/>
[IPerPropertyBrowsingImpl Sınıfı](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
