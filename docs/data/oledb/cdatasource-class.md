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
ms.openlocfilehash: f6b5182fdc451217e2f61642f96e77f679c45d37
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216511"
---
# <a name="cdatasource-class"></a>CDataSource Sınıfı

Bir sağlayıcının veri kaynağına bir bağlantıyı temsil eden bir OLE DB veri kaynağı nesnesine karşılık gelir.

## <a name="syntax"></a>Sözdizimi

```cpp
class CDataSource
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Kapat](#close)|Bağlantıyı kapatır.|
|[Getınitializationstring](#getinitializationstring)|Şu anda açık olan veri kaynağının başlatma dizesini alır.|
|[GetProperties](#getproperties)|Bağlı veri kaynağı için şu anda ayarlanmış olan özelliklerin değerlerini alır.|
|[GetProperty](#getproperty)|Bağlı veri kaynağı için şu anda ayarlanmış olan tek bir özelliğin değerini alır.|
|[Aç](#open)|`CLSID`, `ProgID` Ya da `CEnumerator` çağıran tarafından sağlanmış bilinen bir ad kullanarak bir sağlayıcıya (veri kaynağı) bir bağlantı oluşturur.|
|[OpenFromFileName](#openfromfilename)|Kullanıcı tarafından sağlanan dosya adı tarafından belirtilen bir dosyadaki veri kaynağını açar.|
|[OpenFromInitializationString](#openfrominitializationstring)|Bir başlatma dizesi tarafından belirtilen veri kaynağını açar.|
|[OpenWithPromptFileName](#openwithpromptfilename)|Kullanıcının, ilgili veri kaynağını açmak için önceden oluşturulmuş bir veri bağlantısı dosyası seçmesine izin verir.|
|[OpenWithServiceComponents](#openwithservicecomponents)|Veri bağlantısı iletişim kutusunu kullanarak bir veri kaynağı nesnesi açar.|

## <a name="remarks"></a>Açıklamalar

Tek bir bağlantı için bir veya daha fazla veritabanı oturumu oluşturulabilir. Bu oturumlar tarafından temsil edilir `CSession` . İle oturum oluşturmadan önce bağlantıyı açmak için [CDataSource:: Open](../../data/oledb/cdatasource-open.md) ' i çağırmanız gerekir `CSession::Open` .

Öğesinin nasıl kullanılacağına ilişkin bir örnek için `CDataSource` bkz. [CATDB](../../overview/visual-cpp-samples.md) örneği.

## <a name="cdatasourceclose"></a><a name="close"></a>CDataSource:: Close

İşaretçiyi serbest bırakarak bağlantıyı kapatır `m_spInit` .

### <a name="syntax"></a>Sözdizimi

```cpp
void Close() throw();
```

## <a name="cdatasourcegetinitializationstring"></a><a name="getinitializationstring"></a>CDataSource:: Getınitializationstring

Şu anda açık olan bir veri kaynağının başlatma dizesini alır.

### <a name="syntax"></a>Söz dizimi

```cpp
HRESULT GetInitializationString(BSTR* pInitializationString,
   bool bIncludePassword = false) throw();
```

#### <a name="parameters"></a>Parametreler

*Pınitializationstring*<br/>
dışı Başlatma dizesinin işaretçisi.

*bIncludePassword*<br/>
[in] **`true`** dize bir parola içeriyorsa; Aksi takdirde **`false`** .

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Elde edilen başlatma dizesi daha sonra bu veri kaynağı bağlantısını yeniden açmak için kullanılabilir.

## <a name="cdatasourcegetproperties"></a><a name="getproperties"></a>CDataSource:: GetProperties

Bağlı veri kaynağı nesnesi için istenen özellik bilgilerini döndürür.

### <a name="syntax"></a>Söz dizimi

```cpp
HRESULT GetProperties(ULONG ulPropIDSets,
   constDBPROPIDSET* pPropIDSet,
   ULONG* pulPropertySets,
   DBPROPSET** ppPropsets) const throw();
```

#### <a name="parameters"></a>Parametreler

Windows SDK *OLE DB Programcının Başvurusu* Içindeki [IDBProperties:: GetProperties](/previous-versions/windows/desktop/ms714344(v=vs.85)) bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Tek bir özelliği almak için [GetProperty](../../data/oledb/cdatasource-getproperty.md)kullanın.

## <a name="cdatasourcegetproperty"></a><a name="getproperty"></a>CDataSource:: GetProperty

Bağlı veri kaynağı nesnesi için belirtilen özelliğin değerini döndürür.

### <a name="syntax"></a>Söz dizimi

```cpp
HRESULT GetProperty(const GUID& guid,
   DBPROPID propid,
   VARIANT* pVariant) const throw();
```

#### <a name="parameters"></a>Parametreler

*'ini*<br/>
'ndaki Özelliğin döndürüleceği özellik kümesini tanımlayan bir GUID.

*PROPID*<br/>
'ndaki Döndürülecek özelliğin özellik KIMLIĞI.

*pVariant*<br/>
dışı Variant için bir işaretçi, `GetProperty` özelliğin değerini döndürür.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Birden çok özellik almak için [GetProperties](../../data/oledb/cdatasource-getproperties.md)kullanın.

## <a name="cdatasourceopen"></a><a name="open"></a>CDataSource:: Open

, Veya bilinen bir ad kullanarak bir veri kaynağına bağlantı açar `CLSID` `ProgID` `CEnumerator` veya kullanıcıya bir Bulucu iletişim kutusu ister.

### <a name="syntax"></a>Söz dizimi

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

*in*<br/>
'ndaki `CLSID`Veri sağlayıcısı.

*pPropSet*<br/>
'ndaki Ayarlanacak özellikleri ve değerleri içeren bir [dbpropset](/previous-versions/windows/desktop/ms714367(v=vs.85)) yapıları dizisine yönelik bir işaretçi. Windows SDK *OLE DB Programcı başvurusu* Içindeki [özellik kümeleri ve özellik grupları](/previous-versions/windows/desktop/ms713696(v=vs.85)) bölümüne bakın.

*nPropertySets 'ler*<br/>
'ndaki *PPropset* bağımsız değişkeninde geçirilen [dbpropset](/previous-versions/windows/desktop/ms714367(v=vs.85)) yapılarının sayısı.

*pName*<br/>
'ndaki Bağlanılacak veritabanının adı.

*pUserName*<br/>
'ndaki Kullanıcının adı.

*pPassword*<br/>
'ndaki Kullanıcının parolası.

*nInitMode*<br/>
'ndaki Veritabanı başlatma modu. Geçerli başlatma modlarının bir listesi için Windows SDK *OLE DB Programcı başvurusu* Içindeki [başlatma özellikleri](/previous-versions/windows/desktop/ms723127(v=vs.85))' ne bakın. *NInitMode* değeri sıfırsa, bağlantıyı açmak için kullanılan özellik kümesine başlatma modu dahil değildir.

*Szprogıd*<br/>
'ndaki Bir program tanımlayıcısı.

*sının*<br/>
'ndaki Çağıran bir belirtmezse bağlantıyı açmaya yönelik bilinen adı almak için kullanılan bir [CEnumerator](../../data/oledb/cenumerator-class.md) nesnesi `CLSID` .

*lendiği*<br/>
'ndaki İletişim kutusunun üst öğesi olacak pencerenin tutamacı. *HWND* parametresini kullanan işlev aşırı yüklemesinin kullanılması, otomatik olarak hizmet bileşenlerini çağırır; Ayrıntılar için bkz. açıklamalar.

*dwPromptOptions*<br/>
'ndaki Görüntülenecek konum belirleyici iletişim kutusunun stilini belirler. Olası değerler için bkz. msdasc. h.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

*HWND* parametresini kullanan yöntem aşırı yüklemesi, oledb32.dll ' deki hizmet bileşenleriyle bir veri kaynağı nesnesi açar. Bu DLL, kaynak havuzu oluşturma, otomatik Işlem kaydı vb. gibi hizmet bileşenleri özelliklerinin uygulanmasını içerir. Daha fazla bilgi için, [OLE DB Programcı kılavuzundaki](/previous-versions/windows/desktop/ms713643(v=vs.85))OLE DB başvurusuna bakın.

*HWND* parametresini kullanmayan yöntem aşırı yüklemeleri, oledb32.dll ' deki hizmet bileşenlerini kullanmadan bir veri kaynağı nesnesi açın. Bu işlev aşırı yüklemeleri ile açılmış bir [CDataSource](../../data/oledb/cdatasource-class.md) nesnesi, hizmet bileşenleri işlevlerinin hiçbirini kullanmaz.

### <a name="example"></a>Örnek

Aşağıdaki kod, OLE DB şablonlarıyla bir Jet 4,0 veri kaynağının nasıl açılacağını gösterir. Jet veri kaynağını bir OLE DB veri kaynağı olarak değerlendirmiş olursunuz. Ancak, için çağrın `Open` iki özellik kümesine ihtiyacı vardır: biri DBPROPSET_DBINIT diğeri diğeri DBPROPSET_JETOLEDB_DBINIT için, DBPROP_JETOLEDB_DATABASEPASSWORD ayarlayabilmeniz için.

[!code-cpp[NVC_OLEDB_Consumer#7](../../data/oledb/codesnippet/cpp/cdatasource-open_1.cpp)]

## <a name="cdatasourceopenfromfilename"></a><a name="openfromfilename"></a>CDataSource:: OpenFromFileName

Kullanıcı tarafından sağlanan dosya adı tarafından belirtilen bir dosyadaki veri kaynağını açar.

### <a name="syntax"></a>Söz dizimi

```cpp
HRESULT OpenFromFileName(LPCOLESTR szFileName) throw();
```

#### <a name="parameters"></a>Parametreler

*szFileName*<br/>
'ndaki Bir dosyanın adı, genellikle bir veri kaynağı bağlantısı (. UDL) dosyası.

Veri bağlantısı dosyaları (. udl dosyaları) hakkında daha fazla bilgi için bkz. Windows SDK [veri bağlantısı API 'Sine genel bakış](/previous-versions/windows/desktop/ms718102(v=vs.85)) .

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu yöntem oledb32.dll; içindeki hizmet bileşenlerini kullanarak bir veri kaynağı nesnesi açar. Bu DLL, kaynak havuzu oluşturma, otomatik Işlem kaydı vb. gibi hizmet bileşenleri özelliklerinin uygulanmasını içerir. Daha fazla bilgi için, [OLE DB Programcı kılavuzundaki](/previous-versions/windows/desktop/ms713643(v=vs.85))OLE DB başvurusuna bakın.

## <a name="cdatasourceopenfrominitializationstring"></a><a name="openfrominitializationstring"></a>CDataSource:: OpenFromInitializationString

Kullanıcı tarafından sağlanan başlatma dizesi tarafından belirtilen bir veri kaynağını açar.

### <a name="syntax"></a>Söz dizimi

```cpp
HRESULT OpenFromInitializationString(LPCOLESTR szInitializationString,
   bool fPromptForInfo= false) throw();
```

#### <a name="parameters"></a>Parametreler

*Szınitializationstring*<br/>
'ndaki Başlatma dizesi.

*Fpromptforınfo*<br/>
'ndaki Bu bağımsız değişken olarak ayarlandıysa **`true`** , `OpenFromInitializationString` yalnızca daha fazla bilgi gerekiyorsa, kullanıcıdan istenmesini belirten DBPROP_INIT_PROMPT özelliğini DBPROMPT_COMPLETEREQUIRED olarak ayarlar. Bu, başlatma dizesinin parola gerektiren bir veritabanını belirttiği durumlar için yararlıdır, ancak dize parolayı içermez. Veritabanına bağlanmaya çalışırken kullanıcıdan bir parola (veya eksik olan herhangi bir bilgi) istenir.

Varsayılan değer **`false`** , kullanıcıya hiçbir şekilde sorulmayacağını (DBPROMPT_NOPROMPT DBPROP_INIT_PROMPT ayarlar) belirtir.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu yöntem oledb32.dll; içindeki hizmet bileşenlerini kullanarak bir veri kaynağı nesnesi açar. Bu DLL, kaynak havuzu oluşturma, otomatik Işlem kaydı vb. gibi hizmet bileşenleri özelliklerinin uygulanmasını içerir.

## <a name="cdatasourceopenwithpromptfilename"></a><a name="openwithpromptfilename"></a>CDataSource:: OpenWithPromptFileName

Bu yöntem kullanıcıya bir iletişim kutusu sorar, ardından Kullanıcı tarafından belirtilen dosyayı kullanarak bir veri kaynağı açar.

### <a name="syntax"></a>Söz dizimi

```cpp
HRESULT OpenWithPromptFileName(HWND hWnd = GetActiveWindow(   ),
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_NONE,
   LPCOLESTR szInitialDirectory = NULL) throw();
```

#### <a name="parameters"></a>Parametreler

*lendiği*<br/>
'ndaki İletişim kutusunun üst öğesi olacak pencerenin tutamacı.

*dwPromptOptions*<br/>
'ndaki Görüntülenecek konum belirleyici iletişim kutusunun stilini belirler. Olası değerler için bkz. msdasc. h.

*Szınitialdirectory*<br/>
'ndaki Konumlandırıcı iletişim kutusunda görüntülenecek ilk dizin.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu yöntem oledb32.dll; içindeki hizmet bileşenlerini kullanarak bir veri kaynağı nesnesi açar. Bu DLL, kaynak havuzu oluşturma, otomatik Işlem kaydı vb. gibi hizmet bileşenleri özelliklerinin uygulanmasını içerir. Daha fazla bilgi için, [OLE DB Programcı kılavuzundaki](/previous-versions/windows/desktop/ms713643(v=vs.85))OLE DB başvurusuna bakın.

## <a name="cdatasourceopenwithservicecomponents"></a><a name="openwithservicecomponents"></a>CDataSource:: OpenWithServiceComponents

oledb32.dll ' deki hizmet bileşenlerini kullanarak bir veri kaynağı nesnesi açar.

### <a name="syntax"></a>Söz dizimi

```cpp
HRESULT OpenWithServiceComponents (const CLSID clsid,
   DBPROPSET* pPropset = NULL,
   ULONG ulPropSets = 1);

HRESULT OpenWithServiceComponents (LPCSTR szProgID,
   DBPROPSET* pPropset = NULL,
   ULONG ulPropSets = 1);
```

#### <a name="parameters"></a>Parametreler

*in*<br/>
'ndaki `CLSID`Veri sağlayıcısı.

*Szprogıd*<br/>
'ndaki Veri sağlayıcısının program KIMLIĞI.

*pPropset*<br/>
'ndaki Ayarlanacak özellikleri ve değerleri içeren bir [dbpropset](/previous-versions/windows/desktop/ms714367(v=vs.85)) yapıları dizisine yönelik bir işaretçi. Windows SDK *OLE DB Programcı başvurusu* Içindeki [özellik kümeleri ve özellik grupları](/previous-versions/windows/desktop/ms713696(v=vs.85)) bölümüne bakın. Veri kaynağı nesnesi başlatılmışsa, özellikler veri kaynağı özellik grubuna ait olmalıdır. Aynı özellik *pPropset*içinde birden çok kez belirtilirse, kullanılan değer sağlayıcıya özeldir. *UlPropSets* sıfır ise, bu parametre yok sayılır.

*ulPropSets*<br/>
'ndaki *PPropset* bağımsız değişkeninde geçirilen [dbpropset](/previous-versions/windows/desktop/ms714367(v=vs.85)) yapılarının sayısı. Bu sıfırsa, sağlayıcı *pPropset*'i yoksayar.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu yöntem oledb32.dll; içindeki hizmet bileşenlerini kullanarak bir veri kaynağı nesnesi açar. Bu DLL, kaynak havuzu oluşturma, otomatik Işlem kaydı vb. gibi hizmet bileşenleri özelliklerinin uygulanmasını içerir. Daha fazla bilgi için, [OLE DB Programcı kılavuzundaki](/previous-versions/windows/desktop/ms713643(v=vs.85))OLE DB başvurusuna bakın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB tüketici şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
