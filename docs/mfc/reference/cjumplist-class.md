---
description: 'Daha fazla bilgi edinin: CJumpList sınıfı'
title: CJumpList sınıfı
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
ms.openlocfilehash: 07e896c5b3a205a44850d45dcc4876103a48f2fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236912"
---
# <a name="cjumplist-class"></a>CJumpList sınıfı

, `CJumpList` Görev çubuğundaki bir simgeye sağ tıkladığınızda ortaya çıkan kısayolların listesidir.

## <a name="syntax"></a>Syntax

```
class CJumpList;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CJumpList:: CJumpList](#cjumplist)|Bir `CJumpList` nesnesi oluşturur.|
|[CJumpList:: ~ CJumpList](#_dtorcjumplist)|Bir nesneyi yok eder `CJumpList` .|

|Ad|Açıklama|
|----------|-----------------|
|[CJumpList:: AbortList](#abortlist)|Bir liste oluşturma işlemini kaydetmeden iptal eder.|
|[CJumpList:: AddDestination](#adddestination)|Fazla Yüklendi. Listeye hedef ekler.|
|[CJumpList:: AddKnownCategory](#addknowncategory)|Bilinen bir kategoriyi listeye ekler.|
|[CJumpList:: AddTask](#addtask)|Fazla Yüklendi. Kurallı görevler kategorisine öğe ekler.|
|[CJumpList:: AddTasks](#addtasks)|Kurallı görevler kategorisine öğe ekler.|
|[CJumpList:: AddTaskSeparator](#addtaskseparator)|Görevler arasına bir ayırıcı ekler.|
|[CJumpList:: ClearAll](#clearall)|Şimdiye kadar geçerli örneğine eklenmiş tüm görevleri ve hedefleri kaldırır `CJumpList` .|
|[CJumpList:: ClearAllDestinations](#clearalldestinations)|Şimdiye kadar geçerli örneğine eklenmiş olan tüm hedefleri kaldırır `CJumpList` .|
|[CJumpList:: CommitList](#commitlist)|Liste oluşturma işlemini sonlandırır ve bildirilen listeyi ilişkili depoya (Bu durumda kayıt defteri) kaydeder.|
|[CJumpList:: GetDestinationList](#getdestinationlist)|Hedef listeye bir arabirim işaretçisi alır.|
|[CJumpList:: Getmaxyuvaları](#getmaxslots)|Çağıran uygulamanın hedef menüsünde görüntülenebilecek kategori üstbilgileri dahil olmak üzere en fazla öğe sayısını alır.|
|[CJumpList:: GetRemovedItems](#getremoveditems)|Kaldırılan hedefleri temsil eden öğelerin dizisini döndürür.|
|[CJumpList:: ınitializelist](#initializelist)|Bir liste oluşturma işlemi başlatır.|
|[CJumpList:: Setappıd](#setappid)|Oluşturulacak listenin uygulama kullanıcı modeli KIMLIĞINI ayarlar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CJumpList](../../mfc/reference/cjumplist-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxadv. h

## <a name="cjumplistcjumplist"></a><a name="_dtorcjumplist"></a> CJumpList:: ~ CJumpList

Bir nesneyi yok eder `CJumpList` .

```
~CJumpList();
```

## <a name="cjumplistabortlist"></a><a name="abortlist"></a> CJumpList:: AbortList

Bir liste oluşturma işlemini kaydetmeden iptal eder.

```cpp
void AbortList();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntemin çağrılması, çağrı yapılmadan yok etme ile aynı etkiye sahiptir `CJumpList` `CommitList` .

## <a name="cjumplistadddestination"></a><a name="adddestination"></a> CJumpList:: AddDestination

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
Hedef dosyanın yolunu belirtir.

*strCategoryName*<br/>
Bir kategori adı belirtir. Belirtilen kategori yoksa, oluşturulur.

*Pshellıtıtem*<br/>
Eklenmekte olan hedefi temsil eden bir kabuk öğesi belirtir.

*pShellLink*<br/>
Eklenmekte olan hedefi temsil eden bir kabuk bağlantısı belirtir.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

`CJumpList`Dahili olarak eklenen hedefleri birikir ve sonra içinde kaydeder `CommitList` .

## <a name="cjumplistaddknowncategory"></a><a name="addknowncategory"></a> CJumpList:: AddKnownCategory

Bilinen bir kategoriyi listeye ekler.

```
BOOL AddKnownCategory(KNOWNDESTCATEGORY category);
```

### <a name="parameters"></a>Parametreler

*alan*<br/>
Bilinen bir kategori türünü belirtir. KDC_RECENT ya da KDC_KNOWN olabilir.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Bilinen Kategoriler, (veya dolaylı olarak onu kullanan) her uygulama için otomatik olarak hesaplanacak olan sık ve son kategorileridir. Bu, `SHAddToRecentDocs` kabuk uygulamayı bazı senaryolarda uygulamanın adına çağıracaktır.

## <a name="cjumplistaddtask"></a><a name="addtask"></a> CJumpList:: AddTask

Kurallı görevler kategorisine öğe ekler.

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

*Strcommanddoğrgs*<br/>
*StrTargetExecutablePath* tarafından belirtilen yürütülebilir dosyanın komut satırı bağımsız değişkenlerini belirtir.

*strTitle*<br/>
Hedef listesinde görüntülenecek olan görev adı.

*strIconLocation*<br/>
Hedef listede başlıkla birlikte görüntülenecek simgenin konumu.

*ıiconındex*<br/>
Simge dizini.

*pShellLink*<br/>
Eklenecek bir görevi temsil eden kabuk bağlantısı.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

`CJumpList`Belirtilen görevleri birikir örneği ve bunları sırasında hedef listeye ekler `CommitList` . Görev öğeleri, uygulamanın hedef menüsünün alt kısmındaki bir kategoride görüntülenir. Bu kategori, kullanıcı arabiriminden doldurulduğu zaman diğer tüm kategorilere göre önceliklidir.

## <a name="cjumplistaddtasks"></a><a name="addtasks"></a> CJumpList:: AddTasks

Kurallı görevler kategorisine öğe ekler.

```
BOOL AddTasks(IObjectArray* pObjectCollection);
```

### <a name="parameters"></a>Parametreler

*pObjectCollection*<br/>
Eklenecek görevler koleksiyonu.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

CJumpList örneği belirtilen görevleri toplar ve sırasında hedef listesine ekler `CommitList` . Görev öğeleri, uygulamanın hedef menüsünün alt kısmındaki bir kategoride görüntülenir. Bu kategori, kullanıcı arabiriminden doldurulduğu zaman diğer tüm kategorilere göre önceliklidir.

## <a name="cjumplistaddtaskseparator"></a><a name="addtaskseparator"></a> CJumpList:: AddTaskSeparator

Görevler arasına bir ayırıcı ekler.

```
BOOL AddTaskSeparator();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı, değilse 0.

## <a name="cjumplistcjumplist"></a><a name="cjumplist"></a> CJumpList:: CJumpList

Bir `CJumpList` nesnesi oluşturur.

```
CJumpList(BOOL bAutoCommit = TRUE);
```

### <a name="parameters"></a>Parametreler

*Bautocommıt*<br/>
Bu parametre YANLıŞSA, liste yıkıcıya otomatik olarak yürütülmedi.

## <a name="cjumplistclearall"></a><a name="clearall"></a> CJumpList:: ClearAll

Şimdiye kadar geçerli örneğine eklenmiş tüm görevleri ve hedefleri kaldırır `CJumpList` .

```cpp
void ClearAll();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem tüm verileri ve iç arabirimleri temizler ve serbest bırakır.

## <a name="cjumplistclearalldestinations"></a><a name="clearalldestinations"></a> CJumpList:: ClearAllDestinations

Şu ana kadar geçerli CJumpList örneğine eklenmiş olan tüm hedefleri kaldırır.

```cpp
void ClearAllDestinations();
```

### <a name="remarks"></a>Açıklamalar

Hedef liste binasının geçerli oturumunda şimdiye kadar eklenmiş olan tüm hedefleri kaldırmanız ve diğer hedefleri yeniden eklemeniz gerekiyorsa bu işlevi çağırın. İç `ICustomDestinationList` başlatılmışsa, etkin kalır.

## <a name="cjumplistcommitlist"></a><a name="commitlist"></a> CJumpList:: CommitList

Liste oluşturma işlemini sonlandırır ve bildirilen listeyi ilişkili depoya (Bu durumda kayıt defteri) kaydeder.

```
BOOL CommitList();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Tamamlama atomik. İşlem başarısız olursa bir hata döndürülür.  `CommitList`Çağrıldığında, kaldırılan öğelerin geçerli listesi temizlenir. Bu yöntemi çağırmak nesneyi, etkin bir liste oluşturma işlemi olmaması için sıfırlar. Listeyi güncelleştirmek için `BeginList` yeniden çağrılması gerekir.

## <a name="cjumplistgetdestinationlist"></a><a name="getdestinationlist"></a> CJumpList:: GetDestinationList

Hedef listeye bir arabirim işaretçisi alır.

```
ICustomDestinationList* GetDestinationList();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Sıçrama listesi başlatılmamış veya kaydedilmiş veya durdurulmuş ise, döndürülen değer NULL olur.

## <a name="cjumplistgetmaxslots"></a><a name="getmaxslots"></a> CJumpList:: Getmaxyuvaları

Çağıran uygulamanın hedef menüsünde görüntülenebilecek kategori üstbilgileri dahil olmak üzere en fazla öğe sayısını alır.

```
UINT GetMaxSlots() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Uygulamalar, bu değere kadar Birleşik sayıda öğe ve Kategori üst bilgisi bildirebilir. `AppendCategory`, `AppendKnownCategory` Veya `AddUserTasks` Bu sayıyı aşarsa, hata döndürür.

## <a name="cjumplistgetremoveditems"></a><a name="getremoveditems"></a> CJumpList:: GetRemovedItems

Kaldırılan hedefleri temsil eden öğelerin dizisini döndürür.

```
IObjectArray* GetRemovedItems();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Kaldırılan hedefler, sıçrama listesinin başlatılması sırasında alınır. Yeni bir hedef listesi oluştururken, uygulamaların kaldırılan hedefler listesini işlemesi beklenir ve bu, kaldırılan liste numaralandırıcısı tarafından döndürülen herhangi bir öğe için izleme verilerini temizlemektir. Bir uygulama, geçerli çağrının başladığı işlemde yeni kaldırılan bir öğe sağlamaya çalışırsa `BeginList` , uygulamaların kaldırılan listeyi yeniden sağlamasını sağlamak için bu öğeyi yeniden ekleyen Yöntem çağrısı başarısız olur.

## <a name="cjumplistinitializelist"></a><a name="initializelist"></a> CJumpList:: ınitializelist

Bir liste oluşturma işlemi başlatır.

```
BOOL InitializeList();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Kullanmak için bir işaretçi `ICustomDestinationList` `GetDestinationList` , kullanan kullanılabilir yuva sayısı `GetMaxSlots` veya kullanılarak kaldırılan öğelerin listesini almak istemediğiniz müddetçe bu yöntemi açıkça çağırmanız gerekmez `GetRemovedItems` .

## <a name="cjumplistsetappid"></a><a name="setappid"></a> CJumpList:: Setappıd

Oluşturulacak listenin uygulama kullanıcı modeli KIMLIĞINI ayarlar.

```cpp
void SetAppID(LPCTSTR strAppID);
```

### <a name="parameters"></a>Parametreler

*Strappıd*<br/>
Uygulamanın kullanıcı modeli KIMLIĞINI belirten bir dize.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
