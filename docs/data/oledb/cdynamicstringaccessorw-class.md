---
title: CDynamicStringAccessorW sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicStringAccessorW
dev_langs:
- C++
helpviewer_keywords:
- CDynamicStringAccessorW class
ms.assetid: 9b7fd5cc-3a9b-4b57-b907-f1e35de2c98f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 16f4725013d11eb27e4c6669403942cf171032ac
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43220080"
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

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor Sınıfı](../../data/oledb/caccessor-class.md)<br/>
[CDynamicParameterAccessor Sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[CManualAccessor Sınıfı](../../data/oledb/cmanualaccessor-class.md)<br/>
[CDynamicAccessor Sınıfı](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicStringAccessor Sınıfı](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
