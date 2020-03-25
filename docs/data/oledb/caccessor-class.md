---
title: CAccessor Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL.CAccessor<T>
- ATL::CAccessor
- CAccessor
- ATL::CAccessor<T>
- ATL.CAccessor
helpviewer_keywords:
- CAccessor class
ms.assetid: b2ba959f-a686-46f3-8837-176248aef748
ms.openlocfilehash: 2b30cef2baf8c13c5001e44901b984aa1293494d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212309"
---
# <a name="caccessor-class"></a>CAccessor Sınıfı

Erişimci türlerinden birini temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
class CAccessor : public CAccessorBase, public T
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Kullanıcı kayıt sınıfı.

## <a name="remarks"></a>Açıklamalar

Bir kayıt bir veri kaynağına statik olarak bağlandığında kullanılır. Kayıt, arabelleği içerir. Bu sınıf, bir satır kümesinde birden çok erişimciyi destekler.

Bu erişimci türünü, veritabanının yapısını ve türünü bildiğiniz durumlarda kullanın.

Erişimci, serbest olması gereken belleğe (bir `BSTR` veya arabirim) işaret eden alanlar içeriyorsa, sonraki kayıt okunmadan önce [CAccessorRowset:: FreeRecordMemory](../../data/oledb/caccessorrowset-freerecordmemory.md) üye işlevini çağırın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
