---
title: CAccessor sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CAccessor<T>
- ATL::CAccessor
- CAccessor
- ATL::CAccessor<T>
- ATL.CAccessor
dev_langs:
- C++
helpviewer_keywords:
- CAccessor class
ms.assetid: b2ba959f-a686-46f3-8837-176248aef748
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0ac3ad9da312ba1723fd7201b804260e11a64660
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50060708"
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

Kayıt bir veri kaynağına statik olarak bağlı olduğunda kullanılır. Kayıt arabellek içerir. Bu sınıf, bir satır kümesinde çoklu erişimci destekler.

Yapı ve veritabanı türü bildiğinizde bu erişimcisinin türünü kullanın.

Bellek noktası alanlar, erişimci içeriyorsa, (gibi bir `BSTR` veya arabirimi) getirilmesi gereken serbest, üye işlevi çağrısı [CAccessorRowset::FreeRecordMemory](../../data/oledb/caccessorrowset-freerecordmemory.md) sonraki kayıt okunur.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldbcli.h

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)