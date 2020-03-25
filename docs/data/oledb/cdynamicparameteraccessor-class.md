---
title: CDynamicParameterAccessor Sınıfı
ms.date: 02/14/2018
f1_keywords:
- ATL.CDynamicParameterAccessor
- ATL::CDynamicParameterAccessor
- CDynamicParameterAccessor
- CDynamicParameterAccessor::CDynamicParameterAccessor
- CDynamicParameterAccessor.CDynamicParameterAccessor
- CDynamicParameterAccessor::GetParam
- ATL.CDynamicParameterAccessor.GetParam
- CDynamicParameterAccessor::GetParam<ctype>
- CDynamicParameterAccessor.GetParam
- GetParam
- ATL::CDynamicParameterAccessor::GetParam<ctype>
- ATL::CDynamicParameterAccessor::GetParam
- ATL::CDynamicParameterAccessor::GetParamCount
- CDynamicParameterAccessor::GetParamCount
- CDynamicParameterAccessor.GetParamCount
- GetParamCount
- ATL.CDynamicParameterAccessor.GetParamCount
- GetParamIO
- CDynamicParameterAccessor::GetParamIO
- ATL.CDynamicParameterAccessor.GetParamIO
- CDynamicParameterAccessor.GetParamIO
- ATL::CDynamicParameterAccessor::GetParamIO
- ATL::CDynamicParameterAccessor::GetParamLength
- ATL.CDynamicParameterAccessor.GetParamLength
- CDynamicParameterAccessor.GetParamLength
- CDynamicParameterAccessor::GetParamLength
- GetParamLength
- CDynamicParameterAccessor::GetParamName
- ATL.CDynamicParameterAccessor.GetParamName
- GetParamName
- CDynamicParameterAccessor.GetParamName
- ATL::CDynamicParameterAccessor::GetParamName
- CDynamicParameterAccessor::GetParamStatus
- CDynamicParameterAccessor.GetParamStatus
- ATL.CDynamicParameterAccessor.GetParamStatus
- ATL::CDynamicParameterAccessor::GetParamStatus
- GetParamStatus
- CDynamicParameterAccessor.GetParamString
- GetParamString
- CDynamicParameterAccessor::GetParamString
- ATL.CDynamicParameterAccessor.GetParamString
- ATL::CDynamicParameterAccessor::GetParamString
- CDynamicParameterAccessor.GetParamType
- CDynamicParameterAccessor:GetParamType
- CDynamicParameterAccessor::GetParamType
- ATL.CDynamicParameterAccessor.GetParamType
- GetParamType
- ATL::CDynamicParameterAccessor::GetParamType
- ATL::CDynamicParameterAccessor::SetParam
- ATL::CDynamicParameterAccessor::SetParam<ctype>
- CDynamicParameterAccessor.SetParam
- ATL.CDynamicParameterAccessor.SetParam
- SetParam
- CDynamicParameterAccessor:SetParam
- CDynamicParameterAccessor::SetParam<ctype>
- CDynamicParameterAccessor::SetParam
- ATL::CDynamicParameterAccessor::SetParamLength
- CDynamicParameterAccessor.SetParamLength
- ATL.CDynamicParameterAccessor.SetParamLength
- CDynamicParameterAccessor::SetParamLength
- SetParamLength
- CDynamicParameterAccessor::SetParamStatus
- ATL.CDynamicParameterAccessor.SetParamStatus
- ATL::CDynamicParameterAccessor::SetParamStatus
- CDynamicParameterAccessor.SetParamStatus
- SetParamStatus
- ATL.CDynamicParameterAccessor.SetParamString
- ATL::CDynamicParameterAccessor::SetParamString
- SetParamString
- CDynamicParameterAccessor::SetParamString
- CDynamicParameterAccessor.SetParamString
helpviewer_keywords:
- CDynamicParameterAccessor class
- CDynamicParameterAccessor class, constructor
- CDynamicParameterAccessor method
- GetParam method
- GetParamCount method
- GetParamIO method
- GetParamLength method
- GetParamName method
- GetParamStatus method
- GetParamString method
- GetParamType method
- SetParam method
- SetParamLength method
- SetParamStatus method
- SetParamString method
ms.assetid: 5f22626e-e80d-491f-8b3b-cedc50331960
ms.openlocfilehash: 9c326c337ff210ef9de26b3fd88c0d853832b260
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211880"
---
# <a name="cdynamicparameteraccessor-class"></a>CDynamicParameterAccessor Sınıfı

[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) 'a benzer ancak [ICommandText](/sql/relational-databases/native-client-ole-db-interfaces/icommandwithparameters) arabirimini çağırarak parametre bilgilerini ayarlanacak şekilde edinir.

## <a name="syntax"></a>Sözdizimi

```cpp
class CDynamicParameterAccessor : public CDynamicAccessor
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi**: atldbclı. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[CDynamicParameterAccessor](#cdynamicparameteraccessor)|Oluşturucu.|
|[GetParam](#getparam)|Arabellekteki parametre verilerini alır.|
|[GetParamCount](#getparamcount)|Erişimcinin parametre sayısını alır.|
|[Getparamıo](#getparamio)|Belirtilen parametrenin bir giriş veya çıkış parametresi olup olmadığını belirler.|
|[GetParamLength](#getparamlength)|Arabellekte depolanan belirtilen parametrenin uzunluğunu alır.|
|[GetParamName](#getparamname)|Belirtilen parametrenin adını alır.|
|[GetParamStatus](#getparamstatus)|Arabellekte depolanan belirtilen parametrenin durumunu alır.|
|[GetParamString](#getparamstring)|Arabellekte depolanan belirtilen parametrenin dize verilerini alır.|
|[GetParamType](#getparamtype)|Belirtilen parametrenin veri türünü alır.|
|[SetParam](#setparam)|Parametre verilerini kullanarak arabelleği ayarlar.|
|[SetParamLength](#setparamlength)|Arabellekte depolanan belirtilen parametrenin uzunluğunu ayarlar.|
|[SetParamStatus](#setparamstatus)|Arabellekte depolanan belirtilen parametrenin durumunu ayarlar.|
|[SetParamString](#setparamstring)|Arabellekte depolanan belirtilen parametrenin dize verilerini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Sağlayıcı, tüketicinin bu sınıfı kullanması için `ICommandWithParameters` desteklemelidir.

Parametre bilgileri, bu sınıf tarafından oluşturulan ve yönetilen bir arabellekte saklanır. [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) ve [GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md)kullanarak arabellekteki parametre verilerini elde edin.

Bu sınıfın bir SQL Server saklı yordamı yürütmek ve çıkış parametre değerlerini almak için nasıl kullanılacağını gösteren bir örnek için GitHub 'daki [Microsoft VCSamples](https://github.com/Microsoft/VCSamples) deposundaki [DynamicConsumer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer) örnek koduna bakın.

## <a name="cdynamicparameteraccessorcdynamicparameteraccessor"></a><a name="cdynamicparameteraccessor"></a>CDynamicParameterAccessor:: CDynamicParameterAccessor

Oluşturucu.

### <a name="syntax"></a>Sözdizimi

```cpp
typedef CDynamicParameterAccessor _ParamClass;
CDynamicParameterAccessor(
   DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,
   DBLENGTH nBlobSize = 8000 )
   : CDynamicAccessor(eBlobHandling, nBlobSize )
```

#### <a name="parameters"></a>Parametreler

*eBlobHandling*<br/>
BLOB verilerinin nasıl işleneceğini belirtir. Varsayılan değer DBBLOBHANDLING_DEFAULT. DBBLOBHANDLINGENUM değerlerinin açıklaması için bkz. [CDynamicAccessor:: SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md) .

*nBlobSize*<br/>
En büyük BLOB boyutu bayt cinsinden; Bu değer üzerindeki sütun verileri bir BLOB olarak değerlendirilir. Varsayılan değer 8.000 ' dir. Ayrıntılar için bkz. [CDynamicAccessor:: SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md) .

### <a name="remarks"></a>Açıklamalar

BLOB işlemesi hakkında daha fazla bilgi için [CDynamicAccessor:: CDynamicAccessor](../../data/oledb/cdynamicaccessor-cdynamicaccessor.md) oluşturucusuna bakın.

## <a name="cdynamicparameteraccessorgetparam"></a><a name="getparam"></a>CDynamicParameterAccessor:: GetParam

Parametre arabelleğindeki belirtilen parametreye ait dize olmayan verileri alır.

### <a name="syntax"></a>Sözdizimi

```cpp
template <class ctype>bool GetParam(DBORDINAL nParam,
   ctype* pData) const throw();

template <class ctype> bool GetParam(TCHAR* pParamName,
   ctype* pData) const throw();

void* GetParam(DBORDINAL nParam) const throw();

void* GetParam(TCHAR* pParamName) const throw();
```

#### <a name="parameters"></a>Parametreler

*CType*<br/>
Veri türü olan şablonlu bir parametre.

*nParam*<br/>
'ndaki Parametre numarası (1 ' den fazla). 0 parametresi, dönüş değerleri için ayrılmıştır. Parametre numarası, SQL veya saklı yordam çağrısındaki sırası temelinde parametrenin dizinidir. Örnek için bkz. [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) .

*pParamName*<br/>
'ndaki Parametre adı.

*pData*<br/>
dışı Arabellekten alınan verileri içeren bellek işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Şablonlu olmayan sürümler için arabellekten alınan verileri içeren belleği işaret eder. Şablonlu sürümler için başarılı veya hatalı hata durumunda **false** **döndürür.**

Arabelleğinden dize olmayan parametre verilerini almak için `GetParam` kullanın. Arabellekteki dize parametresi verilerini almak için [GetParamString](../../data/oledb/cdynamicparameteraccessor-getparamstring.md) kullanın.

## <a name="cdynamicparameteraccessorgetparamcount"></a><a name="getparamcount"></a>CDynamicParameterAccessor:: GetParamCount

Arabellekte depolanan parametrelerin sayısını alır.

### <a name="syntax"></a>Sözdizimi

```cpp
DB_UPARAMS GetParamCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Parametre sayısı.

## <a name="cdynamicparameteraccessorgetparamio"></a><a name="getparamio"></a>CDynamicParameterAccessor:: Getparaıo

Belirtilen parametrenin bir giriş veya çıkış parametresi olup olmadığını belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
bool GetParamIO(DBORDINAL nParam,
   DBPARAMIO* pParamIO) const throw();
```

#### <a name="parameters"></a>Parametreler

*nParam*<br/>
'ndaki Parametre numarası (1 ' den fazla). 0 parametresi, dönüş değerleri için ayrılmıştır. Parametre numarası, SQL veya saklı yordam çağrısındaki sırası temelinde parametrenin dizinidir. Örnek için bkz. [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) .

*Pparaıo*<br/>
Belirtilen parametrenin `DBPARAMIO` türünü (giriş veya çıkış) içeren değişkene yönelik bir işaretçi. Aşağıdaki gibi tanımlanır:

```cpp
typedef DWORD DBPARAMIO;

enum DBPARAMIOENUM {
    DBPARAMIO_NOTPARAM   = 0,
    DBPARAMIO_INPUT      = 0x1,
    DBPARAMIO_OUTPUT     = 0x2
};
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı veya hatalı olduğunda **false** **döndürür.**

## <a name="cdynamicparameteraccessorgetparamlength"></a><a name="getparamlength"></a>CDynamicParameterAccessor:: GetParamLength

Arabellekte depolanan belirtilen parametrenin uzunluğunu alır.

### <a name="syntax"></a>Sözdizimi

```cpp
bool GetParamLength(DBORDINAL nParam,
   DBLENGTH* pLength);

DBLENGTH* GetParamLength(DBORDINAL nParam) const throw();
```

#### <a name="parameters"></a>Parametreler

*nParam*<br/>
'ndaki Parametre numarası (1 ' den fazla). 0 parametresi, dönüş değerleri için ayrılmıştır. Parametre numarası, SQL veya saklı yordam çağrısındaki sırası temelinde parametrenin dizinidir. Örnek için bkz. [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) .

*pLength*<br/>
dışı Belirtilen parametrenin bayt cinsinden uzunluğunu içeren değişkene yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

İlk geçersiz kılma başarılı veya hatalı olduğunda **false** **döndürür.** İkinci geçersiz kılma, parametrenin uzunluğunu içeren belleğe işaret eder.

## <a name="cdynamicparameteraccessorgetparamname"></a><a name="getparamname"></a>CDynamicParameterAccessor:: GetParamName

Belirtilen parametrenin adını alır.

### <a name="syntax"></a>Sözdizimi

```cpp
LPOLESTR GetParamName(DBORDINAL nParam) const throw();
```

#### <a name="parameters"></a>Parametreler

*nParam*<br/>
'ndaki Parametre numarası (1 ' den fazla). 0 parametresi, dönüş değerleri için ayrılmıştır. Parametre numarası, SQL veya saklı yordam çağrısındaki sırası temelinde parametrenin dizinidir. Örnek için bkz. [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) .

### <a name="return-value"></a>Dönüş Değeri

Belirtilen parametrenin adı.

## <a name="cdynamicparameteraccessorgetparamstatus"></a><a name="getparamstatus"></a>CDynamicParameterAccessor:: GetParamStatus

Arabellekte depolanan belirtilen parametrenin durumunu alır.

### <a name="syntax"></a>Sözdizimi

```cpp
bool GetParamStatus(DBORDINAL nParam,
   DBSTATUS* pStatus);

DBSTATUS* GetParamStatus(DBORDINAL nParam) const throw();
```

#### <a name="parameters"></a>Parametreler

*nParam*<br/>
'ndaki Parametre numarası (1 ' den fazla). 0 parametresi, dönüş değerleri için ayrılmıştır. Parametre numarası, SQL veya saklı yordam çağrısındaki sırası temelinde parametrenin dizinidir. Örnek için bkz. [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) .

*pStatus*<br/>
dışı Belirtilen parametrenin DBSTATUS durumunu içeren değişkene yönelik bir işaretçi. DBSTATUS değerleri hakkında daha fazla bilgi için *OLE DB Programcı başvurusunda* [durum](/previous-versions/windows/desktop/ms722617(v=vs.85)) ' a bakın veya OLEDB. h içinde DBSTATUS araması yapın.

### <a name="remarks"></a>Açıklamalar

İlk geçersiz kılma başarılı veya hatalı olduğunda **false** **döndürür.** İkinci geçersiz kılma, belirtilen parametrenin durumunu içeren belleğe işaret eder.

## <a name="cdynamicparameteraccessorgetparamstring"></a><a name="getparamstring"></a>CDynamicParameterAccessor:: GetParamString

Arabellekte depolanan belirtilen parametrenin dize verilerini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
bool GetParamString(DBORDINAL nParam,
   CSimpleStringA& strOutput) throw();

bool GetParamString(DBORDINAL nParam,
   CSimpleStringW& strOutput) throw();

bool GetParamString(DBORDINAL nParam,
   CHAR* pBuffer,
   size_t* pMaxLen) throw();

bool GetParamString(DBORDINAL nParam,
   WCHAR* pBuffer,
   size_t* pMaxLen) throw();
```

#### <a name="parameters"></a>Parametreler

*nParam*<br/>
'ndaki Parametre numarası (1 ' den fazla). 0 parametresi, dönüş değerleri için ayrılmıştır. Parametre numarası, SQL veya saklı yordam çağrısındaki sırası temelinde parametrenin dizinidir. Örnek için bkz. [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) .

*strOutput*<br/>
dışı Belirtilen parametrenin ANSI (`CSimpleStringA`) veya Unicode (`CSimpleStringW`) dize verileri. `CString`türünde bir parametre geçirmeniz gerekir, örneğin:

[!code-cpp[NVC_OLEDB_Consumer#9](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-getparamstring_1.cpp)]

*pBuffer*<br/>
dışı Belirtilen parametrenin ANSI (**char**) veya UNICODE (**wchar**) dize verilerine yönelik bir işaretçi.

*pMaxLen*<br/>
dışı *PBuffer* tarafından işaret edilen arabelleğin boyutuna yönelik bir işaretçi (, Sonlandırıcı null dahil olmak üzere karakter cinsinden).

### <a name="remarks"></a>Açıklamalar

Başarılı veya hatalı olduğunda **false** **döndürür.**

*PBuffer* null ise, bu yöntem *pMaxLen* tarafından işaret edilen bellek için gereken arabellek boyutunu ayarlar ve verileri kopyalamadan **doğru** döndürür.

Arabellek *pBuffer* tüm dizeyi içerecek kadar büyük değilse bu yöntem başarısız olur.

Arabellekteki dize parametresi verilerini almak için `GetParamString` kullanın. Arabellekteki dize olmayan parametre verilerini almak için [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) kullanın.

## <a name="cdynamicparameteraccessorgetparamtype"></a><a name="getparamtype"></a>CDynamicParameterAccessor:: GetParamType

Belirtilen parametrenin veri türünü alır.

### <a name="syntax"></a>Sözdizimi

```cpp
bool GetParamType(DBORDINAL nParam,
   DBTYPE* pType) const throw();
```

#### <a name="parameters"></a>Parametreler

*nParam*<br/>
'ndaki Parametre numarası (1 ' den fazla). 0 parametresi, dönüş değerleri için ayrılmıştır. Parametre numarası, SQL veya saklı yordam çağrısındaki sırası temelinde parametrenin dizinidir. Örnek için bkz. [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) .

*pType*<br/>
dışı Belirtilen parametrenin veri türünü içeren değişkene yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı veya hatalı olduğunda **false** **döndürür.**

## <a name="cdynamicparameteraccessorsetparam"></a><a name="setparam"></a>CDynamicParameterAccessor:: SetParam

Belirtilen (dize olmayan) verileri kullanarak parametre arabelleğini ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
template <class ctype>
bool SetParam(DBORDINAL nParam,
   constctype* pData,
   DBSTATUS status = DBSTATUS_S_OK) throw();

template <class ctype>
bool SetParam(TCHAR* pParamName,
   const ctype* pData,
   DBSTATUS status = DBSTATUS_S_OK) throw();
```

#### <a name="parameters"></a>Parametreler

*CType*<br/>
Veri türü olan şablonlu bir parametre.

*nParam*<br/>
'ndaki Parametre numarası (1 ' den fazla). 0 parametresi, dönüş değerleri için ayrılmıştır. Parametre numarası, SQL veya saklı yordam çağrısındaki sırası temelinde parametrenin dizinidir. Örneğin:

[!code-cpp[NVC_OLEDB_Consumer#8](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-setparam_1.cpp)]

*pParamName*<br/>
'ndaki Parametre adı.

*pData*<br/>
'ndaki Arabelleğe yazılacak verileri içeren belleğin işaretçisi.

*durumlarına*<br/>
'ndaki DBSTATUS sütun durumu. DBSTATUS değerleri hakkında daha fazla bilgi için *OLE DB Programcı başvurusunda* [durum](/previous-versions/windows/desktop/ms722617(v=vs.85)) ' a bakın veya OLEDB. h içinde DBSTATUS araması yapın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı veya hatalı olduğunda **false** **döndürür.**

Arabellekte dize olmayan parametre verilerini ayarlamak için `SetParam` kullanın. Arabellekte dize parametresi verilerini ayarlamak için [SetParamString](../../data/oledb/cdynamicparameteraccessor-setparamstring.md) kullanın.

## <a name="cdynamicparameteraccessorsetparamlength"></a><a name="setparamlength"></a>CDynamicParameterAccessor:: SetParamLength

Arabellekte depolanan belirtilen parametrenin uzunluğunu ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
bool SetParamLength(DBORDINAL nParam,
   DBLENGTH length);
```

#### <a name="parameters"></a>Parametreler

*nParam*<br/>
'ndaki Parametre numarası (1 ' den fazla). 0 parametresi, dönüş değerleri için ayrılmıştır. Parametre numarası, SQL veya saklı yordam çağrısındaki sırası temelinde parametrenin dizinidir. Örnek için bkz. [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) .

*uzunluklu*<br/>
'ndaki Belirtilen parametrenin bayt cinsinden uzunluğu.

### <a name="remarks"></a>Açıklamalar

Başarılı veya hatalı olduğunda **false** **döndürür.**

## <a name="cdynamicparameteraccessorsetparamstatus"></a><a name="setparamstatus"></a>CDynamicParameterAccessor:: SetParamStatus

Arabellekte depolanan belirtilen parametrenin durumunu ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
bool SetParamStatus(DBORDINAL nParam,
   DBSTATUS status);
```

#### <a name="parameters"></a>Parametreler

*nParam*<br/>
'ndaki Parametre numarası (1 ' den fazla). 0 parametresi, dönüş değerleri için ayrılmıştır. Parametre numarası, SQL veya saklı yordam çağrısındaki sırası temelinde parametrenin dizinidir. Örnek için bkz. [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) .

*durumlarına*<br/>
'ndaki Belirtilen parametrenin DBSTATUS durumu. DBSTATUS değerleri hakkında daha fazla bilgi için *OLE DB Programcı başvurusunda* [durum](/previous-versions/windows/desktop/ms722617(v=vs.85)) ' a bakın veya OLEDB. h içinde DBSTATUS araması yapın.

### <a name="remarks"></a>Açıklamalar

Başarılı veya hatalı olduğunda **false** **döndürür.**

## <a name="cdynamicparameteraccessorsetparamstring"></a><a name="setparamstring"></a>CDynamicParameterAccessor:: SetParamString

Arabellekte depolanan belirtilen parametrenin dize verilerini ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
bool SetParamString(DBORDINAL nParam,
   constCHAR* pString,
   DBSTATUS status = DBSTATUS_S_OK) throw();bool SetParamString(DBORDINAL nParam,
   constWCHAR* pString,
   DBSTATUS status = DBSTATUS_S_OK) throw();
```

#### <a name="parameters"></a>Parametreler

*nParam*<br/>
'ndaki Parametre numarası (1 ' den fazla). 0 parametresi, dönüş değerleri için ayrılmıştır. Parametre numarası, SQL veya saklı yordam çağrısındaki sırası temelinde parametrenin dizinidir. Örnek için bkz. [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) .

*Pstrıng*<br/>
'ndaki Belirtilen parametrenin ANSI (**char**) veya UNICODE (**wchar**) dize verilerine yönelik bir işaretçi. Bkz. OleDb. h içinde DBSTATUS.

*durumlarına*<br/>
'ndaki Belirtilen parametrenin DBSTATUS durumu. DBSTATUS değerleri hakkında daha fazla bilgi için *OLE DB Programcı başvurusunda* [durum](/previous-versions/windows/desktop/ms722617(v=vs.85)) ' a bakın veya OLEDB. h içinde DBSTATUS araması yapın.

### <a name="remarks"></a>Açıklamalar

Başarılı veya hatalı olduğunda **false** **döndürür.**

*pString*için belirtilen en büyük boyuttan daha büyük bir dize ayarlamaya çalışırsanız `SetParamString` başarısız olur.

Arabellekte dize parametresi verilerini ayarlamak için `SetParamString` kullanın. Arabellekte dize olmayan parametre verilerini ayarlamak için [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor Sınıfı](../../data/oledb/caccessor-class.md)<br/>
[CDynamicAccessor Sınıfı](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CManualAccessor Sınıfı](../../data/oledb/cmanualaccessor-class.md)
