---
title: ISpecifyPropertyPagesImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl::GetPages
helpviewer_keywords:
- property pages, CLSIDs associated with
- ISpecifyPropertyPages
- ISpecifyPropertyPagesImpl class
ms.assetid: 4e4b9795-b656-4d56-9b8c-85941e7731f9
ms.openlocfilehash: 06b6b60227a659bd35e042952c7464971fc40bdc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326408"
---
# <a name="ispecifypropertypagesimpl-class"></a>ISpecifyPropertyPagesImpl Sınıfı

Bu `IUnknown` [sınıf, iSpecifyPropertyPages](/windows/win32/api/ocidl/nn-ocidl-ispecifypropertypages) arabiriminin varsayılan uygulamasını uygular ve sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl
   : public ISpecifyPropertyPages
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `ISpecifyPropertyPagesImpl`türetilmiştir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[ISpecifyPropertyPagesImpl::GetPages](#getpages)|UUID değerlerinin Sayılan Dizisini doldurur. Her UUID, nesnenin özellik sayfasında görüntülenebilen özellik sayfalarından biri için CLSID'ye karşılık gelir.|

## <a name="remarks"></a>Açıklamalar

[ISpecifyPropertyPages](/windows/win32/api/ocidl/nn-ocidl-ispecifypropertypages) arabirimi, istemcinin bir nesne tarafından desteklenen özellik sayfaları için CLSID'lerin listesini almasına olanak tanır. Sınıf `ISpecifyPropertyPagesImpl` bu arabirimin varsayılan bir `IUnknown` uygulamasını sağlar ve hata ayıklama oluştururda dökümü aygıtına bilgi göndererek uygular.

> [!NOTE]
> Nesneniz özellik `ISpecifyPropertyPages` sayfalarını desteklemiyorsa arabirimi ifşa etmeyin.

**İlgili Makaleler** [ATL Tutorial](../../atl/active-template-library-atl-tutorial.md), [ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ISpecifyPropertyPages`

`ISpecifyPropertyPagesImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="ispecifypropertypagesimplgetpages"></a><a name="getpages"></a>ISpecifyPropertyPagesImpl::GetPages

[CAUUID](/windows/win32/api/ocidl/ns-ocidl-cauuid) yapısındaki diziyi, nesnenin özellik sayfasında görüntülenebilecek özellik sayfaları için CLSID'lerle doldurur.

```
STDMETHOD(GetPages)(CAUUID* pPages);
```

### <a name="remarks"></a>Açıklamalar

ATL, her CLSID'yi almak için nesnenin özellik eşlesini kullanır.

Bkz. [ISpecifyPropertyPages::Windows](/windows/win32/api/ocidl/nf-ocidl-ispecifypropertypages-getpages) SDK'daki Sayfaları Alın.

## <a name="see-also"></a>Ayrıca bkz.

[IPropertyPageImpl Sınıfı](../../atl/reference/ipropertypageimpl-class.md)<br/>
[IPerPropertyBrowsingImpl Sınıfı](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
