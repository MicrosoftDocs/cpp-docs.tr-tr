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
ms.openlocfilehash: 19a1e01fd29c74cf1c44081c24bf384704cf2acd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211480"
---
# <a name="cnorowset-class"></a>CNoRowset Sınıfı

, [CCommand](../../data/oledb/ccommand-class.md) veya [CTable](../../data/oledb/ctable-class.md)için şablon bağımsız değişkeni (`TRowset`) olarak kullanılabilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class TAccessor = CAccessorBase>
class CNoRowset
```

### <a name="parameters"></a>Parametreler

*TAccessor*<br/>
Erişimci sınıfı. Varsayılan: `CAccessorBase`.

## <a name="remarks"></a>Açıklamalar

Komut bir satır kümesi döndürmezse `CNoRowset` şablon bağımsız değişkeni olarak kullanın.

`CNoRowset`, her biri diğer erişimci sınıfı yöntemlerine karşılık gelen aşağıdaki saplama yöntemlerini uygular:

- `BindFinished`-bağlamanın tamamlandığını gösterir (`S_OK`döndürür).

- `Close`-satırları ve geçerli IRowset arabirimini yayınlar.

- `GetIID`-bir bağlantı noktasının arabirim KIMLIĞINI alır.

- `GetInterface`-bir arabirim alır.

- `GetInterfacePtr`-kapsüllenmiş arabirim işaretçisini alır.

- `SetAccessor`-erişimciye bir işaretçi ayarlar.

- `SetupOptionalRowsetInterfaces`-satır kümesi için isteğe bağlı arabirimler ayarlar.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
