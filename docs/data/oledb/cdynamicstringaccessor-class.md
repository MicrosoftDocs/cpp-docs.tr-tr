---
title: CDynamicStringAccessor sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicStringAccessor
- CDynamicStringAccessor.GetString
- CDynamicStringAccessor::GetString
- CDynamicStringAccessor::SetString
- CDynamicStringAccessor.SetString
dev_langs:
- C++
helpviewer_keywords:
- CDynamicStringAccessor class
- GetString method
- SetString method
ms.assetid: 138dc4de-c7c3-478c-863e-431e48249027
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 178308fc777d5d1c38bbe0ace586bdb6855a7863
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50063126"
---
# <a name="cdynamicstringaccessor-class"></a>CDynamicStringAccessor Sınıfı

Veritabanı şeması (veritabanı yapılarını) hiçbir bilgiye sahip olduğunda bir veri kaynağına erişim sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template< typename BaseType, DBTYPEENUM OleDbType >
class CDynamicStringAccessorT : public CDynamicAccessor
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: atldbcli.h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[GetString](#getstring)|Belirtilen sütun verileri dize olarak alır.|
|[SetString](#setstring)|Belirtilen sütun verileri dize olarak ayarlar.|

## <a name="remarks"></a>Açıklamalar

Sırada [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) sağlayıcı tarafından bildirilen yerel biçiminde veri istekleri `CDynamicStringAccessor` sağlayıcı dize verileri veri deposundan erişilen tüm verileri getirme ister. Bu, özellikle görüntüleme veya veri deposunun içeriği yazdırma gibi veri deposundaki değerleri hesaplama gerektirmeyen basit görevler için kullanışlıdır.

Yerel veri deposundaki sütunun veri türünü önemli değildir; Sağlayıcı veri dönüştürme destekleyebilir sürece, bu verileri dize biçiminde kullanacaksınız. Sağlayıcı (ortak değil) bir dizeyi yerel veri türünden dönüştürme desteklemiyorsa, istekte bulunan çağrı DB_S_ERRORSOCCURED başarı değeri döndürür ve dönüştürme sorun karşılık gelen sütununu durumunu gösterir DBSTATUS_E_CANTCONVERTVALUE.

Kullanım `CDynamicStringAccessor` sütun bilgisi edinmek için. Erişimci çalışma zamanında dinamik olarak oluşturmak için bu sütun bilgileri kullanın.

Sütun bilgisi oluşturulur ve bu sınıf tarafından yönetilen bir arabellek depolanır. Veri arabelleği kullanımından elde [GetString](../../data/oledb/cdynamicstringaccessor-getstring.md), veya arabelleği kullanarak mağaza [SetString](../../data/oledb/cdynamicstringaccessor-setstring.md).

Bir tartışma ve dinamik erişimciyi sınıfları kullanma örnekleri için bkz: [Dinamik Erişimcileri Kullanma](../../data/oledb/using-dynamic-accessors.md).

## <a name="getstring"></a> CDynamicStringAccessor::GetString

Belirtilen sütun verileri dize olarak alır.

### <a name="syntax"></a>Sözdizimi

```cpp
BaseType* GetString(DBORDINAL nColumn) const throw();

BaseType* GetString(const CHAR* pColumnName) const throw();

BaseType* GetString(const WCHAR* pColumnName) const throw();
```

#### <a name="parameters"></a>Parametreler

*nColumn*<br/>
[in] Sütun numarası. Sütun numaraları 1 ile başlayın. 0 değeri, varsa, yer işareti sütunu, ifade eder.

*pColumnName*<br/>
[in] Sütun adı içeren bir karakter dizesine bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Dize işaretçisine belirtilen sütunundan alınır. Değer türünde `BaseType`, olacak **CHAR** veya **WCHAR** _UNICODE veya tanımlı olup olmadığı bağlı olarak. Belirtilen sütun bulunamazsa NULL değer döndürür.

### <a name="remarks"></a>Açıklamalar

İkinci sütun adı formu alır bir ANSI dizesine geçersiz. Üçüncü bir Unicode dize olarak sütun adı formu alır geçersiz.

## <a name="setstring"></a> CDynamicStringAccessor::SetString

Belirtilen sütun verileri dize olarak ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT SetString(DBORDINAL nColumn,
   BaseType* data) throw();

HRESULT SetString(const CHAR* pColumnName,
   BaseType* data) throw();

HRESULT SetString(const WCHAR* pColumnName,
   BaseType* data) throw();
```

#### <a name="parameters"></a>Parametreler

*nColumn*<br/>
[in] Sütun numarası. Sütun numaraları 1 ile başlayın. Özel değeri 0 için yer işareti sütunu, varsa ifade eder.

*pColumnName*<br/>
[in] Sütun adı içeren bir karakter dizesine bir işaretçi.

*Veri*<br/>
[in] Belirtilen sütuna yazılacak dize verileri için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen sütun kümesi dize değeri için bir işaretçi. Değer türünde `BaseType`, olacak **CHAR** veya **WCHAR** _UNICODE veya tanımlı olup olmadığı bağlı olarak.

### <a name="remarks"></a>Açıklamalar

İkinci form alır sütun adı olarak bir ANSI dizesine geçersiz kılma ve üçüncü bir Unicode dize olarak sütun adı formu alır geçersiz kılın.

Sıfır olmayan bir değer olmasını _SECURE_ATL tanımlanırsa, bir çalışma zamanı onaylama işlemi hatası oluşturulur giriş *veri* dizedir başvurulan veri sütununun maksimum izin verilen uzunluktan daha uzun. Aksi takdirde, giriş dizesi, izin verilen uzunluk üst sınırından daha uzun olması durumunda kesilecek.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor Sınıfı](../../data/oledb/caccessor-class.md)<br/>
[CDynamicParameterAccessor Sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[CManualAccessor Sınıfı](../../data/oledb/cmanualaccessor-class.md)<br/>
[CDynamicAccessor Sınıfı](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicStringAccessorA Sınıfı](../../data/oledb/cdynamicstringaccessora-class.md)<br/>
[CDynamicStringAccessorW Sınıfı](../../data/oledb/cdynamicstringaccessorw-class.md)<br/>
[CXMLAccessor Sınıfı](../../data/oledb/cxmlaccessor-class.md)