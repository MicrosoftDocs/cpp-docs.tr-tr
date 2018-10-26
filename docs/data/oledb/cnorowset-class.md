---
title: CNoRowset sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CNoRowset
- ATL::CNoRowset<TAccessor>
- CNoRowset
- ATL.CNoRowset<TAccessor>
- ATL::CNoRowset
dev_langs:
- C++
helpviewer_keywords:
- CNoRowset class
ms.assetid: 55c6c7a4-9e3a-4775-a2dd-c8b333012fa6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f14ad79e1cbd2207b4eb1582cb80e0107d68ec39
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50064244"
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

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)