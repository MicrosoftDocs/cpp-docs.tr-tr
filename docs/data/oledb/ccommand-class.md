---
title: CCommand Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL::CCommand
- CCommand
- ATL.CCommand
- CCommand.Close
- CCommand::Close
- CCommand.Create
- CCommand::Create
- CCommand.CreateCommand
- CreateCommand
- CCommand::CreateCommand
- ATL::CCommand::GetNextResult
- CCommand::GetNextResult
- GetNextResult
- CCommand.GetNextResult
- ATL.CCommand.GetNextResult
- GetParameterInfo
- CCommand.GetParameterInfo
- CCommand::GetParameterInfo
- ATL.CCommand.Open
- ATL::CCommand::Open
- CCommand.Open
- CCommand::Open
- CCommand.Prepare
- CCommand::Prepare
- Prepare
- CCommand.ReleaseCommand
- ReleaseCommand
- CCommand::ReleaseCommand
- SetParameterInfo
- CCommand.SetParameterInfo
- CCommand::SetParameterInfo
- Unprepare
- CCommand.Unprepare
- CCommand::Unprepare
helpviewer_keywords:
- CCommand class
- Close method
- Create method [C++]
- CreateCommand method
- GetNextResult method
- GetParameterInfo method
- Open method
- Prepare method
- ReleaseCommand method
- SetParameterInfo method
- Unprepare method
ms.assetid: 0760bfc5-b9ee-4aee-8e54-31bd78714d3a
ms.openlocfilehash: 109998dd742828b3c41672fa2afa8716e4687f6a
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91501008"
---
# <a name="ccommand-class"></a>CCommand Sınıfı

Bir komutu ayarlamak ve yürütmek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class TAccessor = CNoAccessor,
   template <typename T> class TRowset = CRowset,
   class TMultiple = CNoMultipleResults>
class CCommand :
   public CAccessorRowset <TAccessor, TRowset>,
   public CCommandBase,
   public TMultiple
```

### <a name="parameters"></a>Parametreler

*TAccessor*<br/>
Komutun kullanmasını istediğiniz erişimci sınıfının türü ( `CDynamicParameterAccessor` veya gibi `CDynamicStringAccessor` `CEnumeratorAccessor` ). Varsayılan olarak, `CNoAccessor` sınıfının parametreleri veya çıkış sütunlarını desteklemediğini belirtir.

*TRowset*<br/>
Komutun kullanmasını istediğiniz satır kümesi sınıfının türü ( `CArrayRowset` veya gibi `CNoRowset` ). Varsayılan değer: `CRowset`.

*TMultiple*<br/>
Birden çok sonuç döndüresağlayan bir OLE DB komutu kullanmak için [CMultipleResults](../../data/oledb/cmultipleresults-class.md)' ı belirtin. Aksi takdirde, [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)kullanın. Ayrıntılar için bkz. [IMultipleResults](/previous-versions/windows/desktop/ms721289(v=vs.85)).

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

| Ad | Açıklama |
|-|-|
|[Kapat](#close)|Geçerli komutu kapatır.|
|[GetNextResult](#getnextresult)|Birden çok sonuç kümesi kullanırken sonraki sonucu getirir.|
|[Aç](#open)|Yürütür ve isteğe bağlı olarak komutunu bağlar.|

### <a name="inherited-methods"></a>Devralınan Yöntemler

| Ad | Açıklama |
|-|-|
|[Oluştur](#create)|Belirtilen oturum için yeni bir komut oluşturur ve sonra komut metnini ayarlar.|
|[CreateCommand](#createcommand)|Yeni bir komut oluşturur.|
|[GetParameterInfo](#getparameterinfo)|Komutun parametrelerinin, adlarının ve türlerinin bir listesini alır.|
|[Hazırlama](#prepare)|Geçerli komutu doğrular ve iyileştirir.|
|[ReleaseCommand](#releasecommand)|Gerekirse parametre erişimcisini serbest bırakır, sonra komutu serbest bırakır.|
|[SetParameterInfo](#setparameterinfo)|Her komut parametresinin yerel türünü belirtir.|
|[Unprepare](#unprepare)|Geçerli komut yürütme planını atar.|

## <a name="remarks"></a>Açıklamalar

Parametre tabanlı bir işlem gerçekleştirmeniz veya bir komut yürütmeniz gerektiğinde bu sınıfı kullanın. Yalnızca basit bir satır kümesi açmanız gerekiyorsa, bunun yerine [CTable](../../data/oledb/ctable-class.md) kullanın.

Kullandığınız erişimci sınıfı, parametreleri ve verileri bağlama yöntemini belirler.

Sağlayıcı saklı yordamları desteklemediğinden, saklı yordamları Jet için OLE DB sağlayıcısıyla kullanamazsınız (sorgu dizelerinde yalnızca sabitler kullanılabilir).

## <a name="ccommandclose"></a><a name="close"></a> CCommand:: Close

Komutuyla ilişkili erişimci satır kümesini yayınlar.

### <a name="syntax"></a>Sözdizimi

```cpp
void Close();
```

### <a name="remarks"></a>Açıklamalar

Bir komut satır kümesi, sonuç kümesi erişimcisi ve (isteğe bağlı olarak, parametreleri desteklemeyen ve parametre erişimcisi gerektirmeyen) bir parametre erişimcisi kullanır.

Bir komut yürüttüğünüzde, komutundan sonra hem hem de `Close` [ReleaseCommand](#releasecommand) çağırmalısınız.

Aynı komutu tekrar tekrar çalıştırmak istediğinizde, çağrılmadan önce çağırarak her sonuç kümesi erişimcisini serbest bırakmanız gerekir `Close` `Execute` . Serinin sonunda, çağırarak parametre erişimcisini serbest bırakmanız gerekir `ReleaseCommand` . Diğer bir yaygın senaryo, çıkış parametrelerine sahip saklı bir yordamı çağırıyor. Birçok sağlayıcıda (SQL Server için OLE DB sağlayıcısı gibi), sonuç kümesi erişimcisini kapatıncaya kadar çıkış parametresi değerlerine erişilemez. `Close`Döndürülen satır kümesini ve sonuç kümesi erişimcisini kapatmak için çağrı yapın, bu nedenle çıkış parametre değerlerini almanızı sağlar.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `Close` `ReleaseCommand` aynı komutu tekrar tekrar çalıştırdığınızda nasıl çağrılacağını gösterir.

[!code-cpp[NVC_OLEDB_Consumer#2](../../data/oledb/codesnippet/cpp/ccommand-close_1.cpp)]

## <a name="ccommandgetnextresult"></a><a name="getnextresult"></a> CCommand:: GetNextResult

Varsa, bir sonraki sonuç kümesini getirir.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetNextResult(DBROWCOUNT* pulRowsAffected,
   bool bBind = true) throw();
```

#### <a name="parameters"></a>Parametreler

*daha sonra Pulrowsabetkilenen*<br/>
[ın/out] Bir komuttan etkilenen satır sayısının döndürüldüğü bir bellek işaretçisi.

*bBind*<br/>
'ndaki Çalıştırıldıktan sonra komutun otomatik olarak bağlanıp bağlanmayacağını belirtir. Varsayılan olarak, **`true`** komut otomatik olarak bağlanmasına neden olur. *BBind* öğesinin ayarlanması, **`false`** el ile bağlayabilmeniz için komutun otomatik bağlamasını engeller. (El ile bağlama, OLAP kullanıcılarına özellikle ilgi çekici bir şekilde yapılır.)

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Bir sonuç kümesi daha önce getirildiyseniz, bu işlev önceki sonuç kümesini serbest bırakır ve sütunların bağlantısını kaldırır. *BBind* ise **`true`** , yeni sütunları bağlar.

Bu işlevi yalnızca `CCommand` *TMultiple*şablon parametresini ayarlayarak birden çok sonuç belirttiyseniz çağırmalısınız = `CMultipleResults` .

## <a name="ccommandopen"></a><a name="open"></a> CCommand:: Open

Yürütür ve isteğe bağlı olarak komutunu bağlar.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT Open(const CSession& session,
   LPCWSTR wszCommand,
   DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   REFGUID guidCommand = DBGUID_DEFAULT,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();

HRESULT Open(const CSession& session,
   LPCSTR szCommand,
   DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   REFGUID guidCommand = DBGUID_DEFAULT,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();

HRESULT Open(const CSession& session,
   INT szCommand = NULL,
   DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   REFGUID guidCommand = DBGUID_DEFAULT,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();

HRESULT Open(DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();
```

#### <a name="parameters"></a>Parametreler

*oturumuna*<br/>
'ndaki Komutun çalıştırılacağı oturum.

*wszCommand*<br/>
'ndaki Yürütülecek komut, Unicode dizesi olarak geçirilir. Kullanılırken NULL olabilir `CAccessor` , bu durumda komut [DEFINE_COMMAND](./macros-and-global-functions-for-ole-db-consumer-templates.md#define_command) makroya geçirilen değerden alınır. Ayrıntılar için *OLE DB Programcı başvurusunda* bkz. [ICommand:: Execute](/previous-versions/windows/desktop/ms718095(v=vs.85)) .

*szCommand*<br/>
'ndaki *WszCommand* ile aynıdır, bu parametre bir ANSI komut dizesi alır. Bu yöntemin dördüncü formu NULL değer alabilir. Ayrıntılar için bu konunun devamındaki "açıklamalar" bölümüne bakın.

*pPropSet*<br/>
'ndaki Ayarlanacak özellikleri ve değerleri içeren bir [dbpropset](/previous-versions/windows/desktop/ms714367(v=vs.85)) yapıları dizisine yönelik bir işaretçi. Windows SDK *OLE DB Programcı başvurusu* Içindeki [özellik kümeleri ve özellik grupları](/previous-versions/windows/desktop/ms713696(v=vs.85)) bölümüne bakın.

*etkilenen Prowsa*<br/>
[ın/out] Bir komuttan etkilenen satır sayısının döndürüldüğü bir bellek işaretçisi. Eğer * \* PROWSA,* null ise, satır sayısı döndürülmez. Aksi takdirde, `Open` aşağıdaki koşullara göre * \* prowsa'* u ayarlar:

|Eğer|Ardından|
|--------|----------|
|`cParamSets`Öğesi 1 ' `pParams` den büyük|* \* prowsaall* , yürütmede belirtilen tüm parametre kümelerinden etkilenen toplam satır sayısını temsil eder.|
|Etkilenen satır sayısı kullanılamıyor|* \* Prowsa,* -1 olarak ayarlanmıştır.|
|Komut satırları güncelleştirmez, silemez veya eklemez|* \* Prowsa,* tanımsız.|

*Guidkomutu*<br/>
'ndaki Sağlayıcı için komut metnini ayrıştırırken kullanılacak sözdizimini ve genel kuralları belirten bir GUID. Ayrıntılar için *OLE DB Programcı başvurusunda* bkz. [ICommandText:: GetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85)) ve [ICommandText \ metin:: setCommandText](/previous-versions/windows/desktop/ms709757(v=vs.85)) .

*bBind*<br/>
'ndaki Çalıştırıldıktan sonra komutun otomatik olarak bağlanıp bağlanmayacağını belirtir. Varsayılan olarak, **`true`** komut otomatik olarak bağlanmasına neden olur. *BBind* öğesinin ayarlanması, **`false`** el ile bağlayabilmeniz için komutun otomatik bağlamasını engeller. (El ile bağlama, OLAP kullanıcılarına özellikle ilgi çekici bir şekilde yapılır.)

*ulPropSets*<br/>
'ndaki *PPropset* bağımsız değişkeninde geçirilen [dbpropset](/previous-versions/windows/desktop/ms714367(v=vs.85)) yapılarının sayısı.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

İlk üç form `Open` bir oturum alır, bir komut oluşturun ve gerekli tüm parametreleri bağlayarak komutu yürütün.

İlk biçimi `Open` Unicode komut dizesi alır ve varsayılan değere sahip değildir.

İkinci biçimi `Open` ANSI komut dizesi alır ve varsayılan değer değildir (mevcut ANSI uygulamalarıyla geriye dönük uyumluluk için sağlanmaz).

Öğesinin `Open` **`int`** varsayılan değeri null olan türde olduğundan, üçüncü biçim komut dizesinin null olmasına izin verir. Çağırma için `Open(session, NULL);` veya null türünde olduğu için sağlanır `Open(session);` **`int`** . Bu sürüm için parametresinin NULL olduğunu onaylar ve onaylar **`int`** .

`Open`Zaten bir komut oluşturduğunuz ve tek bir [hazırlama](#prepare) ve birden çok yürütme gerçekleştirmek istediğiniz zaman dördüncü formunu kullanın.

> [!NOTE]
> `Open` çağrılar `Execute` olan çağırır `GetNextResult` .

## <a name="ccommandcreate"></a><a name="create"></a> CCommand:: Create

Belirtilen oturum için bir komut oluşturmak için [CCommand:: CreateCommand](#createcommand) çağırır, ardından komut metnini belirtmek Için [ICommandText:: setCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85)) çağırır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CCommandBase::Create(const CSession& session,
   LPCWSTR wszCommand,
   REFGUID guidCommand = DBGUID_DEFAULT) throw ();

HRESULT CCommandBase::Create(const CSession& session,
   LPCSTR szCommand,
   REFGUID guidCommand = DBGUID_DEFAULT) throw ();
```

#### <a name="parameters"></a>Parametreler

*oturumuna*<br/>
'ndaki Komutun oluşturulacağı bir oturum.

*wszCommand*<br/>
'ndaki Komut dizesinin Unicode metnine yönelik bir işaretçi.

*szCommand*<br/>
'ndaki Komut dizesinin ANSI metnine yönelik bir işaretçi.

*Guidkomutu*<br/>
'ndaki Sağlayıcı için komut metnini ayrıştırırken kullanılacak sözdizimini ve genel kuralları belirten bir GUID. Çapların açıklaması için *OLE DB Programcı başvurusunda* [ICommandText:: GetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85)) ' i inceleyin.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

İlk biçimi `Create` bir Unicode komut dizesi alır. İkinci biçimi `Create` BIR ANSI komut dizesi alır (mevcut ANSI uygulamalarıyla geriye dönük uyumluluk için verilmiştir).

## <a name="ccommandcreatecommand"></a><a name="createcommand"></a> CCommand:: CreateCommand

Yeni bir komut oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CCommandBase::CreateCommand(const CSession& session) throw ();
```

#### <a name="parameters"></a>Parametreler

*oturumuna*<br/>
'ndaki `CSession` Yeni komutla ilişkilendirilecek nesne.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen oturum nesnesini kullanarak bir komut oluşturur.

## <a name="ccommandgetparameterinfo"></a><a name="getparameterinfo"></a> CCommand:: GetParameterInfo

Komutun parametrelerinin, adlarının ve türlerinin bir listesini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CCommandBase::GetParameterInfo(DB_UPARAMS* pParams,
   DBPARAMINFO** ppParamInfo,
   OLECHAR** ppNamesBuffer) throw ();
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [ICommandWithParameters:: GetParameterInfo](/previous-versions/windows/desktop/ms714917(v=vs.85)) bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

## <a name="ccommandprepare"></a><a name="prepare"></a> CCommand::P Repa

Geçerli komutu doğrular ve iyileştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CCommandBase::Prepare(ULONG cExpectedRuns = 0) throw();
```

#### <a name="parameters"></a>Parametreler

*cExpectedRuns*<br/>
'ndaki Komutu yürütmeyi kaç kez beklediğinizi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [ICommandText::P repof](/previous-versions/windows/desktop/ms718370(v=vs.85))OLE DB yöntemini sarmalanmış.

## <a name="ccommandreleasecommand"></a><a name="releasecommand"></a> CCommand:: ReleaseCommand

Parametre erişimcisini serbest bırakır, ardından komutun kendisini yayınlar.

### <a name="syntax"></a>Sözdizimi

```cpp
void CCommandBase::ReleaseCommand() throw();
```

### <a name="remarks"></a>Açıklamalar

`ReleaseCommand` , ile birlikte kullanılır `Close` . Bkz. kullanım ayrıntıları için [kapatma](#close) .

## <a name="ccommandsetparameterinfo"></a><a name="setparameterinfo"></a> CCommand:: SetParameterInfo

Her komut parametresinin yerel türünü belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CCommandBase::SetParameterInfo(DB_UPARAMS ulParams,
   const DBORDINAL* pOrdinals,
   const DBPARAMBINDINFO* pParamInfo) throw();
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [ıcomtionwithparameters:: SetParameterInfo](/previous-versions/windows/desktop/ms725393(v=vs.85)) bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

## <a name="ccommandunprepare"></a><a name="unprepare"></a> CCommand:: Prepare

Geçerli komut yürütme planını atar.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CCommandBase::Unprepare() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [ICommandText:: unprepare](/previous-versions/windows/desktop/ms719635(v=vs.85))OLE DB yöntemini sarmalanmış.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB tüketici şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
