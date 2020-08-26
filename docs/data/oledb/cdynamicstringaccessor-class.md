---
title: CDynamicStringAccessor Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDynamicStringAccessor
- CDynamicStringAccessor.GetString
- CDynamicStringAccessor::GetString
- CDynamicStringAccessor::SetString
- CDynamicStringAccessor.SetString
helpviewer_keywords:
- CDynamicStringAccessor class
- GetString method
- SetString method
ms.assetid: 138dc4de-c7c3-478c-863e-431e48249027
ms.openlocfilehash: 927ea5ceef9ac74ae3cc1e06a47969b537209002
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838171"
---
# <a name="cdynamicstringaccessor-class"></a>CDynamicStringAccessor Sınıfı

Veritabanı şeması (veritabanının temel yapısı) hakkında bilginiz olmadığında bir veri kaynağına erişmenizi sağlar.

## <a name="syntax"></a>Syntax

```cpp
template< typename BaseType, DBTYPEENUM OleDbType >
class CDynamicStringAccessorT : public CDynamicAccessor
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi**: atldbclı. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

| Ad | Açıklama |
|-|-|
|[GetString](#getstring)|Belirtilen sütun verilerini bir dize olarak alır.|
|[SetString](#setstring)|Belirtilen sütun verisini bir dize olarak ayarlar.|

## <a name="remarks"></a>Açıklamalar

[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) , sağlayıcı tarafından bildirilen yerel biçimdeki verileri istediğinde, `CDynamicStringAccessor` sağlayıcının veri deposundan erişilen tüm verileri dize verileri olarak getirip getirdiğini ister. Bu, veri deposunun içeriğini görüntüleme veya yazdırma gibi veri deposundaki değerlerin hesaplanmasını gerektirmeyen basit görevler için özellikle yararlıdır.

Veri deposundaki sütun verilerinin yerel türü önemi değildir; sağlayıcı veri dönüştürmeyi destekledikleri sürece, verileri dize biçiminde sağlar. Sağlayıcı yerel veri türünden bir dizeye (yaygın olmayan) dönüştürme işlemi desteklemiyorsa, istenen çağrı başarı değeri DB_S_ERRORSOCCURED döndürür ve karşılık gelen sütunun durumu DBSTATUS_E_CANTCONVERTVALUE bir dönüştürme sorunu olduğunu gösterir.

`CDynamicStringAccessor`Sütun bilgilerini almak için yöntemleri kullanın. Bu sütun bilgilerini, çalışma zamanında dinamik olarak bir erişimci oluşturmak için kullanırsınız.

Sütun bilgileri bu sınıf tarafından oluşturulan ve yönetilen bir arabellekte saklanır. [GetString](../../data/oledb/cdynamicstringaccessor-getstring.md)kullanarak arabellekteki verileri alın veya [SetString](../../data/oledb/cdynamicstringaccessor-setstring.md)kullanarak arabelleğe saklayın.

Bir tartışma ve dinamik erişimci sınıflarını kullanma örnekleri için bkz. [dinamik erişimcileri kullanma](../../data/oledb/using-dynamic-accessors.md).

## <a name="cdynamicstringaccessorgetstring"></a><a name="getstring"></a> CDynamicStringAccessor:: GetString

Belirtilen sütun verilerini bir dize olarak alır.

### <a name="syntax"></a>Söz dizimi

```cpp
BaseType* GetString(DBORDINAL nColumn) const throw();

BaseType* GetString(const CHAR* pColumnName) const throw();

BaseType* GetString(const WCHAR* pColumnName) const throw();
```

#### <a name="parameters"></a>Parametreler

*Nsütun*<br/>
'ndaki Sütun numarası. Sütun numaraları 1 ile başlar. 0 değeri, varsa yer işareti sütununa başvurur.

*pColumnName*<br/>
'ndaki Sütun adını içeren bir karakter dizesinin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen sütundan alınan dize değerine yönelik bir işaretçi. Değer `BaseType` , _UNICODE tanımlanmış olup olmadığına bağlı olarak **char** veya **wchar** olacak türdür. Belirtilen sütun bulunmazsa NULL değerini döndürür.

### <a name="remarks"></a>Açıklamalar

İkinci geçersiz kılma formu, sütun adını bir ANSI dizesi olarak alır. Üçüncü geçersiz kılma formu sütun adını bir Unicode dizesi olarak alır.

## <a name="cdynamicstringaccessorsetstring"></a><a name="setstring"></a> CDynamicStringAccessor:: SetString

Belirtilen sütun verisini bir dize olarak ayarlar.

### <a name="syntax"></a>Söz dizimi

```cpp
HRESULT SetString(DBORDINAL nColumn,
   BaseType* data) throw();

HRESULT SetString(const CHAR* pColumnName,
   BaseType* data) throw();

HRESULT SetString(const WCHAR* pColumnName,
   BaseType* data) throw();
```

#### <a name="parameters"></a>Parametreler

*Nsütun*<br/>
'ndaki Sütun numarası. Sütun numaraları 1 ile başlar. Özel 0 değeri, varsa yer işareti sütununa başvurur.

*pColumnName*<br/>
'ndaki Sütun adını içeren bir karakter dizesinin işaretçisi.

*data*<br/>
'ndaki Belirtilen sütuna yazılacak dize verilerine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen sütunun ayarlanacağı dize değerine yönelik bir işaretçi. Değer `BaseType` , _UNICODE tanımlanmış olup olmadığına bağlı olarak **char** veya **wchar** olacak türdür.

### <a name="remarks"></a>Açıklamalar

İkinci geçersiz kılma formu, sütun adını bir ANSI dizesi olarak alır ve üçüncü geçersiz kılma formu sütun adını bir Unicode dizesi olarak alır.

_SECURE_ATL sıfır dışında bir değere sahip olacak şekilde tanımlanmışsa, giriş *veri* dizesi başvurulan veri sütununun izin verilen uzunluk üst sınırından daha uzunsa bir çalışma zamanı onaylama hatası oluşturulur. Aksi takdirde, giriş dizesi izin verilen en fazla uzunluktan daha uzunsa kesilir.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB tüketici şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor sınıfı](../../data/oledb/caccessor-class.md)<br/>
[CDynamicParameterAccessor sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[CManualAccessor sınıfı](../../data/oledb/cmanualaccessor-class.md)<br/>
[CDynamicAccessor sınıfı](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicStringAccessorA sınıfı](../../data/oledb/cdynamicstringaccessora-class.md)<br/>
[CDynamicStringAccessorW sınıfı](../../data/oledb/cdynamicstringaccessorw-class.md)<br/>
[CXMLAccessor sınıfı](../../data/oledb/cxmlaccessor-class.md)
