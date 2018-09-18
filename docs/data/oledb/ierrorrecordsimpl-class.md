---
title: Ierrorrecordsımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
- GetCustomErrorObject
- GetErrorInfo
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 13e00d3d5ac7cb6cf6e4078ee24a7c3b02a2778e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043397"
---
# <a name="ierrorrecordsimpl-class"></a>IErrorRecordsImpl Sınıfı

OLE DB uygulayan [IErrorRecords](/previous-versions/windows/desktop/ms718112\(v=vs.85\)) kayıtları ekleme ve veri üyesi kayıtlar alınırken arabirimi ([m_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)) türü **CAtlArray <** `RecordClass`**>**.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class RecordClass = ATLERRORINFO>  
class IErrorRecordsImpl : public IErrorRecords  
```  
  
### <a name="parameters"></a>Parametreler  

*T*<br/>
Öğesinden türetilen bir sınıf `IErrorRecordsImpl`.  
  
*RecordClass*<br/>
OLE DB hatası nesneyi temsil eden sınıf.  

## <a name="requirements"></a>Gereksinimler  

**Başlık:** atldb.h  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[GetErrorDescriptionString](#geterrordescriptionstring)|Hata açıklaması dizesi bir hatayla kayıttan alır.|  
|[Geterrorguıd](#geterrorguid)|' % S'hata GUID bir hatayla kayıttan alır.|  
|[GetErrorHelpContext](#geterrorhelpcontext)|Yardım içeriği kimliği bir hatayla kayıttan alır.|  
|[GetErrorHelpFile](#geterrorhelpfile)|Bir hatayla kayıttan Yardım dosyasının tam yol adını alır.|  
|[GetErrorSource](#geterrorsource)|Kaynak kodu bir hatayla kayıttan alır.|  
  
### <a name="interface-methods"></a>Arabirim yöntemleri  
  
|||  
|-|-|  
|[AddErrorRecord](#adderrorrecord)|OLE DB hatası nesnesine bir kayıt ekler.|  
|[GetBasicErrorInfo](#getbasicerrorinfo)|Dönüş kodu ve sağlayıcıya özgü hata numarası gibi bir hata ile ilgili temel bilgileri döndürür.|  
|[GetCustomErrorObject](#getcustomerrorobject)|Bir işaretçi, bir özel hata nesnesi üzerinde bir arabirim döndürür.|  
|[GetErrorInfo](#geterrorinfo)|Döndürür bir [IErrorInfo](/previous-versions/windows/desktop/ms718112\(v=vs.85\)) belirtilen kayıt arabirim işaretçisi.|  
|[GetErrorParameters](#geterrorparameters)|Hata parametrelerini döndürür.|  
|[GetRecordCount](#getrecordcount)|OLE DB kayıt nesnesinde kayıt sayısını döndürür.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|[m_rgErrors](#rgerrors)|Hata kayıt dizisi.|  

## <a name="geterrordescriptionstring"></a> Ierrorrecordsımpl::geterrordescriptionstring

Hata açıklaması dizesi bir hatayla kayıttan alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
LPOLESTR GetErrorDescriptionString(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>Parametreler  

*rCurError*<br/>
Bir `ERRORINFO` kaydında bir `IErrorInfo` arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  

Hatayı açıklayan bir dize işaretçisi.  
  
## <a name="geterrorguid"></a> Ierrorrecordsımpl::geterrorguıd

' % S'hata GUID bir hatayla kayıttan alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
REFGUID GetErrorGUID(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>Parametreler  

*rCurError*<br/>
Bir `ERRORINFO` kaydında bir `IErrorInfo` arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  

Bir GUID hatası için bir başvuru.  

## <a name="geterrorhelpcontext"></a> Ierrorrecordsımpl::geterrorhelpcontext

Yardım içeriği kimliği bir hatayla kayıttan alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
DWORD GetErrorHelpContext(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>Parametreler  

*rCurError*<br/>
Bir `ERRORINFO` kaydında bir `IErrorInfo` arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  

Hata için Yardım içeriği kimliği.  

## <a name="geterrorhelpfile"></a> Ierrorrecordsımpl::geterrorhelpfile

Yardım dosyasının yol adı bir hatayla kayıttan alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
LPOLESTR GetErrorHelpFile(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>Parametreler  

*rCurError*<br/>
Bir `ERRORINFO` kaydında bir `IErrorInfo` arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  

Hata için Yardım dosyasına yol adını içeren bir dize işaretçisi.

## <a name="geterrorsource"></a> Ierrorrecordsımpl::geterrorsource

Bir hatayla kayıttan hataya neden olan kaynak kodunu alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
LPOLESTR GetErrorSource(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>Parametreler  

*rCurError*<br/>
Bir `ERRORINFO` kaydında bir `IErrorInfo` arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  

Hatanın kaynak kodunu içeren bir dize işaretçisi. 

## <a name="adderrorrecord"></a> Ierrorrecordsımpl::adderrorrecord

OLE DB hatası nesnesine bir kayıt ekler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
STDMETHOD(AddErrorRecord )(ERRORINFO *pErrorInfo,  
   DWORD dwLookupID,  
   DISPPARAMS *pdispparams,  
   IUnknown *punkCustomError,  
   DWORD dwDynamicErrorID);  
```  
  
#### <a name="parameters"></a>Parametreler  

Bkz: [IErrorRecords::AddErrorRecord](/previous-versions/windows/desktop/ms725362\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*.  

## <a name="getbasicerrorinfo"></a> Ierrorrecordsımpl::getbasicerrorınfo

Dönüş kodu ve sağlayıcıya özgü hata numarası gibi bir hata ile ilgili temel bilgileri döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
STDMETHOD(GetBasicErrorInfo )(ULONG ulRecordNum,  
   ERRORINFO *pErrorInfo);  
```  
  
#### <a name="parameters"></a>Parametreler  

Bkz: [IErrorRecords::GetBasicErrorInfo](/previous-versions/windows/desktop/ms723907\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*. 

## <a name="getcustomerrorobject"></a> Ierrorrecordsımpl::getcustomerrorobject

Bir işaretçi, bir özel hata nesnesi üzerinde bir arabirim döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
STDMETHOD(GetCustomErrorObject )(ULONG ulRecordNum,  
   REFIID riid,  
   IUnknown **ppObject);  
```  
  
#### <a name="parameters"></a>Parametreler  

Bkz: [IErrorRecords::GetCustomErrorObject](/previous-versions/windows/desktop/ms725417\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*.  

## <a name="geterrorinfo"></a> Ierrorrecordsımpl::geterrorınfo

Döndürür bir [IErrorInfo](/previous-versions/windows/desktop/ms718112\(v=vs.85\)) belirtilen kayıt arabirim işaretçisi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
STDMETHOD(GetErrorInfo )(ULONG ulRecordNum,  
   LCID lcid,  
   IErrorInfo **ppErrorInfo);  
```  
  
#### <a name="parameters"></a>Parametreler  

Bkz: [IErrorRecords::GetErrorInfo](/previous-versions/windows/desktop/ms711230\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*.

## <a name="geterrorparameters"></a> Ierrorrecordsımpl::geterrorparameters

Hata parametrelerini döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
STDMETHOD(GetErrorParameters )(ULONG ulRecordNum,  
   DISPPARAMS *pdispparams);  
```  
  
#### <a name="parameters"></a>Parametreler  

Bkz: [IErrorRecords::GetErrorParameters](/previous-versions/windows/desktop/ms715793\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*.  

## <a name="getrecordcount"></a> Ierrorrecordsımpl::getrecordcount

OLE DB kayıt nesnesinde kayıt sayısını döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
STDMETHOD(GetRecordCount )(ULONG *pcRecords);  
```  
  
#### <a name="parameters"></a>Parametreler  

Bkz: [IErrorRecords::GetRecordCount](/previous-versions/windows/desktop/ms722724\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*.  

## <a name="rgerrors"></a> Ierrorrecordsımpl::m_rgerrors

Hata kayıt dizisi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
CAtlArray< RecordClass > m_rgErrors;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)