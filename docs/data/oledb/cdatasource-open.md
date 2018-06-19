---
title: CDataSource::Open | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CDataSource::Open
- ATL.CDataSource.Open
- CDataSource::Open
- CDataSource.Open
dev_langs:
- C++
helpviewer_keywords:
- Open method
ms.assetid: a6d28bd1-799a-48ed-8993-5f82d1705b77
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3196aa89426e895dd6b73b28ce197e8f271a0262
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33097074"
---
# <a name="cdatasourceopen"></a>CDataSource::Open
Kullanarak bir veri kaynağı için bir bağlantı açar bir **CLSID**, **ProgID**, veya `CEnumerator` ad veya bir Bulucu iletişim kutusu ile kullanıcıya sorar.  
  
## <a name="syntax"></a>Sözdizimi  
  
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
 `clsid`  
 [in] **CLSID** veri sağlayıcısı.  
  
 *pPropSet*  
 [in] Bir dizi için bir işaretçi [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) özellikleri ve ayarlanacak değerleri içeren yapıları. Bkz: [özellik kümeleri ve özellik grupları](https://msdn.microsoft.com/en-us/library/ms713696.aspx) içinde *OLE DB Programcının Başvurusu* Windows SDK.  
  
 *nPropertySets*  
 [in] Sayısı [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) yapıları geçirilen *pPropSet* bağımsız değişkeni.  
  
 *Sağlayıcı adı*  
 [in] Bağlantı kurmak için veritabanı adı.  
  
 *pUserName*  
 [in] Kullanıcı adı.  
  
 *pPassword*  
 [in] Kullanıcının parolası.  
  
 `nInitMode`  
 [in] Veritabanı başlatma modu. Bkz: [başlatma özellikleri](https://msdn.microsoft.com/en-us/library/ms723127.aspx)içinde *OLE DB Programcının Başvurusu* geçerli başlatma modlarının bir listesi için Windows SDK. Varsa `nInitMode` sıfır, hiçbir başlatma modu bağlantıyı açmak için kullanılan özellik kümesinde yer almaktadır.  
  
 `szProgID`  
 [in] Bir program tanımlayıcısı.  
  
 `enumerator`  
 [in] A [CEnumerator](../../data/oledb/cenumerator-class.md) arayan belirtmediği zaman bağlantıyı açmak için bir ad sağlamak için kullanılan nesne bir **CLSID**.  
  
 `hWnd`  
 [in] İletişim kutusunun üst olacak penceresine işleyin. Kullanan aşırı yüklenmiş işlevle kullanarak `hWnd` parametresi otomatik olarak hizmet bileşenleri çağırma; açıklamalar Ayrıntılar için bkz.  
  
 `dwPromptOptions`  
 [in] Bulucu iletişim kutusunu görüntülemek için stilini belirler. Olası değerler için msdasc.h bakın.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanan yöntemi aşırı yüklemesini `hWnd` parametresi oledb32.dll hizmet bileşenlerinde ile bir veri kaynağı nesnesi açılır; bu DLL kaynak havuzu, otomatik işlem kaydı gibi hizmet bileşenleri özellikleri uygulamasını içerir ve benzeri. Daha fazla bilgi için bkz: "OLE DB hizmetleri" OLE DB Programcı Başvurusu, [ http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true ](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
 Kullanmayın yöntemi aşırı `hWnd` parametresi oledb32.dll içinde hizmet bileşenlerini kullanmadan bir veri kaynağı nesnesi açın. A [CDataSource](../../data/oledb/cdatasource-class.md) bu işlev aşırı yüklemelerinin ile açılmış nesne bağlanamaz hizmet bileşenleri işlevlerden herhangi birini kullanma.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, Jet 4.0 veri kaynağına OLE DB Şablonları ile açmak gösterilmiştir. Jet veri kaynağı bir OLE DB veri kaynağı olarak kabul eder. Ancak, aramanız için **açık** iki özellik kümeleri gerekir: biri **DBPROPSET_DBINIT** ve diğer **DBPROPSET_JETOLEDB_DBINIT**, böylece ayarlayabileceğiniz  **DBPROP_JETOLEDB_DATABASEPASSWORD**.  
  
 [!code-cpp[NVC_OLEDB_Consumer#7](../../data/oledb/codesnippet/cpp/cdatasource-open_1.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDataSource Sınıfı](../../data/oledb/cdatasource-class.md)
