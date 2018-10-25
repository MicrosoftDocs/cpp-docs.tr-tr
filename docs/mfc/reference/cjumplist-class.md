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
ms.openlocfilehash: 518712dd4d52673ad88dffc0ffa76c9e0281642a
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071881"
---
# <a name="cjumplist-class"></a>CJumpList sınıfı

A `CJumpList` görev çubuğundaki bir simgeyi sağ tıkladığınızda ortaya çıkan kısayolların listesi.

## <a name="syntax"></a>Sözdizimi

```
class CJumpList;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CJumpList::CJumpList](#cjumplist)|Oluşturur bir `CJumpList` nesne.|
|[CJumpList:: ~ CJumpList](#cjumplist__~cjumplist)|Yok eder bir `CJumpList` nesne.|

|Ad|Açıklama|
|----------|-----------------|
|[CJumpList::AbortList](#abortlist)|Taahhüt vermek zorunda kalmadan bir listesi oluşturma işlemi durdurur.|
|[CJumpList::AddDestination](#adddestination)|Fazla Yüklendi. Hedef listesine ekler.|
|[CJumpList::AddKnownCategory](#addknowncategory)|Bilinen bir kategori listesine ekler.|
|[CJumpList::AddTask](#addtask)|Fazla Yüklendi. Öğeleri kurallı görev kategorisine ekler.|
|[CJumpList::AddTasks](#addtasks)|Öğeleri kurallı görev kategorisine ekler.|
|[CJumpList::AddTaskSeparator](#addtaskseparator)|Görevler arasında bir ayırıcı ekler.|
|[CJumpList::ClearAll](#clearall)|Tüm görevleri ve geçerli örneğine eklenmiş olan hedefleri kaldırır `CJumpList` kadar.|
|[CJumpList::ClearAllDestinations](#clearalldestinations)|Geçerli örneğine eklenmiş olan tüm hedeflere kaldırır `CJumpList` kadar.|
|[CJumpList::CommitList](#commitlist)|Bir liste oluşturma işlemi sonlandırır ve ilişkili depolama (Bu durumda registry.) bildirilen listesi kaydeder|
|[CJumpList::GetDestinationList](#getdestinationlist)|Hedef listesine bir arabirim işaretçisi alır.|
|[CJumpList::GetMaxSlots](#getmaxslots)|Çağıran uygulamanın hedef menüde görüntüleyebilen kategorisi üst bilgiler dahil öğeleri, maksimum sayısını alır.|
|[CJumpList::GetRemovedItems](#getremoveditems)|Hedefleri temsil eden öğeleri dizisi döndürür kaldırıldı.|
|[CJumpList::InitializeList](#initializelist)|Bir liste oluşturma işlemi başlar.|
|[CJumpList::SetAppID](#setappid)|Uygulama kullanıcı modeli kimliği oluşturulur listenin için ayarlar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CJumpList](../../mfc/reference/cjumplist-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxadv.h

##  <a name="_dtorcjumplist"></a>  CJumpList:: ~ CJumpList

Yok eder bir `CJumpList` nesne.

```
~CJumpList();
```

##  <a name="abortlist"></a>  CJumpList::AbortList

Taahhüt vermek zorunda kalmadan bir listesi oluşturma işlemi durdurur.

```
void AbortList();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntemi çağırmadan, yok etme aynı etkiye sahip `CJumpList` çağırmadan `CommitList`.

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

*lpcszCategoryName*<br/>
Bir kategori adı belirtir. Belirtilen kategori mevcut değilse oluşturulur.

*strDestinationPath*<br/>
Hedef dosya yolunu belirtir.

*strCategoryName*<br/>
Bir kategori adı belirtir. Belirtilen kategori mevcut değilse oluşturulur.

*pShellItem*<br/>
Kabuk eklenen hedef temsil eden bir öğeyi belirtir.

*pShellLink*<br/>
Kabuk eklenen hedef temsil eden bir bağlantı belirtir.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Örneğini `CJumpList` dahili olarak eklenen hedefler birikir ve bunları tamamlar `CommitList`.

##  <a name="addknowncategory"></a>  CJumpList::AddKnownCategory

Bilinen bir kategori listesine ekler.

```
BOOL AddKnownCategory(KNOWNDESTCATEGORY category);
```

### <a name="parameters"></a>Parametreler

*Kategori*<br/>
Bilinen bir kategori türünü belirtir. KDC_RECENT veya KDC_KNOWN olabilir.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Kategorileri kategorilerinin biz kullanan her uygulama için otomatik olarak hesaplar sık sık yapılan ve son bilinen `SHAddToRecentDocs` (veya kabuk bazı senaryolarda uygulamanın adınıza çağıracak dolaylı olarak kullanır).

##  <a name="addtask"></a>  CJumpList::AddTask

Öğeleri kurallı görev kategorisine ekler.

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
StrTargetExecutablePath tarafından belirtilen yürütülebilir komut satırı bağımsız değişkenleri belirtir.

*strTitle*<br/>
Görev adı hedef listesinde görüntülenir.

*strIconLocation*<br/>
Başlığı ile birlikte hedef listesinde görüntülenecek simge konumu.

*iIconIndex*<br/>
Simge dizini.

*pShellLink*<br/>
Eklenecek bir görevi temsil eden shell bağlantısı.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Örneğini `CJumpList` belirli görevleri birikir ve bunları sırasında hedef listesine ekler `CommitList`. Görev öğeleri, uygulamanın hedef menüsüne sayfanın alt kısmında bir kategorideki görünür. Kullanıcı Arabiriminde dolduğunda bu kategorideki diğer tüm kategorileri önceliklidir.

##  <a name="addtasks"></a>  CJumpList::AddTasks

Öğeleri kurallı görev kategorisine ekler.

```
BOOL AddTasks(IObjectArray* pObjectCollection);
```

### <a name="parameters"></a>Parametreler

*pObjectCollection*<br/>
Eklenecek görevler koleksiyonudur.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

CJumpList örneğini belirtilen görevleri toplanır ve bunları sırasında hedef listesine ekler `CommitList`. Görev öğeleri, uygulamanın hedef menüsüne sayfanın alt kısmında bir kategorideki görünür. Kullanıcı Arabiriminde dolduğunda bu kategorideki diğer tüm kategorileri önceliklidir.

##  <a name="addtaskseparator"></a>  CJumpList::AddTaskSeparator

Görevler arasında bir ayırıcı ekler.

```
BOOL AddTaskSeparator();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır değilse 0.

##  <a name="cjumplist"></a>  CJumpList::CJumpList

Oluşturur bir `CJumpList` nesne.

```
CJumpList(BOOL bAutoCommit = TRUE);
```

### <a name="parameters"></a>Parametreler

*bAutoCommit*<br/>
Bu parametre FALSE ise listenin bir yıkıcı otomatik olarak edilmemiş.

##  <a name="clearall"></a>  CJumpList::ClearAll

Tüm görevleri ve geçerli örneğine eklenmiş olan hedefleri kaldırır `CJumpList` kadar.

```
void ClearAll();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, temizler ve tüm veri ve iç arabirimleri serbest bırakır.

##  <a name="clearalldestinations"></a>  CJumpList::ClearAllDestinations

Şu ana kadar CJumpList geçerli örneğine eklenmiş olan tüm hedeflere kaldırır.

```
void ClearAllDestinations();
```

### <a name="remarks"></a>Açıklamalar

Şu ana kadar hedef liste yapı geçerli oturumda eklendi ve başka hedeflere tekrar ekleyin tüm hedefleri kaldırmanız gerekirse, bu işlevi çağırın. İç `ICustomDestinationList` olmuştur başlatıldı, bu Canlı bırakılır.

##  <a name="commitlist"></a>  CJumpList::CommitList

Bir liste oluşturma işlemi sonlandırır ve ilişkili depolama (Bu örnekte kayıt defteri) bildirilen listesi kaydeder.

```
BOOL CommitList();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Atomik işlemesidir. Yürütme başarısız olursa, bir hata döndürülür.  Zaman `CommitList` çağrılır, geçerli kaldırılan öğeler listesi temizlenir. Bu yöntemi çağırmadan, böylece etkin bir liste yapı işlem yok, nesne sıfırlar. Listeyi güncelleştirmek için `BeginList` yeniden çağrılması gerekir.

##  <a name="getdestinationlist"></a>  CJumpList::GetDestinationList

Hedef listesine bir arabirim işaretçisi alır.

```
ICustomDestinationList* GetDestinationList();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Atlama listesi başlatılmadı, veya kaydedilmiş veya iptal edildi, döndürülen değer NULL olacaktır.

##  <a name="getmaxslots"></a>  CJumpList::GetMaxSlots

Çağıran uygulamanın hedef menüde görüntüleyebilen kategorisi üst bilgiler dahil öğeleri, maksimum sayısını alır.

```
UINT GetMaxSlots() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Uygulamaları yalnızca birkaç öğeleri ve bu değer kadar birleştirilmiş kategoride başlıklar bildirebilir. Varsa çağrılar `AppendCategory`, `AppendKnownCategory`, veya `AddUserTasks` bu taneyi, kullanıcılar hata döndürür.

##  <a name="getremoveditems"></a>  CJumpList::GetRemovedItems

Hedefleri temsil eden öğeleri dizisi döndürür kaldırıldı.

```
IObjectArray* GetRemovedItems();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Kaldırılan hedefleri atlama listesi başlatılması sırasında alınır. Yeni bir hedef liste oluştururken, uygulamaları kaldırılan listesi numaralandırıcısı tarafından döndürülen herhangi bir öğe için izleme verilerini temizleyerek kaldırılan hedefleri listesinde, ilk olarak işleme beklenir. Yalnızca geçerli çağrı işlem kaldırılan öğeyi sağlamak bir uygulama çalışırsa `BeginList` başlatıldı, bu öğeyi yeniden eklenen yöntemi çağrısı, uygulamaları kaldırılan listenin uyarak emin olmak için başarısız olur.

##  <a name="initializelist"></a>  CJumpList::InitializeList

Bir liste oluşturma işlemi başlar.

```
BOOL InitializeList();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Bir işaretçi almak istediğiniz sürece bu yöntemi açıkça çağırmanız gerekmez `ICustomDestinationList` kullanarak `GetDestinationList`, kullanarak kullanılabilir yuva sayısını `GetMaxSlots`, ya da kullanarak kaldırılan öğeler listesi `GetRemovedItems`.

##  <a name="setappid"></a>  CJumpList::SetAppID

Uygulama kullanıcı modeli kimliği oluşturulur listenin için ayarlar.

```
void SetAppID(LPCTSTR strAppID);
```

### <a name="parameters"></a>Parametreler

*strAppID*<br/>
Uygulama kullanıcı modeli kimliği belirten bir dize

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
