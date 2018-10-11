---
title: CCommand sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: de27441658c4c0537384447028a0383a0d87756b
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/11/2018
ms.locfileid: "49083273"
---
# <a name="ccommand-class"></a>CCommand Sınıfı

Ayarlayın ve komutu yürütmek için yöntemler sağlar.  
  
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
Erişimci sınıf türü (gibi `CDynamicParameterAccessor`, `CDynamicStringAccessor`, veya `CEnumeratorAccessor`) kullanmak için komutu istiyor. Varsayılan `CNoAccessor`, sınıfı değil destek parametreleri veya çıkış sütunları belirtir.  
  
*CRowset*<br/>
Satır kümesi sınıfı türü (gibi `CArrayRowset` veya `CNoRowset`) kullanmak için komutu istiyor. Varsayılan, `CRowset` değeridir.  
  
*TMultiple*<br/>
Birden çok sonuç döndüren bir OLE DB komutu kullanmak için belirtin [CMultipleResults](../../data/oledb/cmultipleresults-class.md). Aksi takdirde kullanın [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md). Ayrıntılar için bkz [IMultipleResults](/previous-versions/windows/desktop/ms721289).  

## <a name="requirements"></a>Gereksinimler  

**Başlık:** atldbcli.h  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[Kapat](#close)|Geçerli komut kapatır.|  
|[GetNextResult](#getnextresult)|Birden çok sonuç kümeleri kullanırken, sonraki sonuç getirir.|  
|[açın](#open)|Yürütür ve isteğe bağlı olarak komut bağlar.|  
  
### <a name="inherited-methods"></a>Devralınan yöntemleri  
  
|||  
|-|-|  
|[Oluşturma](#create)|Belirtilen oturum için yeni bir komut oluşturur, ardından komut metni ayarlar.|  
|[CreateCommand](#createcommand)|Yeni bir komut oluşturur.|  
|[GetParameterInfo](#getparameterinfo)|Komut parametreleri, adlarını ve türlerini listesini alır.|  
|[Hazırlama](#prepare)|Doğrular ve geçerli komutu en iyi duruma getirir.|  
|[ReleaseCommand](#releasecommand)|Gerekirse parametresi erişimci yayımlar ve ardından komut serbest bırakır.|  
|[SetParameterInfo](#setparameterinfo)|Her komut parametresi yerel türünü belirtir.|  
|[Unprepare](#unprepare)|Geçerli komut yürütme planını atar.|  
  
## <a name="remarks"></a>Açıklamalar  

Bu sınıf, parametre tabanlı bir işlemi gerçekleştirme veya bir komut çalıştırmak ihtiyacınız olduğunda kullanın. Basit bir satır kümesinde açmak yalnızca ihtiyacınız varsa, [CTable](../../data/oledb/ctable-class.md) yerine.  
  
Kullanmakta olduğunuz erişimci sınıfında parametreleri ve veri bağlama yöntemini belirler.  
  
Bu sağlayıcı tarafından desteklenmeyen saklı yordamlar OLE DB sağlayıcısı ile Jet için kullanamazsınız, çünkü olduğunu not saklı yordamları (yalnızca sabitler sorgu dizelerine izin verilir).  

## <a name="close"></a> CCommand::Close

Komut ile ilişkili erişimci satır kümesini serbest bırakır.  
  
### <a name="syntax"></a>Sözdizimi

```cpp
void Close();  
```  
  
### <a name="remarks"></a>Açıklamalar  

Bir komut, bir satır kümesi, sonuç kümesi erişimcisi ve (isteğe bağlı olarak) bir parametre erişimci (aksine, parametreleri desteklemiyor ve parametre erişimci gerekmez tablolar) kullanır.  
  
Bir komutu yürütürken, her ikisi de çağırmalıdır `Close` ve [ReleaseCommand](../../data/oledb/ccommand-releasecommand.md) komuttan sonra.  
  
Tekrar tekrar aynı komutu yürütmek istediğiniz zaman çağırarak her sonuç kümesi erişimcisi serbest bırakmalısınız `Close` çağırmadan önce `Execute`. Serinin sonunda, parametre erişimci çağırarak serbest bırakmalısınız `ReleaseCommand`. Başka bir yaygın bir senaryo, çıktı parametreleri olan bir saklı yordam çağırıyor. Sonuç kümesi erişimcisi kapatana kadar birçok sağlayıcıları (OLE DB sağlayıcısı için SQL Server gibi) çıkış parametresi değerleri erişilebilir değil. Çağrı `Close` döndürülen satır ve sonuç kümesi erişimcisi, ancak parametre erişimci kapatmak için bu nedenle, çıkış parametresi değerleri almak izin verme.  
  
### <a name="example"></a>Örnek  

Aşağıdaki örnek nasıl çağırabilirsiniz gösterir `Close` ve `ReleaseCommand` yürüttüğünüzde aynı komutu tekrar tekrar.  
  
[!code-cpp[NVC_OLEDB_Consumer#2](../../data/oledb/codesnippet/cpp/ccommand-close_1.cpp)]  
  
## <a name="getnextresult"></a> CCommand::GetNextResult

Sonraki sonuç varsa kümesi getirir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT GetNextResult(DBROWCOUNT* pulRowsAffected, 
   bool bBind = true) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  

*pulRowsAffected*<br/>
[daraltma/genişletme] Burada bir komut tarafından etkilenen satır sayısı döndürülür bellek işaretçisi.  
  
*bBind*<br/>
[in] Komut yürütülen sonra otomatik olarak bağlamak belirtir. Varsayılan değer **true**, otomatik olarak bağlanacak komutu neden olur. Ayarı *bBind* için **false** böylece el ile bağlama komutu, otomatik bağlama engeller. (El ile OLAP kullanıcılara belirli ilgilenilen bağlamadır.)  
  
### <a name="return-value"></a>Dönüş Değeri  

Standart bir HRESULT.  
  
### <a name="remarks"></a>Açıklamalar  

Bir sonuç kümesi daha önce getirilen ise bu işlev, önceki sonuç kümesini serbest bırakır ve sütunları bağlantısını keser. Varsa *bBind* olduğu **true**, yeni sütunlar bağlar.  
  
Yalnızca birden çok sonuç ayarlayarak belirttiyseniz bu işlevi çağırmanız gerekir `CCommand` şablon parametresi *TMultiple*=`CMultipleResults`. 

## <a name="open"></a> CCommand::Open

Yürütür ve isteğe bağlı olarak komut bağlar.  
  
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

*Oturumu*<br/>
[in] Oturumda yürütüleceği komutu.  
  
*wszCommand*<br/>
[in] Komutu yürütmek için bir Unicode dize olarak geçirildi. Kullanırken NULL olabilir `CAccessor`, bu durumda komutu için geçirilen değer alınacağı konum [DEFINE_COMMAND](../../data/oledb/define-command.md) makrosu. Bkz: [ICommand::Execute](/previous-versions/windows/desktop/ms718095) içinde *OLE DB Programcının Başvurusu* Ayrıntılar için.  
  
*szCommand*<br/>
[in] Aynı *wszCommand* dışında bu parametre bir ANSI komut dizesi alır. Dördüncü formu bu yöntemin bir NULL değer alabilir. Ayrıntılar için bu konunun ilerleyen bölümlerindeki "Açıklamalar" bakın.  
  
*pPropSet*<br/>
[in] Bir dizi işaretçi [DBPROPSET](/previous-versions/windows/desktop/ms714367) özelliklerini ve değerlerini ayarlamak için içeren yapılar. Bkz: [özellik kümeleri ve özellik gruplarını](/previous-versions/windows/desktop/ms713696) içinde *OLE DB Programcının Başvurusu* Windows SDK içinde.  
  
*pRowsAffected*<br/>
[daraltma/genişletme] Burada bir komut tarafından etkilenen satır sayısı döndürülür bellek işaretçisi. Varsa  *\*pRowsAffected* NULL ise hiçbir satır sayısı döndürülür. Aksi takdirde, `Open` ayarlar  *\*pRowsAffected* aşağıdaki koşullara uygun:  
  
|Eğer|Ardından|  
|--------|----------|  
|`cParamSets` Öğesinin `pParams` 1'den daha büyük|*\*pRowsAffected* tüm yürütme belirtilen parametre kümeleri tarafından etkilenen satırların toplam sayısını temsil eder.|  
|Etkilenen satır sayısı kullanılamıyor|*\*pRowsAffected* -1 olarak ayarlanır.|  
|Komutu değil güncelleştirin, silin veya Satır Ekle|*\*pRowsAffected* tanımsızdır.|  
  
*guidCommand*<br/>
[in] Komut metni ayrıştırma söz dizimi ve genel kurallar için kullanılacak sağlayıcıyı belirtir bir GUID. Bkz: [ICommandText::GetCommandText](/previous-versions/windows/desktop/ms709825) ve [ICommandText::SetCommandText](/previous-versions/windows/desktop/ms709757) içinde *OLE DB Programcının Başvurusu* Ayrıntılar için.  
  
*bBind*<br/>
[in] Komut yürütülen sonra otomatik olarak bağlamak belirtir. Varsayılan değer **true**, otomatik olarak bağlanacak komutu neden olur. Ayarı *bBind* için **false** böylece el ile bağlama komutu, otomatik bağlama engeller. (El ile OLAP kullanıcılara belirli ilgilenilen bağlamadır.)  
  
*ulPropSets*<br/>
[in] Sayısını [DBPROPSET](/previous-versions/windows/desktop/ms714367) yapıları geçirilen *pPropSet* bağımsız değişken.  
  
### <a name="return-value"></a>Dönüş Değeri  

Standart bir HRESULT.  
  
### <a name="remarks"></a>Açıklamalar  

İlk üç tür `Open` oturumu olması, bir komut oluşturun ve gerektiği gibi herhangi bir parametre bağlama komutu yürütün.  
  
İlk formu `Open` Unicode komut dizesi alır ve varsayılan bir değeri yok.  
  
İkinci form, `Open` ANSI komut dizisi ve (ANSI mevcut uygulamalarla geriye dönük uyumluluk için sağlanır) varsayılan bir değer alır.  
  
Üçüncü biçiminde `Open` komut dizesi, NULL, türü nedeniyle olmasını sağlayan **int** varsayılan değeri null. Arama için sağlanan `Open(session, NULL);` veya `Open(session);` NULL türünde olduğu için **int**. Bu sürüm gerektirir ve bu onaylar **int** parametresi NULL olmalıdır.  
  
Dördüncü biçiminde kullanın `Open` ne zaman bir komut zaten oluşturduğunuz ve tek bir gerçekleştirmek istediğiniz [hazırlama](../../data/oledb/ccommand-prepare.md) ve birden çok yürütme.  
  
> [!NOTE]
>  `Open` çağrıları `Execute`, sırayla çağıran `GetNextResult`. 

## <a name="create"></a> CCommand::Create

Çağrıları [CCommand::CreateCommand](../../data/oledb/ccommand-createcommand.md) belirtilen oturum için bir komut oluşturmak için daha sonra çağırır [ICommandText::SetCommandText](/previous-versions/windows/desktop/ms709825) komut metni belirtmek için.  
  
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

*Oturumu*<br/>
[in] Komut oluşturulacağı hakkındaki oturumu.  
  
*wszCommand*<br/>
[in] Unicode dizesi metninin tamamının komutu için bir işaretçi.  
  
*szCommand*<br/>
[in] Komut dizesi, ANSI metin işaretçisi.  
  
*guidCommand*<br/>
[in] Komut metni ayrıştırma söz dizimi ve genel kurallar için kullanılacak sağlayıcıyı belirtir bir GUID. Diyalektler açıklaması için bkz: [ICommandText::GetCommandText](/previous-versions/windows/desktop/ms709825) içinde *OLE DB Programcının Başvurusu*.  
  
### <a name="return-value"></a>Dönüş Değeri  

Standart bir HRESULT.  
  
### <a name="remarks"></a>Açıklamalar  

İlk formu `Create` Unicode komut dizesi alır. İkinci form, `Create` (ANSI mevcut uygulamalarla geriye dönük uyumluluk için sağlanır) bir ANSI komut dizesi alır.

## <a name="createcommand"></a> CCommand::CreateCommand

Yeni bir komut oluşturur.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT CCommandBase::CreateCommand(const CSession& session) throw ();  
```  
  
#### <a name="parameters"></a>Parametreler  

*Oturumu*<br/>
[in] A `CSession` yeni komutu ile ilişkilendirilecek bir nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  

Standart bir HRESULT.  
  
### <a name="remarks"></a>Açıklamalar  

Bu yöntem, belirtilen oturum nesnesi kullanarak bir komut oluşturur.  

## <a name="getparameterinfo"></a> CCommand::getparameterınfo

Komut parametreleri, adlarını ve türlerini listesini alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT CCommandBase::GetParameterInfo(DB_UPARAMS* pParams,  
   DBPARAMINFO** ppParamInfo,  
   OLECHAR** ppNamesBuffer) throw ();  
```  
  
#### <a name="parameters"></a>Parametreler  

Bkz: [ICommandWithParameters::GetParameterInfo](/previous-versions/windows/desktop/ms714917) içinde *OLE DB Programcının Başvurusu*.  
  
### <a name="return-value"></a>Dönüş Değeri  

Standart bir HRESULT.   

## <a name="prepare"></a> CCommand::Prepare

Doğrular ve geçerli komutu en iyi duruma getirir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT CCommandBase::Prepare(ULONG cExpectedRuns = 0) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  

*cExpectedRuns*<br/>
[in] Komutu yürütmek için beklediğiniz sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  

Standart bir HRESULT.  
  
### <a name="remarks"></a>Açıklamalar  

Bu yöntem, OLE DB yöntemi sarmalar [ICommandPrepare::Prepare](/previous-versions/windows/desktop/ms718370).  

## <a name="releasecommand"></a> CCommand::ReleaseCommand

Parametre erişimci yayımlar ve ardından komut serbest bırakır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
void CCommandBase::ReleaseCommand() throw();  
```  
  
### <a name="remarks"></a>Açıklamalar  

`ReleaseCommand` ile birlikte kullanılan `Close`. Bkz: [Kapat](../../data/oledb/ccommand-close.md) kullanım ayrıntıları için. 

## <a name="setparameterinfo"></a> CCommand::SetParameterInfo

Her komut parametresi yerel türünü belirtir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT CCommandBase::SetParameterInfo(DB_UPARAMS ulParams,  
   const DBORDINAL* pOrdinals,  
   const DBPARAMBINDINFO* pParamInfo) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  

Bkz: [ICommandWithParameters::SetParameterInfo](/previous-versions/windows/desktop/ms725393) içinde *OLE DB Programcının Başvurusu*.  
  
### <a name="return-value"></a>Dönüş Değeri  

Standart bir HRESULT.  

## <a name="unprepare"></a> CCommand::Unprepare

Geçerli komut yürütme planını atar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT CCommandBase::Unprepare() throw();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  

Standart bir HRESULT.  
  
### <a name="remarks"></a>Açıklamalar  

Bu yöntem, OLE DB yöntemi sarmalar [ICommandPrepare::Unprepare](/previous-versions/windows/desktop/ms719635). 
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)