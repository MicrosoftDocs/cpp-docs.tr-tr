---
title: CRecentFileList sınıfı
ms.date: 11/04/2016
f1_keywords:
- CRecentFileList
- AFXADV/CRecentFileList
- AFXADV/CRecentFileList::CRecentFileList
- AFXADV/CRecentFileList::Add
- AFXADV/CRecentFileList::GetDisplayName
- AFXADV/CRecentFileList::GetSize
- AFXADV/CRecentFileList::ReadList
- AFXADV/CRecentFileList::Remove
- AFXADV/CRecentFileList::UpdateMenu
- AFXADV/CRecentFileList::WriteList
helpviewer_keywords:
- CRecentFileList [MFC], CRecentFileList
- CRecentFileList [MFC], Add
- CRecentFileList [MFC], GetDisplayName
- CRecentFileList [MFC], GetSize
- CRecentFileList [MFC], ReadList
- CRecentFileList [MFC], Remove
- CRecentFileList [MFC], UpdateMenu
- CRecentFileList [MFC], WriteList
ms.assetid: a77f0524-7584-4582-849a-7e97b76d186e
ms.openlocfilehash: 30536d91d057de4e551b5a28200dd903e12713b3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372185"
---
# <a name="crecentfilelist-class"></a>CRecentFileList sınıfı

En son kullanılan (MRU) dosya listesinin denetimini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CRecentFileList
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CRecentFileList::CRecentFileList](#crecentfilelist)|Oluşturur bir `CRecentFileList` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRecentFileList::Add](#add)|MRU dosya listesine bir dosya ekler.|
|[CRecentFileList::GetDisplayName](#getdisplayname)|Menü görüntüsü MRU filename için bir görünen ad sağlar.|
|[CRecentFileList::GetSize](#getsize)|MRU dosya listesindeki dosya sayısını alır.|
|[CRecentFileList::ReadList](#readlist)|MRU dosya listesi kayıt defterinden okuma veya. INI dosyası.|
|[CRecentFileList::Remove](#remove)|Bir dosya MRU dosyalar listesinden kaldırır.|
|[CRecentFileList::UpdateMenu](#updatemenu)|Menü görüntüsü MRU dosya listesini güncelleştirir.|
|[CRecentFileList::WriteList](#writelist)|MRU dosya listesi kayıt defterinden yazar veya. INI dosyası.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CRecentFileList::operator \[ \]](#operator_at)|Döndürür bir `CString` verilen konumda nesne.|

## <a name="remarks"></a>Açıklamalar

Dosya eklendiğinde veya MRU dosya listesinden silindikten, dosya listesi okuyamaz ya da kayıt defterine yazılır veya bir. INI dosyası ve MRU dosya listesi görüntüleme menüsü güncelleştirilebilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CRecentFileList`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxadv.h

##  <a name="add"></a>  CRecentFileList::Add

Bir dosyayı en son kullanılan (MRU) dosya listesine ekler.

```
virtual void Add(LPCTSTR lpszPathName);

virtual void Add(
    LPCTSTR lpszPathName,
    LPCTSTR lpszAppID);

void Add(
    IShellItem* pItem,
    LPCTSTR lpszAppID);

void Add(
    IShellLink* pLink,
    LPCTSTR lpszAppID);

void Add(
    PIDLIST_ABSOLUTE pidl,
    LPCTSTR lpszAppID);
```

### <a name="parameters"></a>Parametreler

*lpszPathName*<br/>
Listeye eklenecek yol belirtir.

*lpszAppID*<br/>
Uygulama kullanıcı modeli kimliği için uygulamayı belirtir.

*pItem*<br/>
Kabuk listeye eklenecek öğe işaretçisi belirtir.

*pLink*<br/>
Kabuk listeye eklenecek bağlantı için bir işaretçi belirtir.

*PIDL işaretçisiyle birlikte*<br/>
Yeni docs klasöre eklenen Kabuk öğe için IDLIST belirtir.

### <a name="remarks"></a>Açıklamalar

Dosya adı MRU Listesi üstüne eklenir. MRU listesindeki dosya adı zaten varsa, dosyanın en üstüne taşınır.

##  <a name="crecentfilelist"></a>  CRecentFileList::CRecentFileList

Oluşturur bir `CRecentFileList` nesne.

```
CRecentFileList(
    UINT nStart,
    LPCTSTR lpszSection,
    LPCTSTR lpszEntryFormat,
    int nSize,
    int nMaxDispLen = AFX_ABBREV_FILENAME_LEN);
```

### <a name="parameters"></a>Parametreler

*Nbaşlangıç*<br/>
MRU (en son kullanılan) dosya listesi menüsünde görüntülenen numaralandırma için uzaklık.

*lpszSection*<br/>
Kayıt defteri veya uygulamanın bölümünün noktaları adı. Burada MRU dosya listesini okuma yazılan ve/veya INI dosyası.

*lpszEntryFormat*<br/>
Kayıt defteri veya uygulamanın depolanan girişleri adları için kullanılan bir biçim dizesine işaret eder. INI dosyası.

*nSize*<br/>
MRU dosya listesindeki dosyaların sayısı.

*nMaxDispLen*<br/>
Kullanılabilir bir dosya adı MRU dosya listesinde menü görüntüsü için karakter cinsinden en büyük uzunluğu.

### <a name="remarks"></a>Açıklamalar

Biçim dizesi tarafından işaret edilen *lpszEntryFormat* "% her MRU öğenin dizinini değiştirme için kullanılacak d", içermelidir. Örneğin, biçim dizesi ise `"file%d"` girişleri adlı sonra `file0`, `file1`ve benzeri.

##  <a name="getdisplayname"></a>  CRecentFileList::GetDisplayName

MRU dosya listesini bir dosyada MRU Listesi menü görüntüsü kullanmak için bir görünen adı alır.

```
virtual BOOL GetDisplayName(
    CString& strName,
    int nIndex,
    LPCTSTR lpszCurDir,
    int nCurDir,
    BOOL bAtLeastName = TRUE) const;
```

### <a name="parameters"></a>Parametreler

*strName*<br/>
MRU Dosya menüsü listesinde gösterilecek adı olan dosyasının tam yolu.

*nIndex*<br/>
MRU dosya listesi dosyasında sıfır tabanlı dizini.

*lpszCurDir*<br/>
Geçerli dizin bulunduran dize.

*nCurDir*<br/>
Geçerli dizin dize uzunluğu.

*bAtLeastName*<br/>
Görünen maksimum uzunluğu aşıyor bile sıfır olmayan, dosyanın temel adı döndürülmesi gerektiğini, gösterir (olarak geçirilen *nMaxDispLen* parametresi `CRecentFileList` Oluşturucu).

### <a name="return-value"></a>Dönüş Değeri

**FALSE** varsa dosya adı belirtilen dizinden en son kullanılan (MRU) dosya listesinde.

### <a name="remarks"></a>Açıklamalar

Dosya geçerli dizinde ise, işlev dizini görüntülenmesini devre dışı bırakır. Dosya adı çok uzun, dizin ve uzantı kaldırılır. Dosya adı yine de çok uzunsa, görünen adı boş dize olarak sürece ayarlanır *bAtLeastName* sıfır değil.

##  <a name="getsize"></a>  CRecentFileList::GetSize

MRU dosya listesindeki dosya sayısını alır.

```
int GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dosya geçerli sayısı (MRU) dosya listesinin en son kullanılan.

##  <a name="operator_at"></a>  CRecentFileList::operator]

Aşırı yüklenmiş alt simge (`[]`) işleci, tek bir döndüren `CString` içindeki sıfır tabanlı dizin tarafından belirtilen *nIndex*.

```
CString& operator[ ](int nindex);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Sıfır tabanlı dizini bir `CString` kümesinde `CString`s.

##  <a name="readlist"></a>  CRecentFileList::ReadList

En son kullanılan (MRU) dosya listesi kayıt defterinden ya da uygulamanın okur. INI dosyası.

```
virtual void ReadList();
```

##  <a name="remove"></a>  CRecentFileList::Remove

Bir dosya MRU dosyalar listesinden kaldırır.

```
virtual void Remove(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Dosyanın en son kullanılan (MRU) dosya listeden kaldırılacak sıfır tabanlı dizini.

##  <a name="updatemenu"></a>  CRecentFileList::UpdateMenu

Menü görüntüsü MRU dosya listesini güncelleştirir.

```
virtual void UpdateMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
Bir işaretçi [Ccmduı](../../mfc/reference/ccmdui-class.md) en son kullanılan (MRU) dosya listesi menüsü nesnesi.

##  <a name="writelist"></a>  CRecentFileList::WriteList

En son kayıt ya da uygulamanın (MRU) dosya listesi kullanılan yazar. INI dosyası.

```
virtual void WriteList();
```

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
