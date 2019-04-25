---
title: CDynamicStringAccessorW Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDynamicStringAccessorW
helpviewer_keywords:
- CDynamicStringAccessorW class
ms.assetid: 9b7fd5cc-3a9b-4b57-b907-f1e35de2c98f
ms.openlocfilehash: 20ea4a2d795108e00c4b11c3abea6cf7b9953ca7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230794"
---
# <a name="cdynamicstringaccessorw-class"></a>CDynamicStringAccessorW Sınıfı

Veritabanı şeması (temelindeki) hiçbir bilgiye sahip olduğunda bir veri kaynağına erişim sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef CDynamicStringAccessorT<WCHAR, DBTYPE_WSTR> CDynamicStringAccessorW;
```

## <a name="remarks"></a>Açıklamalar

Her ikisi de sağlayıcı veri deposu olarak dize verileri, erişilen tüm verileri getirme istek ancak `CDynamicStringAccessor` Unicode dize verileri ister.

`CDynamicStringAccessorW` devralınan `GetString` ve `SetString` gelen `CDynamicStringAccessor`. Bu yöntemleri kullanırken bir `CDynamicStringAccessorW` nesnesi `BaseType` olduğu **WCHAR**.

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
