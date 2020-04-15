---
title: CrecentFileList Sınıfı
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
ms.openlocfilehash: a2102c6a39c14c548828e57ad1c49de6a5bc03dd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370902"
---
# <a name="crecentfilelist-class"></a>CrecentFileList Sınıfı

En son kullanılan (MRU) dosya listesinin denetimini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CRecentFileList
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CrecentFileList::CrecentFileList](#crecentfilelist)|Bir `CRecentFileList` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CRecentFileList::Ekle](#add)|MRU dosya listesine bir dosya ekler.|
|[CRecentFileList::GetDisplayName](#getdisplayname)|MRU dosya adının menü ekranı için bir görüntü adı sağlar.|
|[CRecentFileList::GetSize](#getsize)|MRU dosya listesindeki dosya sayısını alır.|
|[CRecentFileList::ReadList](#readlist)|MRU dosya listesini kayıt defterinden okur veya . INI dosyası.|
|[CRecentFileList::Kaldır](#remove)|MRU dosya listesinden bir dosya kaldırır.|
|[CRecentFileList::UpdateMenu](#updatemenu)|MRU dosya listesinin menü ekranını güncelleştirir.|
|[CRecentFileList::WriteList](#writelist)|MrU dosya listesini kayıt defterinden yazar veya . INI dosyası.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CRecentFileList::operatör \[\]](#operator_at)|Belirli `CString` bir konumda bir nesne döndürür.|

## <a name="remarks"></a>Açıklamalar

Dosyalar MRU dosya listesine eklenebilir veya silinebilir, dosya listesi kayıt defterinden okunabilir veya kayıt defterine yazılabilir. INI dosyası ve MRU dosya listesini görüntüleyen menü güncellenebilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CRecentFileList`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxadv.h

## <a name="crecentfilelistadd"></a><a name="add"></a>CRecentFileList::Ekle

En son kullanılan (MRU) dosya listesine bir dosya ekler.

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
Listeye eklenecek yol adını belirtir.

*lpszAppID*<br/>
Uygulama için Uygulama Kullanıcı Modeli Kimliğini belirtir.

*pItem*<br/>
Listeye eklenecek Shell Öğesi için bir işaretçi belirtir.

*pLink*<br/>
Listeye eklenecek Shell Bağlantısı işaretçisini belirtir.

*pidl*<br/>
Son dokümanlar klasörüne eklenmesi gereken kabuk öğesi için IDLIST'i belirtir.

### <a name="remarks"></a>Açıklamalar

Dosya adı MRU listesinin en üstüne eklenir. Dosya adı MRU listesinde zaten varsa, en üste taşınır.

## <a name="crecentfilelistcrecentfilelist"></a><a name="crecentfilelist"></a>CrecentFileList::CrecentFileList

Bir `CRecentFileList` nesne inşa eder.

```
CRecentFileList(
    UINT nStart,
    LPCTSTR lpszSection,
    LPCTSTR lpszEntryFormat,
    int nSize,
    int nMaxDispLen = AFX_ABBREV_FILENAME_LEN);
```

### <a name="parameters"></a>Parametreler

*nBaşlat*<br/>
MRU (en son kullanılan) dosya listesinin menü ekranındaki numaralandırma için ofset.

*lpszBölüm*<br/>
Kayıt defterinin veya uygulamanın bölümünün adına işaret eder. MRU dosya listesinin okunduğu ve/veya yazıldığı INI dosyası.

*lpszEntryFormat*<br/>
Kayıt defterinde veya uygulamanın adlarında kullanılacak biçim dizesini işaret eder. INI dosyası.

*nSize*<br/>
MRU dosya listesindeki maksimum dosya sayısı.

*nMaxDispLen*<br/>
MrU dosya listesindeki bir dosya adının menü görüntüsü için kullanılabilir karakterlerde maksimum uzunluk.

### <a name="remarks"></a>Açıklamalar

*lpszEntryFormat* tarafından işaret edilen biçim dizesi, her MRU öğesinin dizininin yerine kullanılacak "%d" içermelidir. Örneğin, biçim dizesi `"file%d"` ise, girişler `file0` `file1`,, ve benzeri adlanır.

## <a name="crecentfilelistgetdisplayname"></a><a name="getdisplayname"></a>CRecentFileList::GetDisplayName

MRU dosya listesindeki bir dosyanın görüntü adı, MRU listesinin menü ekranında kullanılmak üzere elde eder.

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
MrU dosyalarının menü listesinde adı görüntülenecek olan dosyanın tam yolu.

*Nındex*<br/>
MRU dosya listesindeki dosyanın sıfır tabanlı dizin.

*lpszCurDir*<br/>
Geçerli dizini tutan dize.

*nCurDir*<br/>
Geçerli dizin dizesinin uzunluğu.

*bAtLeastName*<br/>
Sıfır değilse, dosyanın temel adının, maksimum ekran uzunluğunu aşsa bile döndürülmesi gerektiğini gösterir `CRecentFileList` (oluşturucuya *nMaxDispLen* parametresi olarak geçirilir).

### <a name="return-value"></a>Dönüş Değeri

En son kullanılan (MRU) dosya listesinde belirtilen dizinte dosya adı yoksa **YANLIŞ.**

### <a name="remarks"></a>Açıklamalar

Dosya geçerli dizindeyse, işlev dizini ekrandan bırakır. Dosya adı çok uzunsa, dizin ve uzantı çıkarılır. Dosya adı hala çok uzunsa, *bAtLeastName* sıfır olmadığı sürece görüntü adı boş bir dize olarak ayarlanır.

## <a name="crecentfilelistgetsize"></a><a name="getsize"></a>CRecentFileList::GetSize

MRU dosya listesindeki dosya sayısını alır.

```
int GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli en son kullanılan (MRU) dosya listesindeki dosya sayısı.

## <a name="crecentfilelistoperator--"></a><a name="operator_at"></a>CRecentFileList::operator [ ]

Aşırı yüklenen alt`[]`yazı ( ) `CString` işleci *nIndex'te*sıfır tabanlı dizin tarafından belirtilen tek bir döndürür.

```
CString& operator[ ](int nindex);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
S kümesindeki bir `CString` indeksin sıfır tabanlı dizin. `CString`

## <a name="crecentfilelistreadlist"></a><a name="readlist"></a>CRecentFileList::ReadList

En son kullanılan (MRU) dosya listesini kayıt defterinden veya uygulamanın dosya listesini okur. INI dosyası.

```
virtual void ReadList();
```

## <a name="crecentfilelistremove"></a><a name="remove"></a>CRecentFileList::Kaldır

MRU dosya listesinden bir dosya kaldırır.

```
virtual void Remove(int nIndex);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
En son kullanılan (MRU) dosya listesinden kaldırılacak dosyanın sıfır tabanlı dizin.

## <a name="crecentfilelistupdatemenu"></a><a name="updatemenu"></a>CRecentFileList::UpdateMenu

MRU dosya listesinin menü ekranını güncelleştirir.

```
virtual void UpdateMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
En son kullanılan (MRU) dosya listesi menüsü için [CCmdUI](../../mfc/reference/ccmdui-class.md) nesnesine bir işaretçi.

## <a name="crecentfilelistwritelist"></a><a name="writelist"></a>CRecentFileList::WriteList

En son kullanılan (MRU) dosya listesini kayıt defterine veya uygulamanın . INI dosyası.

```
virtual void WriteList();
```

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
