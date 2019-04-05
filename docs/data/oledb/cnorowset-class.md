---
title: CNoRowset Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL.CNoRowset
- ATL::CNoRowset<TAccessor>
- CNoRowset
- ATL.CNoRowset<TAccessor>
- ATL::CNoRowset
helpviewer_keywords:
- CNoRowset class
ms.assetid: 55c6c7a4-9e3a-4775-a2dd-c8b333012fa6
ms.openlocfilehash: 6193e2d461761c53fb05e5c16b3914c56d545173
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59035682"
---
# <a name="cnorowset-class"></a>CNoRowset Sınıfı

Bir şablon bağımsız değişkeni kullanılabilir (`TRowset`) için [CCommand](../../data/oledb/ccommand-class.md) veya [CTable](../../data/oledb/ctable-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
template <class TAccessor = CAccessorBase>
class CNoRowset
```

### <a name="parameters"></a>Parametreler

*TAccessor*<br/>
Bir erişimci sınıfı. Varsayılan, `CAccessorBase` değeridir.

## <a name="remarks"></a>Açıklamalar

Kullanım `CNoRowset` komut satır döndürmezse, şablon bağımsız değişken olarak.

`CNoRowset` karşılık gelen her biri için diğer erişimcisi sınıf yöntemleri aşağıdaki saptama yöntemleri uygular:

- `BindFinished` -Bağlama ne zaman tamamlandığını gösterir (döndürür `S_OK`).

- `Close` -Satır ve geçerli Irowset arabirimi serbest bırakır.

- `GetIID` -Bir bağlantı noktasının arabirim kimliği alır.

- `GetInterface` -Bir arabirim alır.

- `GetInterfacePtr` -Bir kapsüllenmiş arabirim işaretçisini alır.

- `SetAccessor` -Bir işaretçi için erişimci olarak ayarlar.

- `SetupOptionalRowsetInterfaces` -İsteğe bağlı arabirimler satır kümesi için ayarlar.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldbcli.h

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)