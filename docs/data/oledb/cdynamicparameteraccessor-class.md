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
ms.openlocfilehash: 4596f5181dd197b16786ee4d4d16cf06721b13b6
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91498655"
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

| Ad | Açıklama |
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

Sağlayıcı, `ICommandWithParameters` tüketicinin bu sınıfı kullanması için destek sağlamalıdır.

Parametre bilgileri, bu sınıf tarafından oluşturulan ve yönetilen bir arabellekte saklanır. [GetParam](#getparam) ve [GetParamType](#getparamtype)kullanarak arabellekteki parametre verilerini elde edin.

Bu sınıfın bir SQL Server saklı yordamı yürütmek ve çıkış parametre değerlerini almak için nasıl kullanılacağını gösteren bir örnek için GitHub 'daki [Microsoft VCSamples](https://github.com/Microsoft/VCSamples) deposundaki [DynamicConsumer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer) örnek koduna bakın.

## <a name="cdynamicparameteraccessorcdynamicparameteraccessor"></a><a name="cdynamicparameteraccessor"></a> CDynamicParameterAccessor:: CDynamicParameterAccessor

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
BLOB verilerinin nasıl işleneceğini belirtir. Varsayılan değer DBBLOBHANDLING_DEFAULT. DBBLOBHANDLINGENUM değerlerinin açıklaması için bkz. [CDynamicAccessor:: SetBlobHandling](./cdynamicaccessor-class.md#setblobhandling) .

*nBlobSize*<br/>
En büyük BLOB boyutu bayt cinsinden; Bu değer üzerindeki sütun verileri bir BLOB olarak değerlendirilir. Varsayılan değer 8.000 ' dir. Ayrıntılar için bkz. [CDynamicAccessor:: SetBlobSizeLimit](./cdynamicaccessor-class.md#setblobsizelimit) .

### <a name="remarks"></a>Açıklamalar

BLOB işlemesi hakkında daha fazla bilgi için [CDynamicAccessor:: CDynamicAccessor](./cdynamicaccessor-class.md#cdynamicaccessor) oluşturucusuna bakın.

## <a name="cdynamicparameteraccessorgetparam"></a><a name="getparam"></a> CDynamicParameterAccessor:: GetParam

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
'ndaki Parametre numarası (1 ' den fazla). 0 parametresi, dönüş değerleri için ayrılmıştır. Parametre numarası, SQL veya saklı yordam çağrısındaki sırası temelinde parametrenin dizinidir. Örnek için bkz. [SetParam](#setparam) .

*pParamName*<br/>
'ndaki Parametre adı.

*pData*<br/>
dışı Arabellekten alınan verileri içeren bellek işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Şablonlu olmayan sürümler için arabellekten alınan verileri içeren belleği işaret eder. Şablonlu sürümler için **`true`** başarı veya başarısızlık durumunda döndürür **`false`** .

`GetParam`Arabelleğinden dize olmayan parametre verilerini almak için kullanın. Arabellekteki dize parametresi verilerini almak için [GetParamString](#getparamstring) kullanın.

## <a name="cdynamicparameteraccessorgetparamcount"></a><a name="getparamcount"></a> CDynamicParameterAccessor:: GetParamCount

Arabellekte depolanan parametrelerin sayısını alır.

### <a name="syntax"></a>Sözdizimi

```cpp
DB_UPARAMS GetParamCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Parametre sayısı.

## <a name="cdynamicparameteraccessorgetparamio"></a><a name="getparamio"></a> CDynamicParameterAccessor:: Getparaıo

Belirtilen parametrenin bir giriş veya çıkış parametresi olup olmadığını belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
bool GetParamIO(DBORDINAL nParam,
   DBPARAMIO* pParamIO) const throw();
```

#### <a name="parameters"></a>Parametreler

*nParam*<br/>
'ndaki Parametre numarası (1 ' den fazla). 0 parametresi, dönüş değerleri için ayrılmıştır. Parametre numarası, SQL veya saklı yordam çağrısındaki sırası temelinde parametrenin dizinidir. Örnek için bkz. [SetParam](#setparam) .

*Pparaıo*<br/>
`DBPARAMIO`Belirtilen parametrenin türünü (giriş veya çıkış) içeren değişkene yönelik bir işaretçi. Aşağıdaki gibi tanımlanır:

```cpp
typedef DWORD DBPARAMIO;

enum DBPARAMIOENUM {
    DBPARAMIO_NOTPARAM   = 0,
    DBPARAMIO_INPUT      = 0x1,
    DBPARAMIO_OUTPUT     = 0x2
};
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** Başarılı veya başarısız durumuna geri döner **`false`** .

## <a name="cdynamicparameteraccessorgetparamlength"></a><a name="getparamlength"></a> CDynamicParameterAccessor:: GetParamLength

Arabellekte depolanan belirtilen parametrenin uzunluğunu alır.

### <a name="syntax"></a>Sözdizimi

```cpp
bool GetParamLength(DBORDINAL nParam,
   DBLENGTH* pLength);

DBLENGTH* GetParamLength(DBORDINAL nParam) const throw();
```

#### <a name="parameters"></a>Parametreler

*nParam*<br/>
'ndaki Parametre numarası (1 ' den fazla). 0 parametresi, dönüş değerleri için ayrılmıştır. Parametre numarası, SQL veya saklı yordam çağrısındaki sırası temelinde parametrenin dizinidir. Örnek için bkz. [SetParam](#setparam) .

*pLength*<br/>
dışı Belirtilen parametrenin bayt cinsinden uzunluğunu içeren değişkene yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

İlk geçersiz kılma **`true`** başarı veya başarısızlık durumunda geri döner **`false`** . İkinci geçersiz kılma, parametrenin uzunluğunu içeren belleğe işaret eder.

## <a name="cdynamicparameteraccessorgetparamname"></a><a name="getparamname"></a> CDynamicParameterAccessor:: GetParamName

Belirtilen parametrenin adını alır.

### <a name="syntax"></a>Sözdizimi

```cpp
LPOLESTR GetParamName(DBORDINAL nParam) const throw();
```

#### <a name="parameters"></a>Parametreler

*nParam*<br/>
'ndaki Parametre numarası (1 ' den fazla). 0 parametresi, dönüş değerleri için ayrılmıştır. Parametre numarası, SQL veya saklı yordam çağrısındaki sırası temelinde parametrenin dizinidir. Örnek için bkz. [SetParam](#setparam) .

### <a name="return-value"></a>Dönüş Değeri

Belirtilen parametrenin adı.

## <a name="cdynamicparameteraccessorgetparamstatus"></a><a name="getparamstatus"></a> CDynamicParameterAccessor:: GetParamStatus

Arabellekte depolanan belirtilen parametrenin durumunu alır.

### <a name="syntax"></a>Sözdizimi

```cpp
bool GetParamStatus(DBORDINAL nParam,
   DBSTATUS* pStatus);

DBSTATUS* GetParamStatus(DBORDINAL nParam) const throw();
```

#### <a name="parameters"></a>Parametreler

*nParam*<br/>
'ndaki Parametre numarası (1 ' den fazla). 0 parametresi, dönüş değerleri için ayrılmıştır. Parametre numarası, SQL veya saklı yordam çağrısındaki sırası temelinde parametrenin dizinidir. Örnek için bkz. [SetParam](#setparam) .

*pStatus*<br/>
dışı Belirtilen parametrenin DBSTATUS durumunu içeren değişkene yönelik bir işaretçi. DBSTATUS değerleri hakkında daha fazla bilgi için *OLE DB Programcı başvurusunda* [durum](/previous-versions/windows/desktop/ms722617(v=vs.85)) ' a bakın veya OLEDB. h içinde DBSTATUS araması yapın.

### <a name="remarks"></a>Açıklamalar

İlk geçersiz kılma **`true`** başarı veya başarısızlık durumunda geri döner **`false`** . İkinci geçersiz kılma, belirtilen parametrenin durumunu içeren belleğe işaret eder.

## <a name="cdynamicparameteraccessorgetparamstring"></a><a name="getparamstring"></a> CDynamicParameterAccessor:: GetParamString

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
'ndaki Parametre numarası (1 ' den fazla). 0 parametresi, dönüş değerleri için ayrılmıştır. Parametre numarası, SQL veya saklı yordam çağrısındaki sırası temelinde parametrenin dizinidir. Örnek için bkz. [SetParam](#setparam) .

*strOutput*<br/>
dışı `CSimpleStringA`Belirtilen PARAMETRENIN ANSI () veya UNICODE ( `CSimpleStringW` ) dize verileri. Türünde bir parametre geçirmeniz gerekir `CString` , örneğin:

[!code-cpp[NVC_OLEDB_Consumer#9](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-getparamstring_1.cpp)]

*pBuffer*<br/>
dışı Belirtilen parametrenin ANSI (**char**) veya UNICODE (**wchar**) dize verilerine yönelik bir işaretçi.

*pMaxLen*<br/>
dışı *PBuffer* tarafından işaret edilen arabelleğin boyutuna yönelik bir işaretçi (, Sonlandırıcı null dahil olmak üzere karakter cinsinden).

### <a name="remarks"></a>Açıklamalar

**`true`** Başarılı veya başarısız durumuna geri döner **`false`** .

*PBuffer* null ise, bu yöntem, *pMaxLen* tarafından işaret edilen bellekteki gerekli arabellek boyutunu ayarlar ve **`true`** verileri kopyalamadan döndürülür.

Arabellek *pBuffer* tüm dizeyi içerecek kadar büyük değilse bu yöntem başarısız olur.

`GetParamString`Arabellekteki dize parametresi verilerini almak için kullanın. Arabellekteki dize olmayan parametre verilerini almak için [GetParam](#getparam) kullanın.

## <a name="cdynamicparameteraccessorgetparamtype"></a><a name="getparamtype"></a> CDynamicParameterAccessor:: GetParamType

Belirtilen parametrenin veri türünü alır.

### <a name="syntax"></a>Sözdizimi

```cpp
bool GetParamType(DBORDINAL nParam,
   DBTYPE* pType) const throw();
```

#### <a name="parameters"></a>Parametreler

*nParam*<br/>
'ndaki Parametre numarası (1 ' den fazla). 0 parametresi, dönüş değerleri için ayrılmıştır. Parametre numarası, SQL veya saklı yordam çağrısındaki sırası temelinde parametrenin dizinidir. Örnek için bkz. [SetParam](#setparam) .

*pType*<br/>
dışı Belirtilen parametrenin veri türünü içeren değişkene yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** Başarılı veya başarısız durumuna geri döner **`false`** .

## <a name="cdynamicparameteraccessorsetparam"></a><a name="setparam"></a> CDynamicParameterAccessor:: SetParam

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

**`true`** Başarılı veya başarısız durumuna geri döner **`false`** .

`SetParam`Arabellekte dize olmayan parametre verilerini ayarlamak için kullanın. Arabellekte dize parametresi verilerini ayarlamak için [SetParamString](#setparamstring) kullanın.

## <a name="cdynamicparameteraccessorsetparamlength"></a><a name="setparamlength"></a> CDynamicParameterAccessor:: SetParamLength

Arabellekte depolanan belirtilen parametrenin uzunluğunu ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
bool SetParamLength(DBORDINAL nParam,
   DBLENGTH length);
```

#### <a name="parameters"></a>Parametreler

*nParam*<br/>
'ndaki Parametre numarası (1 ' den fazla). 0 parametresi, dönüş değerleri için ayrılmıştır. Parametre numarası, SQL veya saklı yordam çağrısındaki sırası temelinde parametrenin dizinidir. Örnek için bkz. [SetParam](#setparam) .

*length*<br/>
'ndaki Belirtilen parametrenin bayt cinsinden uzunluğu.

### <a name="remarks"></a>Açıklamalar

**`true`** Başarılı veya başarısız durumuna geri döner **`false`** .

## <a name="cdynamicparameteraccessorsetparamstatus"></a><a name="setparamstatus"></a> CDynamicParameterAccessor:: SetParamStatus

Arabellekte depolanan belirtilen parametrenin durumunu ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
bool SetParamStatus(DBORDINAL nParam,
   DBSTATUS status);
```

#### <a name="parameters"></a>Parametreler

*nParam*<br/>
'ndaki Parametre numarası (1 ' den fazla). 0 parametresi, dönüş değerleri için ayrılmıştır. Parametre numarası, SQL veya saklı yordam çağrısındaki sırası temelinde parametrenin dizinidir. Örnek için bkz. [SetParam](#setparam) .

*durumlarına*<br/>
'ndaki Belirtilen parametrenin DBSTATUS durumu. DBSTATUS değerleri hakkında daha fazla bilgi için *OLE DB Programcı başvurusunda* [durum](/previous-versions/windows/desktop/ms722617(v=vs.85)) ' a bakın veya OLEDB. h içinde DBSTATUS araması yapın.

### <a name="remarks"></a>Açıklamalar

**`true`** Başarılı veya başarısız durumuna geri döner **`false`** .

## <a name="cdynamicparameteraccessorsetparamstring"></a><a name="setparamstring"></a> CDynamicParameterAccessor:: SetParamString

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
'ndaki Parametre numarası (1 ' den fazla). 0 parametresi, dönüş değerleri için ayrılmıştır. Parametre numarası, SQL veya saklı yordam çağrısındaki sırası temelinde parametrenin dizinidir. Örnek için bkz. [SetParam](#setparam) .

*Pstrıng*<br/>
'ndaki Belirtilen parametrenin ANSI (**char**) veya UNICODE (**wchar**) dize verilerine yönelik bir işaretçi. Bkz. OleDb. h içinde DBSTATUS.

*durumlarına*<br/>
'ndaki Belirtilen parametrenin DBSTATUS durumu. DBSTATUS değerleri hakkında daha fazla bilgi için *OLE DB Programcı başvurusunda* [durum](/previous-versions/windows/desktop/ms722617(v=vs.85)) ' a bakın veya OLEDB. h içinde DBSTATUS araması yapın.

### <a name="remarks"></a>Açıklamalar

**`true`** Başarılı veya başarısız durumuna geri döner **`false`** .

`SetParamString`*pString*için belirtilen en büyük boyuttan daha büyük bir dize ayarlamaya çalışırsanız başarısız olur.

`SetParamString`Arabellekte dize parametresi verilerini ayarlamak için kullanın. Arabellekte dize olmayan parametre verilerini ayarlamak için [SetParam](#setparam) kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB tüketici şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor sınıfı](../../data/oledb/caccessor-class.md)<br/>
[CDynamicAccessor sınıfı](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CManualAccessor sınıfı](../../data/oledb/cmanualaccessor-class.md)
