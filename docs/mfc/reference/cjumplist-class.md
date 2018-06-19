---
title: CJumpList sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CJumpList
- AFXADV/CJumpList
- AFXADV/CJumpList::CJumpList
- AFXADV/CJumpList::AbortList
- AFXADV/CJumpList::AddDestination
- AFXADV/CJumpList::AddKnownCategory
- AFXADV/CJumpList::AddTask
- AFXADV/CJumpList::AddTasks
- AFXADV/CJumpList::AddTaskSeparator
- AFXADV/CJumpList::ClearAll
- AFXADV/CJumpList::ClearAllDestinations
- AFXADV/CJumpList::CommitList
- AFXADV/CJumpList::GetDestinationList
- AFXADV/CJumpList::GetMaxSlots
- AFXADV/CJumpList::GetRemovedItems
- AFXADV/CJumpList::InitializeList
- AFXADV/CJumpList::SetAppID
dev_langs:
- C++
helpviewer_keywords:
- CJumpList [MFC], CJumpList
- CJumpList [MFC], AbortList
- CJumpList [MFC], AddDestination
- CJumpList [MFC], AddKnownCategory
- CJumpList [MFC], AddTask
- CJumpList [MFC], AddTasks
- CJumpList [MFC], AddTaskSeparator
- CJumpList [MFC], ClearAll
- CJumpList [MFC], ClearAllDestinations
- CJumpList [MFC], CommitList
- CJumpList [MFC], GetDestinationList
- CJumpList [MFC], GetMaxSlots
- CJumpList [MFC], GetRemovedItems
- CJumpList [MFC], InitializeList
- CJumpList [MFC], SetAppID
ms.assetid: d364d27e-f512-4b12-9872-c2a17c78ab1f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d22fa264f48d3c5b1b6b88db338bc3be45c3f398
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369056"
---
# <a name="cjumplist-class"></a>CJumpList sınıfı
A `CJumpList` bir simgeyi görev çubuğunda sağ tıklattığınızda ortaya kısayolları listesidir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CJumpList;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CJumpList::CJumpList](#cjumplist)|Oluşturan bir `CJumpList` nesnesi.|  
|[CJumpList:: ~ CJumpList](#cjumplist__~cjumplist)|Bozar bir `CJumpList` nesnesi.|  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CJumpList::AbortList](#abortlist)|Bir liste oluşturma işlemi kaydetmeden durdurur.|  
|[CJumpList::AddDestination](#adddestination)|Fazla Yüklendi. Hedef listesine ekler.|  
|[CJumpList::AddKnownCategory](#addknowncategory)|Bilinen bir kategori listesine ekler.|  
|[CJumpList::AddTask](#addtask)|Fazla Yüklendi. Öğeleri kurallı Görevler kategorisi ekler.|  
|[CJumpList::AddTasks](#addtasks)|Öğeleri kurallı Görevler kategorisi ekler.|  
|[CJumpList::AddTaskSeparator](#addtaskseparator)|Görevler arasında ayırıcı ekler.|  
|[CJumpList::ClearAll](#clearall)|Tüm görevler ve geçerli örneğine eklenen hedefler kaldırır `CJumpList` kadarki.|  
|[CJumpList::ClearAllDestinations](#clearalldestinations)|Geçerli örneğine eklenen tüm hedefleri kaldırır `CJumpList` kadarki.|  
|[CJumpList::CommitList](#commitlist)|Bir liste oluşturma işlemi sonlandırır ve ilişkili depolama (Bu durumda kayıt.) bildirilen listesi kaydeder|  
|[CJumpList::GetDestinationList](#getdestinationlist)|Hedef listeye bir arabirim işaretçisi alır.|  
|[CJumpList::GetMaxSlots](#getmaxslots)|Öğeler, çağıran uygulamanın hedef menüde görüntüleyebilirsiniz kategori üstbilgileri dahil maksimum sayısını alır.|  
|[CJumpList::GetRemovedItems](#getremoveditems)|Temsil eden öğeleri dizisi döndürür hedefleri kaldırıldı.|  
|[CJumpList::InitializeList](#initializelist)|Bir liste oluşturma işlemi başlar.|  
|[CJumpList::SetAppID](#setappid)|Uygulama kullanıcısı Model kimliği oluşturulacak listesi ayarlar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CJumpList](../../mfc/reference/cjumplist-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxadv.h  
  
##  <a name="_dtorcjumplist"></a>  CJumpList:: ~ CJumpList  
 Bozar bir `CJumpList` nesnesi.  
  
```  
~CJumpList();
```  
  
##  <a name="abortlist"></a>  CJumpList::AbortList  
 Bir liste oluşturma işlemi kaydetmeden durdurur.  
  
```  
void AbortList();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemin çağrılması yok etme aynı etkiye sahip `CJumpList` çağırmadan `CommitList`.  
  
##  <a name="adddestination"></a>  CJumpList::AddDestination  
 Hedef listesine ekler.  
  
```  
BOOL AddDestination(
    LPCTSTR lpcszCategoryName,  
    LPCTSTR strDestinationPath);

 
BOOL AddDestination(
    LPCTSTR strCategoryName,  
    IShellItem* pShellItem);

 
BOOL AddDestination(
    LPCTSTR strCategoryName,  
    IShellLink* pShellLink);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpcszCategoryName`  
 Bir kategori adı belirtir. Belirtilen kategori mevcut değilse oluşturulur.  
  
 `strDestinationPath`  
 Hedef dosya yolunu belirtir.  
  
 `strCategoryName`  
 Bir kategori adı belirtir. Belirtilen kategori mevcut değilse oluşturulur.  
  
 `pShellItem`  
 Eklenmekte olan hedef temsil eden bir kabuk öğesi belirtir.  
  
 `pShellLink`  
 Eklenmekte olan hedef temsil eden bir kabuk bağlantı belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 Örneğinin `CJumpList` dahili olarak eklenen hedefler toplanır ve bunları tamamlar `CommitList`.  
  
##  <a name="addknowncategory"></a>  CJumpList::AddKnownCategory  
 Bilinen bir kategori listesine ekler.  
  
```  
BOOL AddKnownCategory(KNOWNDESTCATEGORY category);
```  
  
### <a name="parameters"></a>Parametreler  
 `category`  
 Bir bilinen kategori türünü belirtir. Ya da olabilir `KDC_RECENT`, veya `KDC_KNOWN`.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 Kategoriler biz kullanan her uygulama için otomatik olarak hesaplar sık ve son kategoriye ayrılır bilinen `SHAddToRecentDocs` (veya kabuk bazı senaryolarda uygulamanın adınıza çağıracak dolaylı kullanır).  
  
##  <a name="addtask"></a>  CJumpList::AddTask  
 Öğeleri kurallı Görevler kategorisi ekler.  
  
```  
BOOL AddTask(
    LPCTSTR strTargetExecutablePath,  
    LPCTSTR strCommandLineArgs,  
    LPCTSTR strTitle,  
    LPCTSTR strIconLocation,  
    int iIconIndex);  
  
BOOL AddTask(IShellLink* pShellLink);
```  
  
### <a name="parameters"></a>Parametreler  
 `strTargetExecutablePath`  
 Hedef görev yolunu belirtir.  
  
 `strCommandLineArgs`  
 StrTargetExecutablePath tarafından belirtilen yürütülebilir dosyanın komut satırı bağımsız değişkenlerini belirtir.  
  
 `strTitle`  
 Hedef liste görünümünde görüntülenen görev adı.  
  
 `strIconLocation`  
 Başlık birlikte hedef listesinde görüntülenen simge konumu.  
  
 `iIconIndex`  
 Simge dizini.  
  
 `pShellLink`  
 Eklenecek görevi temsil eden bir kabuk bağlantısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 Örneğinin `CJumpList` belirli görevleri toplanır ve bunları sırasında hedef listesine ekler `CommitList`. Görev öğeleri uygulamanın hedef menünün altındaki bir kategoride görüntülenir. Kullanıcı Arabiriminde dolduğunda bu kategoriyi diğer tüm kategorileri önceliklidir.  
  
##  <a name="addtasks"></a>  CJumpList::AddTasks  
 Öğeleri kurallı Görevler kategorisi ekler.  
  
```  
BOOL AddTasks(IObjectArray* pObjectCollection);
```  
  
### <a name="parameters"></a>Parametreler  
 `pObjectCollection`  
 Eklenecek görevleri koleksiyonu.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 CJumpList örneğini belirtilen görevleri toplanır ve bunları sırasında hedef listesine ekler `CommitList`. Görev öğeleri uygulamanın hedef menünün altındaki bir kategoride görüntülenir. Kullanıcı Arabiriminde dolduğunda bu kategoriyi diğer tüm kategorileri önceliklidir.  
  
##  <a name="addtaskseparator"></a>  CJumpList::AddTaskSeparator  
 Görevler arasında ayırıcı ekler.  
  
```  
BOOL AddTaskSeparator();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır değilse 0.  
  
##  <a name="cjumplist"></a>  CJumpList::CJumpList  
 Oluşturan bir `CJumpList` nesnesi.  
  
```  
CJumpList(BOOL bAutoCommit = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bAutoCommit`  
 Bu parametre FALSE ise listesi otomatik olarak yıkıcı uyguladığı geçerli değil.  
  
##  <a name="clearall"></a>  CJumpList::ClearAll  
 Tüm görevler ve geçerli örneğine eklenen hedefler kaldırır `CJumpList` kadarki.  
  
```  
void ClearAll();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem temizler ve tüm verileri ve iç arabirimleri serbest bırakır.  
  
##  <a name="clearalldestinations"></a>  CJumpList::ClearAllDestinations  
 CJumpList geçerli örneğine kadarki eklenmiş olan tüm hedefleri kaldırır.  
  
```  
void ClearAllDestinations();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şu ana kadar hedef listesi yapı geçerli oturumda eklenen ve diğer hedefleri tekrar ekleyin tüm hedefleri kaldırmanız gerekiyorsa bu işlevini çağırın. Varsa iç `ICustomDestinationList` bırakıldı başlatılan, Canlı bırakılır.  
  
##  <a name="commitlist"></a>  CJumpList::CommitList  
 Bir liste oluşturma işlemi sonlandırır ve ilişkili depolama (Bu durumda kayıt defteri) bildirilen listesi kaydeder.  
  
```  
BOOL CommitList();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 Yürütme atomik ' dir. Yürütme başarısız olursa bir hata döndürülür.  Zaman `CommitList` çağrılır, geçerli kaldırılan öğeler listesi temizlenecek. Böylece etkin bir liste oluşturma işlem yok, bu yöntemi çağırmadan nesne sıfırlar. Listesini güncelleştirmek için `BeginList` yeniden çağrılması gerekir.  
  
##  <a name="getdestinationlist"></a>  CJumpList::GetDestinationList  
 Hedef listeye bir arabirim işaretçisi alır.  
  
```  
ICustomDestinationList* GetDestinationList();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 Atlama listesi başlatılmadı, veya yürütüldüğü veya iptal edildi, döndürülen değer olacaktır `NULL`.  
  
##  <a name="getmaxslots"></a>  CJumpList::GetMaxSlots  
 Öğeler, çağıran uygulamanın hedef menüde görüntüleyebilirsiniz kategori üstbilgileri dahil maksimum sayısını alır.  
  
```  
UINT GetMaxSlots() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamalar, yalnızca bir öğe sayısını ve bu değeri kadar birlikte kategori üstbilgileri bildirebilir. Varsa çağrılar `AppendCategory`, `AppendKnownCategory`, veya `AddUserTasks` bu sınırı aşıyor, hata döndürür.  
  
##  <a name="getremoveditems"></a>  CJumpList::GetRemovedItems  
 Temsil eden öğeleri dizisi döndürür hedefleri kaldırıldı.  
  
```  
IObjectArray* GetRemovedItems();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 Kaldırılan hedefleri atlama listesi başlatma sırasında alınır. Yeni bir hedef listesi oluşturulurken uygulamaları ilk olarak kaldırılan listesi numaralandırıcı tarafından döndürülen herhangi bir öğe için izleme verilerini temizleyerek kaldırılan Hedefler listesini işleme beklenir. Bir uygulama için geçerli çağrısı işlemde yalnızca kaldırıldı bir öğe sağlamak çalışırsa `BeginList` başlatıldı, bu öğeyi yeniden eklendi yöntem çağrısı, uygulamaları kaldırılan listesi saygı göstermek emin olmak için başarısız olur.  
  
##  <a name="initializelist"></a>  CJumpList::InitializeList  
 Bir liste oluşturma işlemi başlar.  
  
```  
BOOL InitializeList();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 Açıkça bir işaretçi almak istediğiniz sürece bu yöntemi çağırmanız gerekmez `ICustomDestinationList` kullanarak `GetDestinationList`, kullanarak kullanılabilir yuva sayısı `GetMaxSlots`, veya kullanarak kaldırılan öğelerin listesini `GetRemovedItems`.  
  
##  <a name="setappid"></a>  CJumpList::SetAppID  
 Uygulama kullanıcısı Model kimliği oluşturulacak listesi ayarlar.  
  
```  
void SetAppID(LPCTSTR strAppID);
```  
  
### <a name="parameters"></a>Parametreler  
 `strAppID`  
 Uygulama kullanıcı Model kimliğini belirten bir dize  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
