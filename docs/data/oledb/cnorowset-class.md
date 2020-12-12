---
description: 'Daha fazla bilgi edinin: CNoRowset sınıfı'
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
ms.openlocfilehash: 4cdb4631b63ec1f013183713900ffd9574d90fc3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307567"
---
# <a name="cnorowset-class"></a>CNoRowset Sınıfı

, `TRowset` [CCommand](../../data/oledb/ccommand-class.md) veya [CTable](../../data/oledb/ctable-class.md)için şablon bağımsız değişkeni () olarak kullanılabilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class TAccessor = CAccessorBase>
class CNoRowset
```

### <a name="parameters"></a>Parametreler

*TAccessor*<br/>
Erişimci sınıfı. Varsayılan değer: `CAccessorBase`.

## <a name="remarks"></a>Açıklamalar

`CNoRowset`Komut bir satır kümesi döndürmezse şablon bağımsız değişkeni olarak kullanın.

`CNoRowset` her biri diğer erişimci sınıfı yöntemlerine karşılık gelen aşağıdaki saplama yöntemlerini uygular:

- `BindFinished` -Bağlamanın tamamlandığını gösterir (döndürür `S_OK` ).

- `Close` -Satırları ve geçerli IRowset arabirimini yayınlar.

- `GetIID` -Bir bağlantı noktasının arabirim KIMLIĞINI alır.

- `GetInterface` -Bir arabirim alır.

- `GetInterfacePtr` -Bir kapsüllenmiş arabirim işaretçisini alır.

- `SetAccessor` -Erişimciye bir işaretçi ayarlar.

- `SetupOptionalRowsetInterfaces` -Satır kümesi için isteğe bağlı arabirimler ayarlar.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB tüketici şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
