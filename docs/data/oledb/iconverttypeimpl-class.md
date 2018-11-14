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
ms.openlocfilehash: 0b3c0f239b3c80d0b4d3c8425b03a3612a0e6db2
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556237"
---
# <a name="iconverttypeimpl-class"></a>IConvertTypeImpl Sınıfı

Bir uygulamasını sağlar [IConvertType](https://docs.microsoft.com/previous-versions/windows/desktop/ms715926(v=vs.85)) arabirimi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
class ATL_NO_VTABLE IConvertTypeImpl
   : public IConvertType, public CConvertHelper
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, türetilen `IConvertTypeImpl`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldb.h

## <a name="members"></a>Üyeler

### <a name="interface-methods"></a>Arabirim yöntemleri

|||
|-|-|
|[CanConvert](#canconvert)|Bir komutu veya bir satır kümesi tür dönüştürmeleri kullanılabilirliği hakkında bilgi sağlar.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim, komutları, satır kümeleri ve dizin satır kümeleri zorunludur. `IConvertTypeImpl` OLE DB tarafından sağlanan dönüştürme nesne temsilci atayarak arabirimini uygular.

## <a name="canconvert"></a> Iconverttypeımpl::canconvert

Bir komutu veya bir satır kümesi tür dönüştürmeleri kullanılabilirliği hakkında bilgi sağlar.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(CanConvert)(DBTYPE wFromType,
   DBTYPE wToType,
   DBCONVERTFLAGS dwConvertFlags);
```

#### <a name="parameters"></a>Parametreler

Bkz: [IConvertType::CanConvert](https://docs.microsoft.com/previous-versions/windows/desktop/ms711224(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

### <a name="remarks"></a>Açıklamalar

OLE DB veri dönüştürme kullanan `MSADC.DLL`.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)