---
title: IConvertTypeImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL.IConvertTypeImpl<T>
- IConvertTypeImpl
- ATL.IConvertTypeImpl
- ATL::IConvertTypeImpl
- ATL::IConvertTypeImpl<T>
- IConvertTypeImpl.CanConvert
- CanConvert
- IConvertTypeImpl::CanConvert
helpviewer_keywords:
- IConvertTypeImpl class
- CanConvert method
ms.assetid: 7f81e79e-7d3f-4cbe-b93c-d632a94b15f6
ms.openlocfilehash: b4309e794a83e6c13dcf0051791cd1762a6d5012
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845568"
---
# <a name="iconverttypeimpl-class"></a>IConvertTypeImpl Sınıfı

[Iverttype](/previous-versions/windows/desktop/ms715926(v=vs.85)) arabiriminin bir uygulamasını sağlar.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class T>
class ATL_NO_VTABLE IConvertTypeImpl
   : public IConvertType, public CConvertHelper
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, öğesinden türetilir `IConvertTypeImpl` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="interface-methods"></a>Arabirim yöntemleri

| Ad | Açıklama |
|-|-|
|[CanConvert](#canconvert)|Bir komutta veya bir satır kümesinde tür dönüştürmelerinden oluşan kullanılabilirlik hakkında bilgi verir.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim komutlarda, satır kümelerinde ve Dizin satır kümelerinde zorunludur. `IConvertTypeImpl` OLE DB tarafından sağlanan dönüştürme nesnesine temsilci seçerek arabirimi uygular.

## <a name="iconverttypeimplcanconvert"></a><a name="canconvert"></a> Iverttypeımpl:: CanConvert

Bir komutta veya bir satır kümesinde tür dönüştürmelerinden oluşan kullanılabilirlik hakkında bilgi verir.

### <a name="syntax"></a>Söz dizimi

```cpp
STDMETHOD(CanConvert)(DBTYPE wFromType,
   DBTYPE wToType,
   DBCONVERTFLAGS dwConvertFlags);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IConvertType:: CanConvert](/previous-versions/windows/desktop/ms711224(v=vs.85)) bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

İçinde OLE DB veri dönüştürmeyi kullanır `MSADC.DLL` .

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB sağlayıcı şablonu mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
