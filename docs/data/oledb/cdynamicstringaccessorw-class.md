---
description: 'Daha fazla bilgi edinin: CDynamicStringAccessorW sınıfı'
title: CDynamicStringAccessorW Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDynamicStringAccessorW
helpviewer_keywords:
- CDynamicStringAccessorW class
ms.assetid: 9b7fd5cc-3a9b-4b57-b907-f1e35de2c98f
ms.openlocfilehash: 360a9592cdce3a1046eecb360a8691b1d8480caf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170678"
---
# <a name="cdynamicstringaccessorw-class"></a>CDynamicStringAccessorW Sınıfı

Veritabanı şeması (temel yapı) hakkında bilginiz olmadığında bir veri kaynağına erişmenizi sağlar.

## <a name="syntax"></a>Syntax

```cpp
typedef CDynamicStringAccessorT<WCHAR, DBTYPE_WSTR> CDynamicStringAccessorW;
```

## <a name="remarks"></a>Açıklamalar

Her ikisi de sağlayıcının veri deposundan erişilen tüm verileri dize verileri olarak getirip, ancak `CDynamicStringAccessor` Unicode dize verileri isteyeceğini ister.

`CDynamicStringAccessorW``GetString`, ve `SetString` öğesinden devralır `CDynamicStringAccessor` . Bu yöntemleri bir `CDynamicStringAccessorW` nesnesinde kullandığınızda, `BaseType` **wchar** olur.

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
