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
ms.openlocfilehash: e3b76be2a1f1edfcdc1139a3dd396835923c2b4a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210697"
---
# <a name="iconverttypeimpl-class"></a>IConvertTypeImpl Sınıfı

[Iverttype](/previous-versions/windows/desktop/ms715926(v=vs.85)) arabiriminin bir uygulamasını sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
class ATL_NO_VTABLE IConvertTypeImpl
   : public IConvertType, public CConvertHelper
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Sınıfınız `IConvertTypeImpl`türetilir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="interface-methods"></a>Arabirim yöntemleri

|||
|-|-|
|[CanConvert](#canconvert)|Bir komutta veya bir satır kümesinde tür dönüştürmelerinden oluşan kullanılabilirlik hakkında bilgi verir.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim komutlarda, satır kümelerinde ve Dizin satır kümelerinde zorunludur. `IConvertTypeImpl`, OLE DB tarafından sağlanan dönüştürme nesnesine temsilci seçerek arabirimi uygular.

## <a name="iconverttypeimplcanconvert"></a><a name="canconvert"></a>Iverttypeımpl:: CanConvert

Bir komutta veya bir satır kümesinde tür dönüştürmelerinden oluşan kullanılabilirlik hakkında bilgi verir.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(CanConvert)(DBTYPE wFromType,
   DBTYPE wToType,
   DBCONVERTFLAGS dwConvertFlags);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IConvertType:: CanConvert](/previous-versions/windows/desktop/ms711224(v=vs.85)) bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

`MSADC.DLL`OLE DB veri dönüştürmeyi kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
