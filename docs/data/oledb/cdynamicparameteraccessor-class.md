---
title: CDynamicParameterAccessor sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 02/14/2018
ms.technology:
- cpp-data
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d0db07c8419db53d30612e6edbbe134634e37a74
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/11/2018
ms.locfileid: "49083950"
---
# <a name="cdynamicparameteraccessor-class"></a>CDynamicParameterAccessor Sınıfı

Benzer şekilde [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) çağırarak ayarlamak için parametre bilgilerini alır, ancak [ICommandWithParameters](/sql/relational-databases/native-client-ole-db-interfaces/icommandwithparameters) arabirimi.

## <a name="syntax"></a>Sözdizimi

```cpp
class CDynamicParameterAccessor : public CDynamicAccessor
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: atldbcli.h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[CDynamicParameterAccessor](#cdynamicparameteraccessor)|Oluşturucu.|
|[GetParam](#getparam)|Parametre verisi arabellekteki alır.|
|[GetParamCount](#getparamcount)|Erişimci parametrelerinde sayısını alır.|
|[GetParamIO](#getparamio)|Belirtilen parametre bir giriş veya çıkış parametresi olup olmadığını belirler.|
|[GetParamLength](#getparamlength)|Arabellekteki depolanan belirtilen parametre uzunluğunu alır.|
|[GetParamName](#getparamname)|Belirtilen parametre adını alır.|
|[GetParamStatus](#getparamstatus)|Arabellekteki depolanan belirtilen parametreyi alır.|
|[GetParamString](#getparamstring)|Arabellekteki depolanan belirtilen parametresinin dize verilerini alır.|
|[GetParamType](#getparamtype)|Belirtilen bir parametrenin veri türünü alır.|
|[SetParam](#setparam)|Parametre verisi kullanarak ara ayarlar.|
|[SetParamLength](#setparamlength)|Arabellekteki depolanan belirtilen parametre uzunluğunu ayarlar.|
|[SetParamStatus](#setparamstatus)|Arabellekteki depolanan belirtilen parametre durumunu ayarlar.|
|[SetParamString](#setparamstring)|Arabellekteki depolanan belirtilen parametresinin dize verilerini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Sağlayıcı desteklemelidir `ICommandWithParameters` tüketici Bu sınıf kullanmak için.

Parametre bilgileri oluşturulur ve bu sınıf tarafından yönetilen bir arabellek depolanır. Parametre verisi arabellekteki kullanarak elde [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) ve [GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md).

Bu sınıf bir SQL Server saklı yordamı yürütme ve çıkış parametresi değerleri almak için nasıl kullanılacağını gösteren bir örnek için bkz: [DynamicConsumer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer) örnek kodda [Microsoft VCSamples](https://github.com/Microsoft/VCSamples) github deposu.

## <a name="cdynamicparameteraccessor"></a> CDynamicParameterAccessor::CDynamicParameterAccessor

Oluşturucu.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
typedef CDynamicParameterAccessor _ParamClass;  
CDynamicParameterAccessor(DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,   
   DBLENGTH nBlobSize = 8000 )   
   : CDynamicAccessor(eBlobHandling, nBlobSize )  
```  
  
#### <a name="parameters"></a>Parametreler  

*eBlobHandling*<br/>
Nasıl ele alınması için BLOB verilerini olduğunu belirtir. DBBLOBHANDLING_DEFAULT varsayılan değerdir. Bkz: [CDynamicAccessor::SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md) DBBLOBHANDLINGENUM değerlerin bir açıklaması.  
  
*nBlobSize*<br/>
Bayt cinsinden en yüksek BLOB boyutu; sütun verileri bu değer üzerinde bir BLOB kabul edilir. 8000 varsayılan değerdir. Bkz: [CDynamicAccessor::SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md) Ayrıntılar için.  
  
### <a name="remarks"></a>Açıklamalar  

Bkz: [CDynamicAccessor::CDynamicAccessor](../../data/oledb/cdynamicaccessor-cdynamicaccessor.md) BLOB işleme hakkında daha fazla bilgi için oluşturucu. 

## <a name="getparam"></a> CDynamicParameterAccessor::GetParam

Belirtilen parametre dize olmayan verileri parametresi arabelleğinden alır.  
  
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
Veri türü şablonlu bir parametre.  
  
*nParam*<br/>
[in] Parametre sayısı (1 uzaklık). Parametre 0 dönüş değerleri için ayrılmıştır. Parametre numarası SQL veya saklı yordam çağrısı, bir sırada temel parametresi dizinidir. Bkz: [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) örneği.  
  
*pParamName*<br/>
[in] Parametre adı.  
  
*pData*<br/>
[out] Arabellekteki alınan verileri içeren bellek işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  

Şablonu oluşturulmamış sürümleri için verileri içeren bellek noktalarına arabellekteki alınır. Şablonlu sürümleri için döndürür **true** başarı veya **false** başarısız.  
  
Kullanım `GetParam` arabellekteki dize olmayan parametre verisi almak için. Kullanım [GetParamString](../../data/oledb/cdynamicparameteraccessor-getparamstring.md) arabellekteki dizesi parametre verilerini almak için.  

## <a name="getparamcount"></a> CDynamicParameterAccessor::GetParamCount

Arabellekteki depolanan parametre sayısını alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
DB_UPARAMS GetParamCount() const throw();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  

Parametre sayısı.  

## <a name="getparamio"></a> CDynamicParameterAccessor::getparamıo

Belirtilen parametre bir giriş veya çıkış parametresi olup olmadığını belirler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
bool GetParamIO(DBORDINAL nParam,   
   DBPARAMIO* pParamIO) const throw();  
```  
  
#### <a name="parameters"></a>Parametreler  

*nParam*<br/>
[in] Parametre sayısı (1 uzaklık). Parametre 0 dönüş değerleri için ayrılmıştır. Parametre numarası SQL veya saklı yordam çağrısı, bir sırada temel parametresi dizinidir. Bkz: [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) örneği.  
  
*pParamIO*<br/>
Bir işaretçi içeren değişken `DBPARAMIO` belirtilen parametre türü (giriş veya çıkış). Şu şekilde tanımlanır:  
  
```cpp  
typedef DWORD DBPARAMIO;  
  
enum DBPARAMIOENUM {  
    DBPARAMIO_NOTPARAM   = 0,  
    DBPARAMIO_INPUT      = 0x1,  
    DBPARAMIO_OUTPUT     = 0x2  
};  
```  
  
### <a name="return-value"></a>Dönüş Değeri  

Döndürür **true** başarı veya **false** başarısız.  

## <a name="getparamlength"></a> CDynamicParameterAccessor::GetParamLength

Arabellekteki depolanan belirtilen parametre uzunluğunu alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
bool GetParamLength(DBORDINAL nParam,  
   DBLENGTH* pLength);  

DBLENGTH* GetParamLength(DBORDINAL nParam) const throw();  
```  
  
#### <a name="parameters"></a>Parametreler  

*nParam*<br/>
[in] Parametre sayısı (1 uzaklık). Parametre 0 dönüş değerleri için ayrılmıştır. Parametre numarası SQL veya saklı yordam çağrısı, bir sırada temel parametresi dizinidir. Bkz: [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) örneği.  
  
*pLength*<br/>
[out] Belirtilen parametre bayt cinsinden uzunluğunu içeren bir değişken için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  

İlk geçersiz kılma döndürür **true** başarı veya **false** başarısız. İkinci parametresinin uzunluğu içeren bellek noktalarına geçersiz kılar. 

## <a name="getparamname"></a> CDynamicParameterAccessor::GetParamName

Belirtilen parametre adını alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
LPOLESTR GetParamName(DBORDINAL nParam) const throw();  
```  
  
#### <a name="parameters"></a>Parametreler  

*nParam*<br/>
[in] Parametre sayısı (1 uzaklık). Parametre 0 dönüş değerleri için ayrılmıştır. Parametre numarası SQL veya saklı yordam çağrısı, bir sırada temel parametresi dizinidir. Bkz: [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) örneği.  
  
### <a name="return-value"></a>Dönüş Değeri  

Belirtilen parametre adı.  

## <a name="getparamstatus"></a> CDynamicParameterAccessor::GetParamStatus

Arabellekteki depolanan belirtilen parametreyi alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
bool GetParamStatus(DBORDINAL nParam,  
   DBSTATUS* pStatus);  

DBSTATUS* GetParamStatus(DBORDINAL nParam) const throw();  
```  
  
#### <a name="parameters"></a>Parametreler  

*nParam*<br/>
[in] Parametre sayısı (1 uzaklık). Parametre 0 dönüş değerleri için ayrılmıştır. Parametre numarası SQL veya saklı yordam çağrısı, bir sırada temel parametresi dizinidir. Bkz: [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) örneği.  
  
*pStatus*<br/>
[out] Belirtilen parametre DBSTATUS durumunu içeren bir değişken için bir işaretçi. DBSTATUS değerler hakkında daha fazla bilgi için bkz. [durumu](/previous-versions/windows/desktop/ms722617) içinde *OLE DB Programcının Başvurusu*, ya da araması DBSTATUS için biçim.  
  
### <a name="remarks"></a>Açıklamalar  

İlk geçersiz kılma döndürür **true** başarı veya **false** başarısız. İkinci belirtilen parametre durumunu içeren bellek noktalarına geçersiz kılar.

## <a name="getparamstring"></a> CDynamicParameterAccessor::GetParamString

Arabellekteki depolanan belirtilen parametresinin dize verilerini alır.  
  
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
[in] Parametre sayısı (1 uzaklık). Parametre 0 dönüş değerleri için ayrılmıştır. Parametre numarası SQL veya saklı yordam çağrısı, bir sırada temel parametresi dizinidir. Bkz: [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) örneği.  
  
*strOutput*<br/>
[out] ANSI (`CSimpleStringA`) veya Unicode (`CSimpleStringW`) dize verilerini belirtilen parametre. Türünde bir parametre geçmelidir `CString`, örneğin:  
  
[!code-cpp[NVC_OLEDB_Consumer#9](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-getparamstring_1.cpp)]  
  
*pBuffer*<br/>
[out] ANSI işaretçisi (**CHAR**) veya Unicode (**WCHAR**) dize verilerini belirtilen parametre.  
  
*pMaxLen*<br/>
[out] Arabellek boyutu için bir işaretçi tarafından işaret edilen *pBuffer* (Sonlandırıcı NULL karakter dahil).  
  
### <a name="remarks"></a>Açıklamalar  

Döndürür **true** başarı veya **false** başarısız.  
  
Varsa *pBuffer* NULL ise bu yöntem tarafından işaret edilen bellek gerekli arabellek boyutunu ayarlayacak *pMaxLen* ve dönüş **true** veri kopyalama olmadan.  
  
Bu yöntem başarısız olur arabellek *pBuffer* tüm dizeyi içeren yeteri kadar büyük değil.  
  
Kullanım `GetParamString` arabellekteki dizesi parametre verilerini almak için. Kullanım [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) arabellekteki dize olmayan parametre verisi almak için.  

## <a name="getparamtype"></a> CDynamicParameterAccessor::GetParamType

Belirtilen bir parametrenin veri türünü alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
bool GetParamType(DBORDINAL nParam,  
   DBTYPE* pType) const throw();  
```  
  
#### <a name="parameters"></a>Parametreler  

*nParam*<br/>
[in] Parametre sayısı (1 uzaklık). Parametre 0 dönüş değerleri için ayrılmıştır. Parametre numarası SQL veya saklı yordam çağrısı, bir sırada temel parametresi dizinidir. Bkz: [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) örneği.  
  
*pType*<br/>
[out] Belirtilen parametre veri türü içeren bir değişken için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  

Döndürür **true** başarı veya **false** başarısız.  

## <a name="setparam"></a> CDynamicParameterAccessor::SetParam

Belirtilen (dize olmayan) verileri kullanarak parametre arabelleği ayarlar.  
  
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
Veri türü şablonlu bir parametre.  
  
*nParam*<br/>
[in] Parametre sayısı (1 uzaklık). Parametre 0 dönüş değerleri için ayrılmıştır. Parametre numarası SQL veya saklı yordam çağrısı, bir sırada temel parametresi dizinidir. Örneğin:  
  
[!code-cpp[NVC_OLEDB_Consumer#8](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-setparam_1.cpp)]  
  
*pParamName*<br/>
[in] Parametre adı.  
  
*pData*<br/>
[in] Arabelleğe yazılacak veriler içeren bellek işaretçisi.  
  
*Durumu*<br/>
[in] DBSTATUS sütun durumu. DBSTATUS değerler hakkında daha fazla bilgi için bkz. [durumu](/previous-versions/windows/desktop/ms722617) içinde *OLE DB Programcının Başvurusu*, ya da araması DBSTATUS için biçim.  
  
### <a name="return-value"></a>Dönüş Değeri  

Döndürür **true** başarı veya **false** başarısız.  
  
Kullanım `SetParam` arabellekteki dize olmayan parametre verisini ayarlayın. Kullanım [SetParamString](../../data/oledb/cdynamicparameteraccessor-setparamstring.md) dizesi parametre verilerini arabelleğe ayarlamak için.  

## <a name="setparamlength"></a> CDynamicParameterAccessor::SetParamLength

Arabellekteki depolanan belirtilen parametre uzunluğunu ayarlar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
bool SetParamLength(DBORDINAL nParam,  
   DBLENGTH length);  
```  
  
#### <a name="parameters"></a>Parametreler  

*nParam*<br/>
[in] Parametre sayısı (1 uzaklık). Parametre 0 dönüş değerleri için ayrılmıştır. Parametre numarası SQL veya saklı yordam çağrısı, bir sırada temel parametresi dizinidir. Bkz: [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) örneği.  
  
*Uzunluğu*<br/>
[in] Belirtilen parametre bayt cinsinden uzunluğu.  
  
### <a name="remarks"></a>Açıklamalar  

Döndürür **true** başarı veya **false** başarısız. 

## <a name="setparamstatus"></a> CDynamicParameterAccessor::SetParamStatus

Arabellekteki depolanan belirtilen parametre durumunu ayarlar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
bool SetParamStatus(DBORDINAL nParam,  
   DBSTATUS status);  
```  
  
#### <a name="parameters"></a>Parametreler  

*nParam*<br/>
[in] Parametre sayısı (1 uzaklık). Parametre 0 dönüş değerleri için ayrılmıştır. Parametre numarası SQL veya saklı yordam çağrısı, bir sırada temel parametresi dizinidir. Bkz: [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) örneği.  
  
*Durumu*<br/>
[in] Belirtilen parametre DBSTATUS durumu. DBSTATUS değerler hakkında daha fazla bilgi için bkz. [durumu](/previous-versions/windows/desktop/ms722617) içinde *OLE DB Programcının Başvurusu*, ya da araması DBSTATUS için biçim.  
  
### <a name="remarks"></a>Açıklamalar  

Döndürür **true** başarı veya **false** başarısız. 

## <a name="setparamstring"></a> CDynamicParameterAccessor::SetParamString

Arabellekteki depolanan belirtilen parametresinin dize verilerini ayarlar.  
  
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
[in] Parametre sayısı (1 uzaklık). Parametre 0 dönüş değerleri için ayrılmıştır. Parametre numarası SQL veya saklı yordam çağrısı, bir sırada temel parametresi dizinidir. Bkz: [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) örneği.  
  
*pString*<br/>
[in] ANSI işaretçisi (**CHAR**) veya Unicode (**WCHAR**) dize verilerini belirtilen parametre. DBSTATUS içinde biçim bakın.  
  
*Durumu*<br/>
[in] Belirtilen parametre DBSTATUS durumu. DBSTATUS değerler hakkında daha fazla bilgi için bkz. [durumu](/previous-versions/windows/desktop/ms722617) içinde *OLE DB Programcının Başvurusu*, ya da araması DBSTATUS için biçim.  
  
### <a name="remarks"></a>Açıklamalar  

Döndürür **true** başarı veya **false** başarısız.  
  
`SetParamString` Belirtilen en yüksek boyuttan daha büyük bir dize ayarlamaya çalışırsanız başarısız olur *pString*.  
  
Kullanım `SetParamString` dizesi parametre verilerini arabelleğe ayarlamak için. Kullanım [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) arabellekteki dize olmayan parametre verisini ayarlayın. 

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor Sınıfı](../../data/oledb/caccessor-class.md)<br/>
[CDynamicAccessor Sınıfı](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CManualAccessor Sınıfı](../../data/oledb/cmanualaccessor-class.md)  