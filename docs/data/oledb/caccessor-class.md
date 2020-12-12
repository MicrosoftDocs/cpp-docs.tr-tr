---
description: 'Daha fazla bilgi edinin: CAccessor sınıfı'
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
ms.openlocfilehash: 26b03bc3f464ce606194d6835953c39969bde5de
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319176"
---
# <a name="caccessor-class"></a>CAccessor Sınıfı

Erişimci türlerinden birini temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
class CAccessor : public CAccessorBase, public T
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Kullanıcı kayıt sınıfı.

## <a name="remarks"></a>Açıklamalar

Bir kayıt bir veri kaynağına statik olarak bağlandığında kullanılır. Kayıt, arabelleği içerir. Bu sınıf, bir satır kümesinde birden çok erişimciyi destekler.

Bu erişimci türünü, veritabanının yapısını ve türünü bildiğiniz durumlarda kullanın.

Erişimci, serbest olması gereken belleğe (örneğin, bir veya arabirim) işaret eden alanlar içeriyorsa `BSTR` , sonraki kayıt okunmadan önce [CAccessorRowset:: FreeRecordMemory](./caccessorrowset-class.md#freerecordmemory) üye işlevini çağırın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB tüketici şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
