---
title: CDataSource Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL.CDataSource
- ATL::CDataSource
- CDataSource
- ATL::CDataSource::Close
- ATL.CDataSource.Close
- CDataSource::Close
- CDataSource.Close
- ATL::CDataSource::GetInitializationString
- CDataSource.GetInitializationString
- GetInitializationString
- CDataSource::GetInitializationString
- ATL.CDataSource.GetInitializationString
- CDataSource::GetProperties
- ATL.CDataSource.GetProperties
- CDataSource.GetProperties
- ATL::CDataSource::GetProperties
- GetProperties
- ATL::CDataSource::GetProperty
- ATL.CDataSource.GetProperty
- CDataSource.GetProperty
- CDataSource::GetProperty
- ATL::CDataSource::Open
- ATL.CDataSource.Open
- CDataSource::Open
- CDataSource.Open
- CDataSource::OpenFromFileName
- ATL::CDataSource::OpenFromFileName
- OpenFromFileName
- CDataSource.OpenFromFileName
- ATL.CDataSource.OpenFromFileName
- CDataSource.OpenFromInitializationString
- OpenFromInitializationString
- CDataSource::OpenFromInitializationString
- ATL::CDataSource::OpenFromInitializationString
- ATL.CDataSource.OpenFromInitializationString
- CDataSource.OpenWithPromptFileName
- OpenWithPromptFileName
- ATL::CDataSource::OpenWithPromptFileName
- ATL.CDataSource.OpenWithPromptFileName
- CDataSource::OpenWithPromptFileName
- CDataSource::OpenWithServiceComponents
- OpenWithServiceComponents
- CDataSource.OpenWithServiceComponents
helpviewer_keywords:
- CDataSource class
- Close method
- GetInitializationString method
- GetProperties method
- GetProperty method
- Open method
- OpenFromFileName method
- OpenFromInitializationString method
- OpenWithPromptFileName method
- OpenWithServiceComponents method
ms.assetid: 99bf862c-9d5c-4117-9501-aa0e2672085c
ms.openlocfilehash: 2564d4d9b0a2e5df1f575d6f2627ce80f48533c1
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59021923"
---
# <a name="cdatasource-class"></a>CDataSource Sınıfı

Bir veri kaynağına bağlantı sağlayıcısı üzerinden temsil eden bir OLE DB veri kaynağı nesnesi karşılık gelir.

## <a name="syntax"></a>Sözdizimi

```cpp
class CDataSource
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldbcli.h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Kapat](#close)|Bağlantıyı kapatır.|
|[Getınitializationstring](#getinitializationstring)|Şu anda açık olan veri kaynağının başlatma dizesi alır.|
|[GetProperties](#getproperties)|Bağlı veri kaynağı için ayarlanmış özelliklerin değerlerini alır.|
|[GetProperty](#getproperty)|Bağlı veri kaynağı için ayarlanmış tek bir özelliğin değerini alır.|
|[açın](#open)|Bir sağlayıcı (veri kaynağı) kullanarak bir bağlantı oluşturur bir `CLSID`, `ProgID`, veya bir `CEnumerator` çağıran tarafından sağlanan bir bilinen ad.|
|[OpenFromFileName](#openfromfilename)|Bir veri kaynağı, kullanıcı tarafından sağlanan dosya adıyla belirtilen bir dosya açar.|
|[OpenFromInitializationString](#openfrominitializationstring)|Bir başlatma dizesi tarafından belirtilen veri kaynağı açılır.|
|[OpenWithPromptFileName](#openwithpromptfilename)|İlgili veri kaynağını açmak için bir önceden oluşturulmuş bir veri bağlantısı dosyasını seçmesini sağlar.|
|[OpenWithServiceComponents](#openwithservicecomponents)|Veri Bağlantısı iletişim kutusunu kullanarak bir veri kaynağı nesnesi açılır.|

## <a name="remarks"></a>Açıklamalar

Bir veya daha fazla veritabanı oturumları için tek bir bağlantı oluşturabilirsiniz. Bu oturumlar tarafından temsil edilen `CSession`. Çağırmalısınız [CDataSource::Open](../../data/oledb/cdatasource-open.md) bir oturumla oluşturmadan önce bağlantıyı açmak için `CSession::Open`.

Nasıl kullanılacağına ilişkin bir örnek `CDataSource`, bkz: [CatDB](../../overview/visual-cpp-samples.md) örnek.

## <a name="close"></a> CDataSource::Close

Serbest bırakarak bağlantıyı kapatır `m_spInit` işaretçi.

### <a name="syntax"></a>Sözdizimi

```cpp
void Close() throw();
```

## <a name="getinitializationstring"></a> CDataSource::getınitializationstring

Şu anda açık olan bir veri kaynağının başlatma dizesi alır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetInitializationString(BSTR* pInitializationString,
   bool bIncludePassword = false) throw();
```

#### <a name="parameters"></a>Parametreler

*pInitializationString*<br/>
[out] Başlatma dizesi için bir işaretçi.

*bIncludePassword*<br/>
[in] **true** parola; dize içeriyorsa, aksi takdirde **false**.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Daha sonra bu veri kaynağı bağlantısı yeniden elde edilen başlatma dizesi kullanılabilir.

## <a name="getproperties"></a> CDataSource::GetProperties

Bağlı veri kaynağı nesnesi için istenen özellik bilgileri döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetProperties(ULONG ulPropIDSets,
   constDBPROPIDSET* pPropIDSet,
   ULONG* pulPropertySets,
   DBPROPSET** ppPropsets) const throw();
```

#### <a name="parameters"></a>Parametreler

Bkz: [IDBProperties::GetProperties](/previous-versions/windows/desktop/ms714344(v=vs.85)) içinde *OLE DB Programcının Başvurusu* Windows SDK içinde.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Tek bir özellik almak için kullanın [GetProperty](../../data/oledb/cdatasource-getproperty.md).

## <a name="getproperty"></a> CDataSource::GetProperty

Bağlı veri kaynağı nesnesinin Belirtilen bir özelliğinin değerini döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetProperty(const GUID& guid,
   DBPROPID propid,
   VARIANT* pVariant) const throw();
```

#### <a name="parameters"></a>Parametreler

*GUID*<br/>
[in] Hangi özelliği döndürmek özelliği tanımlayan bir GUID.

*PROPID*<br/>
[in] Döndürülecek bir özellik için özellik kimliği.

*pVariant*<br/>
[out] Değişken için bir işaretçi burada `GetProperty` özelliğinin değerini döndürür.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Birden çok özellik almak için kullanın [GetProperties](../../data/oledb/cdatasource-getproperties.md).

## <a name="open"></a> CDataSource::Open

Kullanarak bir veri kaynağı için bir bağlantı açar bir `CLSID`, `ProgID`, veya `CEnumerator` bilinen ad veya bir Bulucu iletişim kutusu ile kullanıcıya sorar.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT Open(const CLSID& clsid,
   DBPROPSET* pPropSet = NULL,
   ULONG nPropertySets = 1) throw();

HRESULT Open(const CLSID& clsid,
   LPCTSTR pName,
   LPCTSTR pUserName = NULL,
   LPCTSTR pPassword = NULL,
   long nInitMode = 0) throw();HRESULT Open(LPCTSTR szProgID,
   DBPROPSET* pPropSet = NULL,
   ULONG nPropertySets = 1) throw();HRESULT Open(LPCTSTR szProgID,
   LPCTSTR pName,  LPCTSTR pUserName = NULL,
   LPCTSTR pPassword = NULL,
   long nInitMode = 0) throw();

HRESULT Open(const CEnumerator& enumerator,
   DBPROPSET* pPropSet = NULL,
   ULONG nPropertySets = 1) throw();

HRESULT Open(const CEnumerator& enumerator,
   LPCTSTR pName,
   LPCTSTR pUserName = NULL,
   LPCTSTR pPassword = NULL,
   long nInitMode = 0) throw();

HRESULT Open(HWND hWnd = GetActiveWindow(),
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_WIZARDSHEET) throw();

HRESULT Open(LPCWSTR szProgID,
   DBPROPSET* pPropSet = NULL,
   ULONG nPropertySets = 1) throw();

HRESULT Open(LPCSTR szProgID,
   LPCTSTR pName,LPCTSTR pUserName = NULL,
   LPCTSTR pPassword = NULL,
   long nInitMode = 0) throw();
```

#### <a name="parameters"></a>Parametreler

*CLSID*<br/>
[in] `CLSID` Veri sağlayıcısı.

*pPropSet*<br/>
[in] Bir dizi işaretçi [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) özelliklerini ve değerlerini ayarlamak için içeren yapılar. Bkz: [özellik kümeleri ve özellik gruplarını](/previous-versions/windows/desktop/ms713696(v=vs.85)) içinde *OLE DB Programcının Başvurusu* Windows SDK içinde.

*nPropertySets*<br/>
[in] Sayısını [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) yapıları geçirilen *pPropSet* bağımsız değişken.

*Sağlayıcı adı*<br/>
[in] Bağlanılacak veritabanının adı.

*pUserName*<br/>
[in] Kullanıcı adı.

*pPassword*<br/>
[in] Kullanıcının parolası.

*nInitMode*<br/>
[in] Veritabanı başlatma modu. Bkz: [başlatma özellikleri](/previous-versions/windows/desktop/ms723127(v=vs.85))içinde *OLE DB Programcının Başvurusu* geçerli başlatma modlarının bir listesi için Windows SDK. Varsa *nInitMode* sıfır, hiçbir başlatma işlemi modu bağlantıyı açmak için kullanılan özellik kümesine eklenir.

*szProgID*<br/>
[in] Bir program tanımlayıcısı.

*Numaralandırıcı*<br/>
[in] A [CEnumerator](../../data/oledb/cenumerator-class.md) nesne arayan belirtmediği zaman bağlantı açmak için bir ad sağlamak için kullanılan bir `CLSID`.

*hWnd*<br/>
[in] İletişim kutusunun üst olacak penceresine işleyin. Kullanan işlev aşırı yüklemesi kullanarak *hWnd* parametre otomatik olarak hizmet bileşenleri çağırma; Ayrıntılar için açıklamalara bakın.

*dwPromptOptions*<br/>
[in] Bulucu iletişim kutusunda görüntülenecek stilini belirler. Msdasc.h olası değerler için bkz.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Kullanan yöntemi aşırı yüklemesini *hWnd* parametresi oledb32.dll hizmet bileşenleri içeren bir veri kaynağı nesnesi açılır; bu DLL'yi kaynak havuzu, otomatik gibi hizmet bileşenleri özellikleri uygulamasını içerir. İşlem kaydı ve benzeri. Daha fazla bilgi için bkz: "OLE DB hizmetleri" OLE DB Programcı Başvurusu, [ https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true ](https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).

Yöntemi aşırı kullanmayın *hWnd* parametresi bir veri kaynağı nesnesi içinde oledb32.dll hizmet bileşenleri kullanmadan açın. A [CDataSource](../../data/oledb/cdatasource-class.md) nesne bu işlev aşırı yüklemelerinin ile açılmış hizmet bileşenleri işlevlerden herhangi birini kullanmak mümkün olacaktır.

### <a name="example"></a>Örnek

Aşağıdaki kod, Jet 4.0 veri kaynağına OLE DB Şablonları ile açmak gösterilmektedir. Jet veri kaynağı bir OLE DB veri kaynağı olarak kabul edin. Ancak, çağrınız `Open` iki özellik kümeleri gerekir: bir DBPROPSET_DBINIT diğeri DBPROPSET_JETOLEDB_DBINIT, DBPROP_JETOLEDB_DATABASEPASSWORD ayarlayabilirsiniz.

[!code-cpp[NVC_OLEDB_Consumer#7](../../data/oledb/codesnippet/cpp/cdatasource-open_1.cpp)]

## <a name="openfromfilename"></a> CDataSource::OpenFromFileName

Bir veri kaynağı, kullanıcı tarafından sağlanan dosya adıyla belirtilen bir dosya açar.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT OpenFromFileName(LPCOLESTR szFileName) throw();
```

#### <a name="parameters"></a>Parametreler

*szFileName*<br/>
[in] Bir dosya, genellikle bir veri kaynağı bağlantısı adı (. UDL) dosyası.

Veri bağlantısı dosyalarını (UDL dosyaları) hakkında daha fazla bilgi için bkz: [veri bağlantısı API'sine genel bakış](/previous-versions/windows/desktop/ms718102(v=vs.85)) Windows SDK.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu yöntem oledb32.dll hizmet bileşenlerini kullanarak bir veri kaynağı nesnesi açılır; Bu DLL, kaynak havuzu, otomatik bir işlem kaydı ve benzeri gibi hizmet bileşenleri özellikleri uygulamasını içerir. Daha fazla bilgi için bkz: "OLE DB hizmetleri" OLE DB Programcı Başvurusu, [ https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true ](https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).

## <a name="openfrominitializationstring"></a> CDataSource::OpenFromInitializationString

Kullanıcı tarafından sağlanan başlatma dizesi tarafından belirtilen bir veri kaynağı açılır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT OpenFromInitializationString(LPCOLESTR szInitializationString,
   bool fPromptForInfo= false) throw();
```

#### <a name="parameters"></a>Parametreler

*szInitializationString*<br/>
[in] Başlatma dizesi.

*fPromptForInfo*<br/>
[in] Bu bağımsız değişken ayarlanmışsa **true**, ardından `OpenFromInitializationString` yalnızca daha fazla bilgi gerekirse kullanıcıya sorulması belirtir DBPROMPT_COMPLETEREQUIRED DBPROP_INIT_PROMPT özelliğini ayarlar. Başlatma dizesi parola gerektiren bir veritabanı belirten durumlarda kullanışlıdır ancak dize parola içermiyor. Kullanıcıdan bir parola (veya diğer eksik bilgileri) istenecektir veritabanına bağlanmaya çalışırken.

Varsayılan değer **false**, kullanıcının istenen (kümeler için DBPROMPT_NOPROMPT DBPROP_INIT_PROMPT) hiçbir zaman olması belirtir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu yöntem oledb32.dll hizmet bileşenlerini kullanarak bir veri kaynağı nesnesi açılır; Bu DLL, kaynak havuzu, otomatik bir işlem kaydı ve benzeri gibi hizmet bileşenleri özellikleri uygulamasını içerir.

## <a name="openwithpromptfilename"></a> CDataSource::OpenWithPromptFileName

Bu yöntem bir iletişim kutusu ile kullanıcıya sorar ve kullanıcı tarafından belirtilen dosya kullanarak bir veri kaynağı açar.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT OpenWithPromptFileName(HWND hWnd = GetActiveWindow(   ),
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_NONE,
   LPCOLESTR szInitialDirectory = NULL) throw();
```

#### <a name="parameters"></a>Parametreler

*hWnd*<br/>
[in] İletişim kutusunun üst olacak penceresine işleyin.

*dwPromptOptions*<br/>
[in] Bulucu iletişim kutusunda görüntülenecek stilini belirler. Msdasc.h olası değerler için bkz.

*szInitialDirectory*<br/>
[in] Bulucu iletişim kutusunda görüntülemek için başlangıç dizini.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu yöntem oledb32.dll hizmet bileşenlerini kullanarak bir veri kaynağı nesnesi açılır; Bu DLL, kaynak havuzu, otomatik bir işlem kaydı ve benzeri gibi hizmet bileşenleri özellikleri uygulamasını içerir. Daha fazla bilgi için bkz: "OLE DB hizmetleri" OLE DB Programcı Başvurusu, [ https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true ](https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).

## <a name="openwithservicecomponents"></a> CDataSource::OpenWithServiceComponents

Hizmet bileşenleri oledb32.dll kullanarak bir veri kaynağı nesnesi açılır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT OpenWithServiceComponents (const CLSID clsid,
   DBPROPSET* pPropset = NULL,
   ULONG ulPropSets = 1);

HRESULT OpenWithServiceComponents (LPCSTR szProgID,
   DBPROPSET* pPropset = NULL,
   ULONG ulPropSets = 1);
```

#### <a name="parameters"></a>Parametreler

*CLSID*<br/>
[in] `CLSID` Veri sağlayıcısı.

*szProgID*<br/>
[in] Program Kimliği bir veri sağlayıcısı.

*pPropset*<br/>
[in] Bir dizi işaretçi [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) özelliklerini ve değerlerini ayarlamak için içeren yapılar. Bkz: [özellik kümeleri ve özellik gruplarını](/previous-versions/windows/desktop/ms713696(v=vs.85)) içinde *OLE DB Programcının Başvurusu* Windows SDK içinde. Veri kaynağı nesnesi başlatılırsa, özellikleri veri kaynağı özelliği grubuna ait olmalıdır. Aynı özellik birden çok kez belirtilmişse *pPropset*, hangi değerin kullanıldığını sağlayıcıya özgü kaldırılır. Varsa *ulPropSets* sıfırsa, bu parametre yoksayılır.

*ulPropSets*<br/>
[in] Sayısını [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) yapıları geçirilen *pPropSet* bağımsız değişken. Sağlayıcı bu sıfırsa yoksayar *pPropset*.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu yöntem oledb32.dll hizmet bileşenlerini kullanarak bir veri kaynağı nesnesi açılır; Bu DLL, kaynak havuzu, otomatik bir işlem kaydı ve benzeri gibi hizmet bileşenleri özellikleri uygulamasını içerir. Daha fazla bilgi için bkz: "OLE DB hizmetleri" OLE DB Programcı Başvurusu, [ https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true ](https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)