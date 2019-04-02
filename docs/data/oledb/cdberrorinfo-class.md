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
- GetAllErrorInfo
- CDBErrorInfo.GetAllErrorInfo
- CDBErrorInfo::GetBasicErrorInfo
- ATL.CDBErrorInfo.GetBasicErrorInfo
- CDBErrorInfo.GetBasicErrorInfo
- ATL::CDBErrorInfo::GetBasicErrorInfo
- GetBasicErrorInfo
- CDBErrorInfo::GetCustomErrorObject
- ATL.CDBErrorInfo.GetCustomErrorObject
- CDBErrorInfo.GetCustomErrorObject
- ATL::CDBErrorInfo::GetCustomErrorObject
- GetCustomErrorObject
- GetErrorInfo
- ATL.CDBErrorInfo.GetErrorInfo
- CDBErrorInfo.GetErrorInfo
- ATL::CDBErrorInfo::GetErrorInfo
- CDBErrorInfo::GetErrorInfo
- ATL.CDBErrorInfo.GetErrorParameters
- CDBErrorInfo::GetErrorParameters
- ATL::CDBErrorInfo::GetErrorParameters
- CDBErrorInfo.GetErrorParameters
- GetErrorParameters
- CDBErrorInfo.GetErrorRecords
- ATL.CDBErrorInfo.GetErrorRecords
- ATL::CDBErrorInfo::GetErrorRecords
- GetErrorRecords
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
ms.openlocfilehash: 9a047263022c45ddc2fcb98dc618a4c6075bfd75
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58778357"
---
# <a name="cdberrorinfo-class"></a>CDBErrorInfo Sınıfı

OLE DB kullanarak OLE DB hata işleme için destek sağlayan [IErrorRecords](/previous-versions/windows/desktop/ms718112(v=vs.85)) arabirimi.

## <a name="syntax"></a>Sözdizimi

```cpp
class CDBErrorInfo
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldbcli.h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[GetAllErrorInfo](#getallerrorinfo)|Bir hata kaydında bulunan tüm hata bilgilerini döndürür.|
|[GetBasicErrorInfo](#getbasicerrorinfo)|Çağrıları [IErrorRecords::GetBasicErrorInfo](/previous-versions/windows/desktop/ms723907(v=vs.85)) belirtilen hata hakkındaki temel bilgileri döndürmek için.|
|[GetCustomErrorObject](#getcustomerrorobject)|Çağrıları [IErrorRecords::GetCustomErrorObject](/previous-versions/windows/desktop/ms725417(v=vs.85)) bir özel hata nesnesi üzerinde bir arabirim işaretçisi döndürülecek.|
|[GetErrorInfo](#geterrorinfo)|Çağrıları [IErrorRecords::GetErrorInfo](/previous-versions/windows/desktop/ms711230(v=vs.85)) döndürülecek bir `IErrorInfo` belirtilen kayıt arabirim işaretçisi.|
|[GetErrorParameters](#geterrorparameters)|Çağrıları [IErrorRecords::GetErrorParameters](/previous-versions/windows/desktop/ms715793(v=vs.85)) hata parametreleri dönün.|
|[GetErrorRecords](#geterrorrecords)|Belirtilen nesne için hata kayıtları alır.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim, kullanıcıya bir veya daha fazla hata kaydı döndürür. Çağrı [Cdberrorınfo::geterrorrecords](../../data/oledb/cdberrorinfo-geterrorrecords.md) hata kaydı sayısını almak için ilk olarak,. Ardından gibi erişim biri işlev çağrısı [Cdberrorınfo::getallerrorınfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md), her kayıt için hata bilgisi alınamıyor.

## <a name="getallerrorinfo"></a> Cdberrorınfo::getallerrorınfo

Hata bilgilerini bir hata kaydında bulunan tüm türlerini döndürür.

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
[in] Sıfır tabanlı hata bilgilerini döndürülecek kayıt sayısı.

*lcid*<br/>
[in] Yerel ayar kimliği döndürülen hata bilgileri için.

*pbstrDescription*<br/>
[out] Bir metin açıklama hata ya da yerel desteklenmiyorsa NULL bir işaretçi. Açıklamalara bakın.

*pbstrSource*<br/>
[out] Hatayı oluşturan bileşen adını içeren bir dize işaretçisi.

*pguid*<br/>
[out] GUID hata tanımlı arabiriminin bir işaretçi.

*pdwHelpContext*<br/>
[out] Hata için Yardım içeriği kimliği için bir işaretçi.

*pbstrHelpFile*<br/>
[out] Hatayı açıklayan Yardım dosyasının yolunu içeren bir dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK. Bkz: [IErrorRecords::GetErrorInfo](/previous-versions/windows/desktop/ms711230(v=vs.85)) içinde *OLE DB Programcının Başvurusu* diğer dönüş değerleri için.

### <a name="remarks"></a>Açıklamalar

Çıkış değeri *pbstrDescription* dahili olarak çağırılarak alınır `IErrorInfo::GetDescription`, ayarlar değeri NULL olarak yerel ayarı desteklenmiyor veya aşağıdaki koşulların her ikisi de doğruysa:

1. değerini *LCID* ABD değil İngilizce ve

1. değerini *LCID* olan GetUserDefaultLCID tarafından döndürülen değer eşit değildir.

## <a name="getbasicerrorinfo"></a> Cdberrorınfo::getbasicerrorınfo

Çağrıları [IErrorRecords::GetBasicErrorInfo](/previous-versions/windows/desktop/ms723907(v=vs.85)) sağlayıcıya özgü hata numarası ve dönüş kodu gibi bir hata ile ilgili temel bilgileri döndürmek için.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetBasicErrorInfo(ULONG ulRecordNum,
   ERRORINFO* pErrorInfo) const throw();
```

#### <a name="parameters"></a>Parametreler

Bkz: [IErrorRecords::GetBasicErrorInfo](/previous-versions/windows/desktop/ms723907(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

## <a name="getcustomerrorobject"></a> Cdberrorınfo::getcustomerrorobject

Çağrıları [IErrorRecords::GetCustomErrorObject](/previous-versions/windows/desktop/ms725417(v=vs.85)) bir özel hata nesnesi üzerinde bir arabirim işaretçisi döndürülecek.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetCustomErrorObject(ULONG ulRecordNum,
   REFIID riid,IUnknown** ppObject) const throw();
```

#### <a name="parameters"></a>Parametreler

Bkz: [IErrorRecords::GetCustomErrorObject](/previous-versions/windows/desktop/ms725417(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

## <a name="geterrorinfo"></a> Cdberrorınfo::geterrorınfo

Çağrıları [IErrorRecords::GetErrorInfo](/previous-versions/windows/desktop/ms711230(v=vs.85)) döndürülecek bir [IErrorInfo](/previous-versions/windows/desktop/ms718112(v=vs.85)) belirtilen kayıt arabirim işaretçisi.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetErrorInfo(ULONG ulRecordNum,
   LCID lcid,IErrorInfo** ppErrorInfo) const throw();
```

#### <a name="parameters"></a>Parametreler

Bkz: [IErrorRecords::GetErrorInfo](/previous-versions/windows/desktop/ms711230(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

## <a name="geterrorparameters"></a> Cdberrorınfo::geterrorparameters

Çağrıları [IErrorRecords::GetErrorParameters](/previous-versions/windows/desktop/ms715793(v=vs.85)) hata parametreleri dönün.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetErrorParameters(ULONG ulRecordNum,
   DISPPARAMS* pdispparams) const throw();
```

#### <a name="parameters"></a>Parametreler

Bkz: [IErrorRecords::GetErrorParameters](/previous-versions/windows/desktop/ms715793(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

## <a name="geterrorrecords"></a> Cdberrorınfo::geterrorrecords

Belirtilen nesne için hata kayıtları alır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetErrorRecords(IUnknown* pUnk,
   const IID& iid,
   ULONG* pcRecords) throw();

HRESULT GetErrorRecords(ULONG* pcRecords) throw();
```

#### <a name="parameters"></a>Parametreler

*pUnk*<br/>
[in] Hata kaydı alınacağı nesne için arabirim.

*IID*<br/>
[in] IID hatayla ilişkili arabirimi.

*pcRecords*<br/>
[out] Hata Kayıt (bir tabanlı) sayısı için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Hata bilgileri almak için hangi arabirim kontrol etmek istediğiniz işlevin ilk formu kullanın. Aksi takdirde, ikinci formu kullanın.

## <a name="see-also"></a>Ayrıca Bkz.

[DBViewer](../../overview/visual-cpp-samples.md)<br/>
[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)