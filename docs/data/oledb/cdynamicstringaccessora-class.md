---
description: 'Daha fazla bilgi edinin: CDynamicStringAccessorA sınıfı'
title: CDynamicStringAccessorA Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDynamicStringAccessorA
helpviewer_keywords:
- CDynamicStringAccessorA class
ms.assetid: ed0d9821-a655-41f1-a902-43c3042ac49c
ms.openlocfilehash: 45a4d10c8a50c4009151fa90e51172405047a21a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170730"
---
# <a name="cdynamicstringaccessora-class"></a>CDynamicStringAccessorA Sınıfı

Veritabanı şeması (temel yapı) hakkında bilginiz olmadığında bir veri kaynağına erişmenizi sağlar.

## <a name="syntax"></a>Syntax

```cpp
typedef CDynamicStringAccessorT<CHAR, DBTYPE_STR> CDynamicStringAccessorA;
```

## <a name="remarks"></a>Açıklamalar

Her ikisi de sağlayıcının veri deposundan erişilen tüm verileri dize verileri olarak getirdiğini, ancak `CDynamicStringAccessor` ANSI dize verileri isteyeceğini ister.

`CDynamicStringAccessorA``GetString`, ve `SetString` öğesinden devralır `CDynamicStringAccessor` . Bu yöntemleri bir `CDynamicStringAccessorA` nesnesinde kullandığınızda, `BaseType` **char**' dır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi**: atldbclı. h

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB tüketici şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor sınıfı](../../data/oledb/caccessor-class.md)<br/>
[CDynamicParameterAccessor sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[CManualAccessor sınıfı](../../data/oledb/cmanualaccessor-class.md)<br/>
[CDynamicAccessor sınıfı](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicStringAccessor sınıfı](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
