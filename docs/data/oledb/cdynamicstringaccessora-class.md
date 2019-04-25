---
title: CDynamicStringAccessorA Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDynamicStringAccessorA
helpviewer_keywords:
- CDynamicStringAccessorA class
ms.assetid: ed0d9821-a655-41f1-a902-43c3042ac49c
ms.openlocfilehash: 3a0da9c779230fc1bf58bfa1d685623f844012c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62231044"
---
# <a name="cdynamicstringaccessora-class"></a>CDynamicStringAccessorA Sınıfı

Veritabanı şeması (temelindeki) hiçbir bilgiye sahip olduğunda bir veri kaynağına erişim sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef CDynamicStringAccessorT<CHAR, DBTYPE_STR> CDynamicStringAccessorA;
```

## <a name="remarks"></a>Açıklamalar

Her ikisi de sağlayıcı veri deposu olarak dize verileri, erişilen tüm verileri getirme istek ancak `CDynamicStringAccessor` istekleri ANSI veri dizesi.

`CDynamicStringAccessorA` devralınan `GetString` ve `SetString` gelen `CDynamicStringAccessor`. Bu yöntemleri kullanırken bir `CDynamicStringAccessorA` nesnesi `BaseType` olduğu **CHAR**.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: atldbcli.h

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor Sınıfı](../../data/oledb/caccessor-class.md)<br/>
[CDynamicParameterAccessor Sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[CManualAccessor Sınıfı](../../data/oledb/cmanualaccessor-class.md)<br/>
[CDynamicAccessor Sınıfı](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicStringAccessor Sınıfı](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
