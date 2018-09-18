---
title: CColumnAccessor sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CColumnAccessor
- ATL::CColumnAccessor
- ATL.CColumnAccessor
dev_langs:
- C++
helpviewer_keywords:
- CColumnAccessor class
ms.assetid: 6ce1e67f-6a20-490d-9326-c168b43eee7e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b1843b6279cb7c86762cc6d975a2a7e67d3d278d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055643"
---
# <a name="ccolumnaccessor-class"></a>CColumnAccessor Sınıfı

Eklenen tüketici kod oluşturur.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
class CColumnAccessor : public CAccessorBase  
```  
  
## <a name="remarks"></a>Açıklamalar  

Eklenen kodun her sütun ayrı bir erişimci bağlıdır. Bu sınıf eklenen kodun kullanıldığını bilmeniz gerekir (örneğin, bu hata ayıklama sırasında karşılaşabileceğiniz), ancak genellikle hiçbir zaman doğrudan veya yöntemlerini kullanın.  
  
`CColumnAccessor` işlev diğer erişimcisi sınıf yöntemleri karşılık her biri aşağıdaki saptama yöntemleri uygular:  
  
- `CColumnAccessor` Oluşturucusu oluşturur ve başlatır `CColumnAccessor` nesne.  
  
- `CreateAccessor` Bağlama yapıları sütun için bellek ayırır ve sütun veri üyelerine başlatır.  
  
- `BindColumns` Sütunları için erişimciler bağlar.  
  
- `SetParameterBuffer` Arabellekler için parametreleri ayırır.  
  
- `AddParameter` Bir parametre girişi parametre girişi yapılara ekler.  
  
- `HasOutputColumns` Erişimci sütunları çıktısı olup olmadığını belirler  
  
- `HasParameters` Erişimcisi parametrelere sahip olup olmadığını belirler.  
  
- `BindParameters` Oluşturulan parametre sütunları bağlar.  
  
## <a name="requirements"></a>Gereksinimler  

**Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)