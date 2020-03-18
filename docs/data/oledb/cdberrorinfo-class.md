---
title: CDBErrorInfo Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDBErrorInfo
- ATL::CDBErrorInfo
- ATL.CDBErrorInfo
- ATL.CDBErrorInfo.GetAllErrorInfo
- CDBErrorInfo::GetAllErrorInfo
- ATL::CDBErrorInfo::GetAllErrorInfo
- CDBErrorInfo.GetAllErrorInfo
- CDBErrorInfo::GetBasicErrorInfo
- ATL.CDBErrorInfo.GetBasicErrorInfo
- CDBErrorInfo.GetBasicErrorInfo
- ATL::CDBErrorInfo::GetBasicErrorInfo
- CDBErrorInfo::GetCustomErrorObject
- ATL.CDBErrorInfo.GetCustomErrorObject
- CDBErrorInfo.GetCustomErrorObject
- ATL::CDBErrorInfo::GetCustomErrorObject
- ATL.CDBErrorInfo.GetErrorInfo
- CDBErrorInfo.GetErrorInfo
- ATL::CDBErrorInfo::GetErrorInfo
- CDBErrorInfo::GetErrorInfo
- ATL.CDBErrorInfo.GetErrorParameters
- CDBErrorInfo::GetErrorParameters
- ATL::CDBErrorInfo::GetErrorParameters
- CDBErrorInfo.GetErrorParameters
- CDBErrorInfo.GetErrorRecords
- ATL.CDBErrorInfo.GetErrorRecords
- ATL::CDBErrorInfo::GetErrorRecords
- CDBErrorInfo::GetErrorRecords
helpviewer_keywords:
- CDBErrorInfo class
- GetAllErrorInfo method
- GetBasicErrorInfo method
- GetCustomErrorObject method
- GetErrorInfo method
- GetErrorParameters method
- GetErrorRecords method
ms.assetid: 9a5c18a2-ee3e-40f5-ab4c-581288d7f737
ms.openlocfilehash: 2d2b21652fd5ee3604c3c72c2168c3d9a495caf1
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447463"
---
# <a name="cdberrorinfo-class"></a>CDBErrorInfo Sınıfı

OLE DB [IErrorRecords](/previous-versions/windows/desktop/ms718112(v=vs.85)) arabirimini kullanarak OLE DB hata işleme için destek sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
class CDBErrorInfo
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[GetAllErrorInfo](#getallerrorinfo)|Bir hata kaydında bulunan tüm hata bilgilerini döndürür.|
|[GetBasicErrorInfo](#getbasicerrorinfo)|Belirtilen hatayla ilgili temel bilgileri döndürmek için [IErrorRecords:: GetBasicErrorInfo](/previous-versions/windows/desktop/ms723907(v=vs.85)) öğesini çağırır.|
|[GetCustomErrorObject](#getcustomerrorobject)|Özel bir hata nesnesindeki bir arabirime bir işaretçi döndürmek için [IErrorRecords:: GetCustomErrorObject](/previous-versions/windows/desktop/ms725417(v=vs.85)) öğesini çağırır.|
|[GetErrorInfo](#geterrorinfo)|Belirtilen kayda bir `IErrorInfo` arabirimi işaretçisi döndürmek için [IErrorRecords:: GetErrorInfo](/previous-versions/windows/desktop/ms711230(v=vs.85)) çağırır.|
|[GetErrorParameters](#geterrorparameters)|Hata parametrelerini döndürmek için [IErrorInfo:: GetErrorParameters](/previous-versions/windows/desktop/ms715793(v=vs.85)) ' i çağırır.|
|[GetErrorRecords](#geterrorrecords)|Belirtilen nesne için hata kayıtlarını alır.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim kullanıcıya bir veya daha fazla hata kaydı döndürür. Hata kayıtlarının sayımını almak için önce [CDBErrorInfo:: GetErrorRecords](../../data/oledb/cdberrorinfo-geterrorrecords.md) öğesini çağırın. Ardından, her bir kayıtla ilgili hata bilgilerini almak için [CDBErrorInfo:: GetAllErrorInfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md)gibi erişim işlevlerinden birini çağırın.

## <a name="getallerrorinfo"></a>CDBErrorInfo:: GetAllErrorInfo

Bir hata kaydında bulunan tüm hata bilgisi türlerini döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetAllErrorInfo(ULONG ulRecordNum,
   LCID lcid,  BSTR* pbstrDescription,
   BSTR* pbstrSource = NULL,
   GUID* pguid = NULL,
   DWORD* pdwHelpContext = NULL,
   BSTR* pbstrHelpFile = NULL) const throw();
```

#### <a name="parameters"></a>Parametreler

*ulRecordNum*<br/>
'ndaki Hata bilgilerinin döndürüleceği kaydın sıfır tabanlı numarası.

*lcid*<br/>
'ndaki Döndürülecek hata bilgileri için yerel ayar KIMLIĞI.

*pbstrDescription*<br/>
dışı Hatanın metin açıklamasına yönelik bir işaretçi veya yerel ayar desteklenmiyorsa NULL. Bkz. açıklamalar.

*pbstrSource*<br/>
dışı Hatayı oluşturan bileşenin adını içeren bir dize işaretçisi.

*PGUID*<br/>
dışı Hatayı tanımlayan arabirimin GUID 'sine yönelik bir işaretçi.

*pdwHelpContext*<br/>
dışı Hata için yardım bağlamı KIMLIĞINE yönelik bir işaretçi.

*pbstrHelpFile*<br/>
dışı Hatayı açıklayan Yardım dosyasının yolunu içeren bir dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK. *OLE DB Programcı 'nin* diğer dönüş değerleri için başvurusu Içindeki [IErrorRecords:: GetErrorInfo](/previous-versions/windows/desktop/ms711230(v=vs.85)) bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

*PbstrDescription* çıkış değeri, yerel ayar DESTEKLENMIYORSA değeri null olarak ayarlayan veya aşağıdaki koşulların her ikisi de doğru olduğunda `IErrorInfo::GetDescription`çağırarak dahili olarak elde edilir:

1. *LCID* değeri ABD İngilizcesi değil ve

1. *LCID* değeri, GetUserDefaultLCID tarafından döndürülen değere eşit değil.

## <a name="getbasicerrorinfo"></a>CDBErrorInfo:: GetBasicErrorInfo

Hata hakkında dönüş kodu ve sağlayıcıya özgü hata numarası gibi temel bilgileri döndürmek için [IErrorRecords:: GetBasicErrorInfo](/previous-versions/windows/desktop/ms723907(v=vs.85)) öğesini çağırır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetBasicErrorInfo(ULONG ulRecordNum,
   ERRORINFO* pErrorInfo) const throw();
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IErrorRecords:: GetBasicErrorInfo](/previous-versions/windows/desktop/ms723907(v=vs.85)) bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

## <a name="getcustomerrorobject"></a>CDBErrorInfo:: GetCustomErrorObject

Özel bir hata nesnesindeki bir arabirime bir işaretçi döndürmek için [IErrorRecords:: GetCustomErrorObject](/previous-versions/windows/desktop/ms725417(v=vs.85)) öğesini çağırır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetCustomErrorObject(ULONG ulRecordNum,
   REFIID riid,IUnknown** ppObject) const throw();
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IErrorRecords:: GetCustomErrorObject](/previous-versions/windows/desktop/ms725417(v=vs.85)) bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

## <a name="geterrorinfo"></a>CDBErrorInfo:: GetErrorInfo

Belirtilen kayda bir [IErrorInfo](/previous-versions/windows/desktop/ms718112(v=vs.85)) arabirimi işaretçisi döndürmek Için [IErrorRecords:: GetErrorInfo](/previous-versions/windows/desktop/ms711230(v=vs.85)) çağırır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetErrorInfo(ULONG ulRecordNum,
   LCID lcid,IErrorInfo** ppErrorInfo) const throw();
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IErrorRecords:: GetErrorInfo](/previous-versions/windows/desktop/ms711230(v=vs.85)) bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

## <a name="geterrorparameters"></a>CDBErrorInfo:: GetErrorParameters

Hata parametrelerini döndürmek için [IErrorInfo:: GetErrorParameters](/previous-versions/windows/desktop/ms715793(v=vs.85)) ' i çağırır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetErrorParameters(ULONG ulRecordNum,
   DISPPARAMS* pdispparams) const throw();
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IErrorRecords:: GetErrorParameters](/previous-versions/windows/desktop/ms715793(v=vs.85)) bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

## <a name="geterrorrecords"></a>CDBErrorInfo:: GetErrorRecords

Belirtilen nesne için hata kayıtlarını alır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetErrorRecords(IUnknown* pUnk,
   const IID& iid,
   ULONG* pcRecords) throw();

HRESULT GetErrorRecords(ULONG* pcRecords) throw();
```

#### <a name="parameters"></a>Parametreler

*pUnk dili*<br/>
'ndaki Hata kayıtlarının alınacağı nesneye yönelik arabirim.

*'si*<br/>
'ndaki Hatayla ilişkili arabirimin IID 'si.

*pcRecords*<br/>
dışı Hata kayıtlarının (tek tabanlı) sayısına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Hangi arabirimin hata bilgisinin alınacağını denetlemek istiyorsanız, işlevin ilk biçimini kullanın. Aksi takdirde, ikinci formu kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[DBViewer](../../overview/visual-cpp-samples.md)<br/>
[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)