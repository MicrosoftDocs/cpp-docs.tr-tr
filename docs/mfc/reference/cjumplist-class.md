---
title: CJumplist Sınıfı
ms.date: 03/27/2019
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
ms.openlocfilehash: 98d6bec3d33c9060ebb741111dff793f64cc7cb0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372327"
---
# <a name="cjumplist-class"></a>CJumplist Sınıfı

A, `CJumpList` görev çubuğundaki bir simgeye sağ tıklattığınızda ortaya çıkan kısayolların listesidir.

## <a name="syntax"></a>Sözdizimi

```
class CJumpList;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CJumplist::CJumplist](#cjumplist)|Bir `CJumpList` nesne inşa eder.|
|[CJumplist::~CJumplist](#_dtorcjumplist)|Bir `CJumpList` nesneyi yok eder.|

|Adı|Açıklama|
|----------|-----------------|
|[CJumpList::AbortList](#abortlist)|İşlem yapmadan liste oluşturma işlemini iptal eder.|
|[CJumpList::AddDestination](#adddestination)|Fazla Yüklendi. Listeye hedef ekler.|
|[CJumplist::AddKnownCategory](#addknowncategory)|Listeye Bilinen Bir Kategori eklenir.|
|[CJumpList::AddTask](#addtask)|Fazla Yüklendi. Kanonik Görevler kategorisine öğeler ekler.|
|[CJumplist::Görevler Ekle](#addtasks)|Kanonik Görevler kategorisine öğeler ekler.|
|[CJumpList::AddTaskSeparator](#addtaskseparator)|Görevler arasında ayırıcı ekler.|
|[CJumplist::ClearAll](#clearall)|Şu ana `CJumpList` kadar geçerli örneğe eklenen tüm görevleri ve hedefleri kaldırır.|
|[CJumpList::ClearAllDestinations](#clearalldestinations)|Şu ana `CJumpList` kadar geçerli örneğin eklenmiştir tüm hedefleri kaldırır.|
|[CJumpList::CommitList](#commitlist)|Liste oluşturma işlemini sona erdirer ve bildirilen listeyi ilişkili mağazaya (bu durumda kayıt defteri) adatır.|
|[CJumpList::GetDestinationList](#getdestinationlist)|Hedef listesine bir arabirim işaretçisi alır.|
|[CJumpList::GetMaxSlots](#getmaxslots)|Arama uygulamasının hedef menüsünde görüntülenebilen kategori üstbilgisi de dahil olmak üzere en fazla öğe sayısını alır.|
|[CJumpList::GetRemovedItems](#getremoveditems)|Kaldırılan hedefleri temsil eden öğeler dizisini döndürür.|
|[CJumpList::InitializeList](#initializelist)|Liste oluşturma işlemi başlasın.|
|[CJumplist::SetAppID](#setappid)|Oluşturulacak liste için Uygulama Kullanıcı Modeli Kimliğini ayarlar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CJumplist](../../mfc/reference/cjumplist-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxadv.h

## <a name="cjumplistcjumplist"></a><a name="_dtorcjumplist"></a>CJumplist::~CJumplist

Bir `CJumpList` nesneyi yok eder.

```
~CJumpList();
```

## <a name="cjumplistabortlist"></a><a name="abortlist"></a>CJumpList::AbortList

İşlem yapmadan liste oluşturma işlemini iptal eder.

```
void AbortList();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntemi çağırmak, aramadan `CJumpList` `CommitList`yok etmekle aynı etkiye sahiptir.

## <a name="cjumplistadddestination"></a><a name="adddestination"></a>CJumpList::AddDestination

Listeye hedef ekler.

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

*lpcszCategoryName*<br/>
Bir kategori adı belirtir. Belirtilen kategori yoksa, oluşturulur.

*strDestinationPath*<br/>
Hedef dosyasına giden bir yol belirtir.

*strCategoryName*<br/>
Bir kategori adı belirtir. Belirtilen kategori yoksa, oluşturulur.

*pShellItem*<br/>
Eklenen hedefi temsil eden bir Shell Öğesi belirtir.

*pShellLink*<br/>
Eklenen hedefi temsil eden bir Shell Bağlantısı belirtir.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Dahili `CJumpList` olarak eklenen hedefleri birikir ve sonra `CommitList`bunları .

## <a name="cjumplistaddknowncategory"></a><a name="addknowncategory"></a>CJumplist::AddKnownCategory

Listeye Bilinen Bir Kategori eklenir.

```
BOOL AddKnownCategory(KNOWNDESTCATEGORY category);
```

### <a name="parameters"></a>Parametreler

*Kategori*<br/>
Bilinen bir kategori türünü belirtir. Ya KDC_RECENT, ya da KDC_KNOWN olabilir.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Bilinen Kategoriler, kullanan her uygulama için otomatik olarak hesaplayabileceğimiz Sık ve Son kategorilerdir `SHAddToRecentDocs` (veya dolaylı olarak kabuk bazı senaryolarda uygulama adına adlandıracağı şekilde kullanır).

## <a name="cjumplistaddtask"></a><a name="addtask"></a>CJumpList::AddTask

Kanonik Görevler kategorisine öğeler ekler.

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

*strTargetExecutablePath*<br/>
Hedef görev yolunu belirtir.

*strCommandLineArgs*<br/>
*strTargetExecutablePath*tarafından belirtilen yürütülebilir komut satırı bağımsız değişkenlerini belirtir.

*strTitle*<br/>
Hedef Listesinde görüntülenecek görev adı.

*strIconLocation*<br/>
Başlıkla birlikte Hedef Liste'de görüntülenecek simgenin konumu.

*iIconIndex*<br/>
Simge dizini.

*pShellLink*<br/>
Eklenecek bir görevi temsil eden Shell Bağlantısı.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Örneğin, `CJumpList` belirtilen görevleri birikir ve bu görevleri `CommitList`hedef listesine ekler. Görev öğeleri, uygulamanın hedef menüsünün alt kısmındaki bir kategoride görünür. Bu kategori, UI'da doldurulduğunda diğer tüm kategorilerden önce gelir.

## <a name="cjumplistaddtasks"></a><a name="addtasks"></a>CJumplist::Görevler Ekle

Kanonik Görevler kategorisine öğeler ekler.

```
BOOL AddTasks(IObjectArray* pObjectCollection);
```

### <a name="parameters"></a>Parametreler

*pObjectCollection*<br/>
Eklenecek görevler topluluğu.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

CJumpList örneği belirtilen görevleri birikir ve `CommitList`sırasında Hedef Listesine ekler. Görev öğeleri, uygulamanın hedef menüsünün alt kısmındaki bir kategoride görünür. Bu kategori, UI'da doldurulduğunda diğer tüm kategorilerden önce gelir.

## <a name="cjumplistaddtaskseparator"></a><a name="addtaskseparator"></a>CJumpList::AddTaskSeparator

Görevler arasında ayırıcı ekler.

```
BOOL AddTaskSeparator();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız başarılı ise, 0 değilse.

## <a name="cjumplistcjumplist"></a><a name="cjumplist"></a>CJumplist::CJumplist

Bir `CJumpList` nesne inşa eder.

```
CJumpList(BOOL bAutoCommit = TRUE);
```

### <a name="parameters"></a>Parametreler

*bAutoCommit*<br/>
Bu parametre FALSE ise liste otomatik olarak yıkıcı olarak işlenmez.

## <a name="cjumplistclearall"></a><a name="clearall"></a>CJumplist::ClearAll

Şu ana `CJumpList` kadar geçerli örneğe eklenen tüm görevleri ve hedefleri kaldırır.

```
void ClearAll();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, tüm verileri ve dahili arabirimleri temizler ve yayımlar.

## <a name="cjumplistclearalldestinations"></a><a name="clearalldestinations"></a>CJumpList::ClearAllDestinations

Şu ana kadar Geçerli CJumpList örneğine eklenen tüm hedefleri kaldırır.

```
void ClearAllDestinations();
```

### <a name="remarks"></a>Açıklamalar

Hedef listesi oluşturmanın geçerli oturumunda şimdiye kadar eklenen tüm hedefleri kaldırmanız ve diğer hedefleri yeniden eklemeniz gerekiyorsa bu işlevi arayın. Eğer iç `ICustomDestinationList` harf eki verilmiştir, canlı bırakılmış.

## <a name="cjumplistcommitlist"></a><a name="commitlist"></a>CJumpList::CommitList

Liste oluşturma işlemini sona erdirer ve bildirilen listeyi ilişkili mağazaya (bu durumda kayıt defteri) adar.

```
BOOL CommitList();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Taahhüt atomiktir. Commit başarısız olursa bir hata döndürülür.  Çağrıldığında, `CommitList` kaldırılan öğelerin geçerli listesi temizlenir. Bu yöntemi çağırmak, etkin bir liste oluşturma hareketi olmayacak şekilde nesneyi sıfırlar. Listeyi güncelleştirmek `BeginList` için yeniden çağrılması gerekir.

## <a name="cjumplistgetdestinationlist"></a><a name="getdestinationlist"></a>CJumpList::GetDestinationList

Hedef listesine bir arabirim işaretçisi alır.

```
ICustomDestinationList* GetDestinationList();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Atlama listesi başharflere döndürülmediyse veya işlenmiş veya iptal edilmişse, döndürülen değer NULL olur.

## <a name="cjumplistgetmaxslots"></a><a name="getmaxslots"></a>CJumpList::GetMaxSlots

Arama uygulamasının hedef menüsünde görüntülenebilen kategori üstbilgisi de dahil olmak üzere en fazla öğe sayısını alır.

```
UINT GetMaxSlots() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Uygulamalar yalnızca bu değere kadar birleştirilmiş birkaç öğe ve kategori üstbilgiraporlayabilir. Bu numarayı `AppendCategory` `AppendKnownCategory`ararsa veya `AddUserTasks` bu numarayı aşarsa, hatadöndürer.

## <a name="cjumplistgetremoveditems"></a><a name="getremoveditems"></a>CJumpList::GetRemovedItems

Kaldırılan hedefleri temsil eden öğeler dizisini döndürür.

```
IObjectArray* GetRemovedItems();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Kaldırılan hedefler atlama listesinin başlatılması sırasında alınır. Yeni bir hedef listesi oluştururken, uygulamaların ilk olarak kaldırılan hedef listesinin işlenmesi ve kaldırılan liste numarası tarafından döndürülen herhangi bir öğe için izleme verilerini temizlemesi beklenir. Bir uygulama, geçerli aramanın `BeginList` başlatıldıkı harekette yeni kaldırılan bir öğeyi sağlamaya çalışırsa, uygulamaların kaldırılan listeye saygı duyduğundan emin olmak için maddeyi yeniden eklenen yöntem başarısız olur.

## <a name="cjumplistinitializelist"></a><a name="initializelist"></a>CJumpList::InitializeList

Liste oluşturma işlemi başlasın.

```
BOOL InitializeList();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Kullanmak `ICustomDestinationList` için bir işaretçi almak istemiyorsanız bu yöntemi açıkça `GetDestinationList`aramanız gerekmez , kullanarak `GetMaxSlots`kullanılabilir yuva sayısı `GetRemovedItems`, ya da kullanarak kaldırılan öğelerin listesini .

## <a name="cjumplistsetappid"></a><a name="setappid"></a>CJumplist::SetAppID

Oluşturulacak liste için Uygulama Kullanıcı Modeli Kimliğini ayarlar.

```
void SetAppID(LPCTSTR strAppID);
```

### <a name="parameters"></a>Parametreler

*strAppID*<br/>
Uygulama Kullanıcı Modeli Kimliğini belirten bir dize.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
