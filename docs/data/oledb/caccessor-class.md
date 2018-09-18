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
ms.openlocfilehash: b3adc22d940e79a4f86fec45c0d0e4fc3969f1a7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46071425"
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