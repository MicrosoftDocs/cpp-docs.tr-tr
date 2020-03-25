---
title: IErrorRecordsImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL::IErrorRecordsImpl
- ATL.IErrorRecordsImpl
- IErrorRecordsImpl
- GetErrorDescriptionString
- IErrorRecordsImpl.GetErrorDescriptionString
- IErrorRecordsImpl::GetErrorDescriptionString
- GetErrorGUID
- IErrorRecordsImpl.GetErrorGUID
- IErrorRecordsImpl::GetErrorGUID
- GetErrorHelpContext
- IErrorRecordsImpl::GetErrorHelpContext
- IErrorRecordsImpl.GetErrorHelpContext
- IErrorRecordsImpl::GetErrorHelpFile
- GetErrorHelpFile
- IErrorRecordsImpl.GetErrorHelpFile
- IErrorRecordsImpl.GetErrorSource
- GetErrorSource
- IErrorRecordsImpl::GetErrorSource
- IErrorRecordsImpl.AddErrorRecord
- AddErrorRecord
- IErrorRecordsImpl::AddErrorRecord
- ATL::IErrorRecordsImpl::GetBasicErrorInfo
- IErrorRecordsImpl::GetBasicErrorInfo
- GetBasicErrorInfo
- ATL.IErrorRecordsImpl.GetBasicErrorInfo
- IErrorRecordsImpl.GetBasicErrorInfo
- ATL::IErrorRecordsImpl::GetCustomErrorObject
- IErrorRecordsImpl::GetCustomErrorObject
- ATL.IErrorRecordsImpl.GetCustomErrorObject
- IErrorRecordsImpl.GetCustomErrorObject
- IErrorRecordsImpl.GetErrorInfo
- IErrorRecordsImpl::GetErrorInfo
- IErrorRecordsImpl::GetErrorParameters
- ATL.IErrorRecordsImpl.GetErrorParameters
- IErrorRecordsImpl.GetErrorParameters
- GetErrorParameters
- ATL::IErrorRecordsImpl::GetErrorParameters
- IErrorRecordsImpl::GetRecordCount
- ATL::IErrorRecordsImpl::GetRecordCount
- IErrorRecordsImpl.GetRecordCount
- ATL.IErrorRecordsImpl.GetRecordCount
- IErrorRecordsImpl::m_rgErrors
- IErrorRecordsImpl.m_rgErrors
- ATL.IErrorRecordsImpl.m_rgErrors
- m_rgErrors
- ATL::IErrorRecordsImpl::m_rgErrors
helpviewer_keywords:
- IErrorRecordsImpl class
- GetErrorDescriptionString method
- GetErrorGUID method
- GetErrorHelpContext method
- GetErrorHelpFile method
- GetErrorSource method
- AddErrorRecord method
- GetBasicErrorInfo method
- GetCustomErrorObject method
- GetErrorInfo method
- GetErrorParameters method
- GetRecordCount method
- m_rgErrors
ms.assetid: dea8e938-c5d8-45ab-86de-eb8fbf534ffb
ms.openlocfilehash: 40ac0b248e1e90dae29a787d59f6ded9581aca70
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210606"
---
# <a name="ierrorrecordsimpl-class"></a>IErrorRecordsImpl Sınıfı

OLE DB [IErrorRecords](/previous-versions/windows/desktop/ms718112(v=vs.85)) arabirimini uygular, **CAtlArray <** `RecordClass` **>** türünde bir veri üyesine ([m_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)) kayıt ekleme ve kayıtları alma.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class RecordClass = ATLERRORINFO>
class IErrorRecordsImpl : public IErrorRecords
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
`IErrorRecordsImpl`türetilen bir sınıf.

*RecordClass*<br/>
OLE DB Error nesnesini temsil eden bir sınıf.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[GetErrorDescriptionString](#geterrordescriptionstring)|Hata kaydından hata açıklaması dizesini alır.|
|[Geterrorguıd](#geterrorguid)|Hata kaydından hata GUID 'sini alır.|
|[GetErrorHelpContext](#geterrorhelpcontext)|Bir hata kaydından yardım bağlamı KIMLIĞINI alır.|
|[GetErrorHelpFile](#geterrorhelpfile)|Bir hata kaydındaki yardım dosyasının tam yol adını alır.|
|[GetErrorSource](#geterrorsource)|Bir hata kaydındaki hata kaynak kodunu alır.|

### <a name="interface-methods"></a>Arabirim yöntemleri

|||
|-|-|
|[AddErrorRecord](#adderrorrecord)|OLE DB Error nesnesine bir kayıt ekler.|
|[GetBasicErrorInfo](#getbasicerrorinfo)|Hata hakkında, dönüş kodu ve sağlayıcıya özgü hata numarası gibi temel bilgileri döndürür.|
|[GetCustomErrorObject](#getcustomerrorobject)|Özel bir hata nesnesindeki arabirime yönelik bir işaretçi döndürür.|
|[GetErrorInfo](#geterrorinfo)|Belirtilen kayıt üzerinde bir [IErrorInfo](/previous-versions/windows/desktop/ms718112(v=vs.85)) arabirimi işaretçisi döndürür.|
|[GetErrorParameters](#geterrorparameters)|Hata parametrelerini döndürür.|
|[GetRecordCount](#getrecordcount)|OLE DB kaydı nesnesindeki kayıt sayısını döndürür.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[m_rgErrors](#rgerrors)|Bir hata kaydı dizisi.|

## <a name="ierrorrecordsimplgeterrordescriptionstring"></a><a name="geterrordescriptionstring"></a>Ierrorrecordsimpl:: GetErrorDescriptionString

Hata kaydından hata açıklaması dizesini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
LPOLESTR GetErrorDescriptionString(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>Parametreler

*rCurError*<br/>
Bir `IErrorInfo` arabirimindeki `ERRORINFO` kaydı.

### <a name="return-value"></a>Dönüş Değeri

Hatayı açıklayan bir dizeye yönelik bir işaretçi.

## <a name="ierrorrecordsimplgeterrorguid"></a><a name="geterrorguid"></a>Ierrorrecordsimpl:: GetErrorGUID

Hata kaydından hata GUID 'sini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
REFGUID GetErrorGUID(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>Parametreler

*rCurError*<br/>
Bir `IErrorInfo` arabirimindeki `ERRORINFO` kaydı.

### <a name="return-value"></a>Dönüş Değeri

Hata için bir GUID başvurusu.

## <a name="ierrorrecordsimplgeterrorhelpcontext"></a><a name="geterrorhelpcontext"></a>Ierrorrecordsimpl:: GetErrorHelpContext

Bir hata kaydından yardım bağlamı KIMLIĞINI alır.

### <a name="syntax"></a>Sözdizimi

```cpp
DWORD GetErrorHelpContext(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>Parametreler

*rCurError*<br/>
Bir `IErrorInfo` arabirimindeki `ERRORINFO` kaydı.

### <a name="return-value"></a>Dönüş Değeri

Hatanın yardım bağlamı KIMLIĞI.

## <a name="ierrorrecordsimplgeterrorhelpfile"></a><a name="geterrorhelpfile"></a>Ierrorrecordsimpl:: GetErrorHelpFile

Bir hata kaydındaki yardım dosyasının yol adını alır.

### <a name="syntax"></a>Sözdizimi

```cpp
LPOLESTR GetErrorHelpFile(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>Parametreler

*rCurError*<br/>
Bir `IErrorInfo` arabirimindeki `ERRORINFO` kaydı.

### <a name="return-value"></a>Dönüş Değeri

Hata için yardım dosyasının yol adını içeren bir dize işaretçisi.

## <a name="ierrorrecordsimplgeterrorsource"></a><a name="geterrorsource"></a>Ierrorrecordsimpl:: GetErrorSource

Hata kaydından hataya neden olan kaynak kodunu alır.

### <a name="syntax"></a>Sözdizimi

```cpp
LPOLESTR GetErrorSource(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>Parametreler

*rCurError*<br/>
Bir `IErrorInfo` arabirimindeki `ERRORINFO` kaydı.

### <a name="return-value"></a>Dönüş Değeri

Hata için kaynak kodu içeren bir dize işaretçisi.

## <a name="ierrorrecordsimpladderrorrecord"></a><a name="adderrorrecord"></a>Ierrorrecordsimpl:: AddErrorRecord

OLE DB Error nesnesine bir kayıt ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(AddErrorRecord )(ERRORINFO *pErrorInfo,
   DWORD dwLookupID,
   DISPPARAMS *pdispparams,
   IUnknown *punkCustomError,
   DWORD dwDynamicErrorID);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IErrorRecords:: adderrorrecord](/previous-versions/windows/desktop/ms725362(v=vs.85)) öğesine bakın.

## <a name="ierrorrecordsimplgetbasicerrorinfo"></a><a name="getbasicerrorinfo"></a>Ierrorrecordsimpl:: GetBasicErrorInfo

Hata hakkında, dönüş kodu ve sağlayıcıya özgü hata numarası gibi temel bilgileri döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(GetBasicErrorInfo )(ULONG ulRecordNum,
   ERRORINFO *pErrorInfo);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IErrorRecords:: GetBasicErrorInfo](/previous-versions/windows/desktop/ms723907(v=vs.85)) bölümüne bakın.

## <a name="ierrorrecordsimplgetcustomerrorobject"></a><a name="getcustomerrorobject"></a>Ierrorrecordsimpl:: GetCustomErrorObject

Özel bir hata nesnesindeki arabirime yönelik bir işaretçi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(GetCustomErrorObject )(ULONG ulRecordNum,
   REFIID riid,
   IUnknown **ppObject);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IErrorRecords:: GetCustomErrorObject](/previous-versions/windows/desktop/ms725417(v=vs.85)) bölümüne bakın.

## <a name="ierrorrecordsimplgeterrorinfo"></a><a name="geterrorinfo"></a>Ierrorrecordsimpl:: GetErrorInfo

Belirtilen kayıt üzerinde bir [IErrorInfo](/previous-versions/windows/desktop/ms718112(v=vs.85)) arabirimi işaretçisi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(GetErrorInfo )(ULONG ulRecordNum,
   LCID lcid,
   IErrorInfo **ppErrorInfo);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IErrorRecords:: GetErrorInfo](/previous-versions/windows/desktop/ms711230(v=vs.85)) bölümüne bakın.

## <a name="ierrorrecordsimplgeterrorparameters"></a><a name="geterrorparameters"></a>Ierrorrecordsimpl:: GetErrorParameters

Hata parametrelerini döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(GetErrorParameters )(ULONG ulRecordNum,
   DISPPARAMS *pdispparams);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IErrorRecords:: GetErrorParameters](/previous-versions/windows/desktop/ms715793(v=vs.85)) bölümüne bakın.

## <a name="ierrorrecordsimplgetrecordcount"></a><a name="getrecordcount"></a>Ierrorrecordsimpl:: GetRecordCount

OLE DB kaydı nesnesindeki kayıt sayısını döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(GetRecordCount )(ULONG *pcRecords);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IErrorRecords:: GetRecordCount](/previous-versions/windows/desktop/ms722724(v=vs.85)) öğesine bakın.

## <a name="ierrorrecordsimplm_rgerrors"></a><a name="rgerrors"></a>Ierrorrecordsimpl:: m_rgErrors

Bir hata kaydı dizisi.

### <a name="syntax"></a>Sözdizimi

```cpp
CAtlArray< RecordClass > m_rgErrors;
```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
