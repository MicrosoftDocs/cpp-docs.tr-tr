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
ms.openlocfilehash: 52c7e2ce5acdd2df33e2a6422535a337f0a43aec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368624"
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
Komutun kullanmasını istediğiniz erişimci `CDynamicParameterAccessor` `CDynamicStringAccessor`sınıfın `CEnumeratorAccessor`türü (, , veya ) gibi. Varsayılan, `CNoAccessor`sınıfın parametreleri veya çıkış sütunlarını desteklemediğini belirten bir değerdir.

*TRowset*<br/>
Komutun kullanmasını istediğiniz satır `CArrayRowset` kümesi `CNoRowset`sınıfı türü (örneğin veya) Varsayılan değer: `CRowset`.

*TMultiple*<br/>
Birden çok sonuç döndürebilen bir OLE DB komutu kullanmak için [CMultipleResults](../../data/oledb/cmultipleresults-class.md)belirtin. Aksi takdirde, [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)kullanın. Ayrıntılar için [IMultipleResults'a](/previous-versions/windows/desktop/ms721289(v=vs.85))bakın.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldbcli.h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Kapat](#close)|Geçerli komutu kapatır.|
|[GetNextResult](#getnextresult)|Birden çok sonuç kümesi kullanırken bir sonraki sonucu getirir.|
|[Aç](#open)|Komutu yürütür ve isteğe bağlı olarak bağlar.|

### <a name="inherited-methods"></a>Kalıtsal Yöntemler

|||
|-|-|
|[Oluştur](#create)|Belirtilen oturum için yeni bir komut oluşturur, ardından komut metnini ayarlar.|
|[CreateKomut](#createcommand)|Yeni bir komut oluşturur.|
|[Getparameterınfo](#getparameterinfo)|Komutun parametrelerinin, adlarının ve türlerinin listesini alır.|
|[Hazırlama](#prepare)|Geçerli komutu doğrular ve optimize eder.|
|[ReleaseCommand](#releasecommand)|Gerekirse parametre aksesuarını serbest bırakır, sonra komutu serbest bırakır.|
|[Setparameterınfo](#setparameterinfo)|Her komut parametresinin yerel türünü belirtir.|
|[Hazırlanmamış](#unprepare)|Geçerli komut yürütme planını atar.|

## <a name="remarks"></a>Açıklamalar

Parametre tabanlı bir işlem gerçekleştirmeniz veya bir komut yürütmeniz gerektiğinde bu sınıfı kullanın. Yalnızca basit bir satır kümesini açmanız gerekiyorsa, bunun yerine [CTable'ı](../../data/oledb/ctable-class.md) kullanın.

Kullandığınız erişimci sınıf, parametreleri ve verileri bağlama yöntemini belirler.

Bu sağlayıcı depolanan yordamları desteklemediği için (sorgu dizelerinde yalnızca sabitlere izin verildiğinden) OLE DB Sağlayıcısı jet için depolanmış yordamları kullanamayacağınızı unutmayın.

## <a name="ccommandclose"></a><a name="close"></a>CCommand::Kapat

Komutla ilişkili erişimci satır kümesini serbest bırakır.

### <a name="syntax"></a>Sözdizimi

```cpp
void Close();
```

### <a name="remarks"></a>Açıklamalar

Komut, bir satır kümesi, sonuç kümesi aksesuarı ve (isteğe bağlı olarak) parametreleri desteklemeyen ve parametre aksesuarı gerekmeyen tablolardan farklı olarak bir parametre aksesuarı kullanır.

Bir komutu çalıştırdığınızda, `Close` komuttan sonra hem de [ReleaseCommand'ı](../../data/oledb/ccommand-releasecommand.md) aramalısınız.

Aynı komutu tekrar tekrar yürütmek istediğinizde, aramadan önce her `Close` sonuç `Execute`kümesi aksesuarını arayarak serbest bırakmalısınız. Serinin sonunda, parametre aksesuarını arayarak `ReleaseCommand`serbest bırakmalısınız. Başka bir yaygın senaryo çıktı parametreleri olan bir depolanmış yordamı çağırıyor. Birçok sağlayıcıda (SQL Server için OLE DB sağlayıcısı gibi) sonuç ayarlı erişime sahip olana kadar çıktı parametre değerlerine erişilemez. Döndürülen satır kümesini ve sonuç kümesi aksesuarını kapatmak için arayın, `Close` ancak parametre aksesuarını değil, böylece çıktı parametre değerlerini almanıza olanak sağlar.

### <a name="example"></a>Örnek

Aşağıdaki örnek, aynı komutu tekrar tekrar nasıl arayabildiğinizi `Close` ve `ReleaseCommand` ne zaman uygulayabileceğinizi gösterir.

[!code-cpp[NVC_OLEDB_Consumer#2](../../data/oledb/codesnippet/cpp/ccommand-close_1.cpp)]

## <a name="ccommandgetnextresult"></a><a name="getnextresult"></a>CCommand::GetNextResult

Varsa bir sonraki sonuç kümesini getirir.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetNextResult(DBROWCOUNT* pulRowsAffected,
   bool bBind = true) throw();
```

#### <a name="parameters"></a>Parametreler

*pulRowsEtkilenen*<br/>
[içeri/çıkış] Bir komuttan etkilenen satır sayısının döndürüldüğü belleğe işaretçi.

*bBind*<br/>
[içinde] Yürütüldükten sonra komutu otomatik olarak bağlayıp bağlamayacağını belirtir. Varsayılan **değer doğrudur,** bu da komutun otomatik olarak bağlanmasına neden olur. *bBind'i* **false** olarak ayarlamak, komutun otomatik olarak bağlanmasını engeller, böylece el ile bağlanabilirsiniz. (El ile bağlama, OLAP kullanıcıları nın özellikle ilgisini çekiyor.)

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Bir sonuç kümesi daha önce alınmışsa, bu işlev önceki sonuç kümesini serbest bırakır ve sütunları unbinds. *bBind* **doğruysa,** yeni sütunları bağlar.

Bu `CCommand` işlevi yalnızca şablon parametresi *TMultiple'yi*=`CMultipleResults`ayarlayarak birden çok sonuç belirtmişseniz aramalısınız.

## <a name="ccommandopen"></a><a name="open"></a>CCommand::Aç

Komutu yürütür ve isteğe bağlı olarak bağlar.

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

*Oturum*<br/>
[içinde] Komutun yürütüldek oturumu.

*wszKomut*<br/>
[içinde] Unicode dizesi olarak geçirilen yürütme komutu. Kullanırken `CAccessor`NULL olabilir , bu durumda komut [DEFINE_COMMAND](../../data/oledb/define-command.md) makroya geçirilen değerden alınır. Ayrıntılar için *OLE DB Programcısı Nın Başvurusu'nda* [ICommand::Execute in iCommand::Execute.](/previous-versions/windows/desktop/ms718095(v=vs.85))

*szKomut*<br/>
[içinde] Bu parametre nin bir ANSI komut dizesi alması dışında *wszCommand* ile aynıdır. Bu yöntemin dördüncü biçimi NULL değeri alabilir. Ayrıntılar için bu konunun ilerleyen saatlerinde "Açıklamalar"a bakın.

*pPropSet*<br/>
[içinde] Ayarlanacak özellikleri ve değerleri içeren [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) yapıları dizisiiçin bir işaretçi. Windows SDK'daki *OLE DB Programcısı Nın Başvurusu'ndaki* [Özellik Kümeleri ve Özellik Grupları'na](/previous-versions/windows/desktop/ms713696(v=vs.85)) bakın.

*pRowsEtkilenen*<br/>
[içeri/çıkış] Bir komuttan etkilenen satır sayısının döndürüldüğü belleğe işaretçi. pRowsAffected NULL ise, satır sayısı döndürülür. * \** Aksi `Open` takdirde, aşağıdaki koşullara göre * \*pRowsAffected* ayarlar:

|Eğer|Ardından|
|--------|----------|
|Element `cParamSets` `pParams` 1'den büyüktür|pRowsAffected, yürütmede belirtilen tüm parametre kümelerinden etkilenen toplam satır sayısını temsil eder. * \**|
|Etkilenen satır sayısı kullanılamıyor|pRowsAffected -1 olarak ayarlanır. * \**|
|Komut satırları güncelleştirmez, silmez veya eklemez|* \*pRowsEtkilenen* tanımsız.|

*guidCommand*<br/>
[içinde] Sağlayıcının komut metnini ayrışdırmada kullanması için sözdizimini ve genel kuralları belirten bir GUID. Ayrıntılar için *OLE DB Programcısı* referansında [ICommandText::GetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85)) ve [ICommandText::SetCommandText'e](/previous-versions/windows/desktop/ms709757(v=vs.85)) bakın.

*bBind*<br/>
[içinde] Yürütüldükten sonra komutu otomatik olarak bağlayıp bağlamayacağını belirtir. Varsayılan **değer doğrudur,** bu da komutun otomatik olarak bağlanmasına neden olur. *bBind'i* **false** olarak ayarlamak, komutun otomatik olarak bağlanmasını engeller, böylece el ile bağlanabilirsiniz. (El ile bağlama, OLAP kullanıcıları nın özellikle ilgisini çekiyor.)

*ulPropSets*<br/>
[içinde] *pPropSet* bağımsız değişkeninde geçirilen [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) yapılarının sayısı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Bir oturum `Open` almak, bir komut oluşturmak ve gerektiğinde herhangi bir parametre bağlama komutu yürütmek ilk üç formları.

İlk form `Open` Unicode komut dizesini alır ve varsayılan değeri yoktur.

İkinci form `Open` bir ANSI komut dizesini alır ve varsayılan değer almaz (varolan ANSI uygulamalarıyla geriye dönük uyumluluk sağlanır).

Üçüncü form, `Open` varsayılan NULL değerine sahip tür **int'i** nedeniyle komut dizesinin NULL olmasını sağlar. Arama `Open(session, NULL);` için veya `Open(session);` NULL türü **int**olduğundan sağlanır. Bu **sürüm, int** parametrenin NULL olmasını gerektirir ve iddia eder.

Zaten bir komut `Open` oluşturduk ve tek bir [Hazırla](../../data/oledb/ccommand-prepare.md) ve birden çok yürütme gerçekleştirmek istediğiniz de dördüncü formu kullanın.

> [!NOTE]
> `Open`aramalar `Execute`, sırayla `GetNextResult`çağırır .

## <a name="ccommandcreate"></a><a name="create"></a>CCommand::Oluştur

[CCommand çağırır::CreateCommand](../../data/oledb/ccommand-createcommand.md) belirtilen oturum için bir komut oluşturmak için, sonra [iCommandText çağırır::SetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85)) komut metnini belirtmek için.

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

*Oturum*<br/>
[içinde] Komutu oluşturmak için hangi oturum.

*wszKomut*<br/>
[içinde] Komut dizesinin Unicode metnine işaretçi.

*szKomut*<br/>
[içinde] Komut dizesinin ANSI metnine işaretçi.

*guidCommand*<br/>
[içinde] Sağlayıcının komut metnini ayrışdırmada kullanması için sözdizimini ve genel kuralları belirten bir GUID. Lehçelerin açıklaması için, [Bkz. ICommandText::GetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85)) in The *OLE DB Programcı'nın Referansı.*

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

İlk form `Create` unicode komut dizesini alır. İkinci form `Create` bir ANSI komut dizesini alır (varolan ANSI uygulamalarıyla geriye dönük uyumluluk için sağlanır).

## <a name="ccommandcreatecommand"></a><a name="createcommand"></a>CCommand::Create Komutu

Yeni bir komut oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CCommandBase::CreateCommand(const CSession& session) throw ();
```

#### <a name="parameters"></a>Parametreler

*Oturum*<br/>
[içinde] Yeni `CSession` komutla ilişkilendirilecek bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen oturum nesnesini kullanarak bir komut oluşturur.

## <a name="ccommandgetparameterinfo"></a><a name="getparameterinfo"></a>CCommand::GetParameterInfo

Komutun parametrelerinin, adlarının ve türlerinin listesini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CCommandBase::GetParameterInfo(DB_UPARAMS* pParams,
   DBPARAMINFO** ppParamInfo,
   OLECHAR** ppNamesBuffer) throw ();
```

#### <a name="parameters"></a>Parametreler

Bkz. [ICommandWithParametreler::GetParameterInfo](/previous-versions/windows/desktop/ms714917(v=vs.85)) in the *OLE DB Programcı'nın Referansı*.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

## <a name="ccommandprepare"></a><a name="prepare"></a>CCommand::Prepare

Geçerli komutu doğrular ve optimize eder.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CCommandBase::Prepare(ULONG cExpectedRuns = 0) throw();
```

#### <a name="parameters"></a>Parametreler

*cExpectedRuns*<br/>
[içinde] Komutu kaç kez yürütmeyi beklediğiniz.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu yöntem OLE DB yöntemi [ICommandPrepare::Prepare](/previous-versions/windows/desktop/ms718370(v=vs.85))sarar.

## <a name="ccommandreleasecommand"></a><a name="releasecommand"></a>CCommand::ReleaseKomutu

Parametre erişimini serbest bırakır, sonra komutun kendisini serbest bırakır.

### <a name="syntax"></a>Sözdizimi

```cpp
void CCommandBase::ReleaseCommand() throw();
```

### <a name="remarks"></a>Açıklamalar

`ReleaseCommand`ile `Close`birlikte kullanılır. Kullanım ayrıntıları için [Kapat'a](../../data/oledb/ccommand-close.md) bakın.

## <a name="ccommandsetparameterinfo"></a><a name="setparameterinfo"></a>CCommand::SetParameterInfo

Her komut parametresinin yerel türünü belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CCommandBase::SetParameterInfo(DB_UPARAMS ulParams,
   const DBORDINAL* pOrdinals,
   const DBPARAMBINDINFO* pParamInfo) throw();
```

#### <a name="parameters"></a>Parametreler

Bkz. [ICommandWithParameters::SetParameterInfo](/previous-versions/windows/desktop/ms725393(v=vs.85)) in the *OLE DB Programcı'nın Referansı*.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

## <a name="ccommandunprepare"></a><a name="unprepare"></a>CCommand::Hazırlanmamış

Geçerli komut yürütme planını atar.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CCommandBase::Unprepare() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu yöntem OLE DB yöntemi [ICommandPrepare sarar::Unprepare](/previous-versions/windows/desktop/ms719635(v=vs.85)).

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
