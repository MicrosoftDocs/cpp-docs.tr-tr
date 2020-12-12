---
description: 'Daha fazla bilgi edinin: CRecentFileList sınıfı'
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
ms.openlocfilehash: 9433e65336cba1018c7bff8cf3a90e239ae5e3eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301132"
---
# <a name="crecentfilelist-class"></a>CRecentFileList sınıfı

En son kullanılan (MRU) dosya listesinin denetimini destekler.

## <a name="syntax"></a>Syntax

```
class CRecentFileList
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CRecentFileList:: CRecentFileList](#crecentfilelist)|Bir `CRecentFileList` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRecentFileList:: Add](#add)|MRU dosya listesine bir dosya ekler.|
|[CRecentFileList:: GetDisplayName](#getdisplayname)|MRU Dosya adının menü görüntülemesi için bir görünen ad sağlar.|
|[CRecentFileList:: GetSize](#getsize)|MRU dosya listesindeki dosya sayısını alır.|
|[CRecentFileList:: ReadList](#readlist)|Kayıt defterinden veya bir MRU dosya listesini okur. INı dosyası.|
|[CRecentFileList:: Remove](#remove)|MRU dosya listesinden bir dosyayı kaldırır.|
|[CRecentFileList:: UpdateMenu](#updatemenu)|MRU dosya listesinin menü görüntüsünü güncelleştirir.|
|[CRecentFileList:: WriteList](#writelist)|MRU dosya listesini kayıt defterinden veya konumundan yazar. INı dosyası.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CRecentFileList:: işleci \[\]](#operator_at)|`CString`Verilen konumdaki bir nesne döndürür.|

## <a name="remarks"></a>Açıklamalar

Dosyalar, MRU dosya listesine eklenebilir veya silinebilir, dosya listesi, kayıt defterinden veya bir ile okunabilir veya yazılabilir. INı dosyası ve MRU dosya listesini görüntüleyen menü de güncelleştirilemeyebilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CRecentFileList`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxadv. h

## <a name="crecentfilelistadd"></a><a name="add"></a> CRecentFileList:: Add

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
Uygulamanın uygulama kullanıcı modeli KIMLIĞINI belirtir.

*pItem*<br/>
Listeye eklenecek kabuk öğesine yönelik bir işaretçi belirtir.

*Plınk*<br/>
Listeye eklenecek bir kabuk bağlantısı işaretçisi belirtir.

*pidl*<br/>
Son Belgeler klasörüne eklenmesi gereken kabuk öğesi için ıDLIST öğesini belirtir.

### <a name="remarks"></a>Açıklamalar

Dosya adı MRU listesinin en üstüne eklenir. Dosya adı MRU listesinde zaten varsa, en üste taşınır.

## <a name="crecentfilelistcrecentfilelist"></a><a name="crecentfilelist"></a> CRecentFileList:: CRecentFileList

Bir `CRecentFileList` nesnesi oluşturur.

```
CRecentFileList(
    UINT nStart,
    LPCTSTR lpszSection,
    LPCTSTR lpszEntryFormat,
    int nSize,
    int nMaxDispLen = AFX_ABBREV_FILENAME_LEN);
```

### <a name="parameters"></a>Parametreler

*nBaşlangıç*<br/>
MRU (en son kullanılan) dosya listesinin menü görüntüsüne ait numaralandırmanın boşluğu.

*lpszSection*<br/>
Kayıt defterinin veya uygulamanın, bölümünün adını gösterir. MRU dosya listesinin okunduğu ve/veya yazıldığı INI dosyası.

*lpszEntryFormat*<br/>
Kayıt defterinde veya uygulamanın içinde depolanan girişlerin adları için kullanılacak bir biçim dizesine işaret eder. INı dosyası.

*nSize*<br/>
MRU dosya listesindeki en fazla dosya sayısı.

*nMaxDispLen*<br/>
MRU dosya listesindeki bir dosya adının menü görüntüsü için kullanılabilen uzunluk üst sınırı (karakter cinsinden).

### <a name="remarks"></a>Açıklamalar

*LpszEntryFormat* tarafından işaret edilen biçim dizesi, her MRU öğesinin dizinini değiştirme için kullanılacak "% d" içermelidir. Örneğin, biçim dizesi ise, girdiler, vb `"file%d"` . olarak adlandırılır `file0` `file1` .

## <a name="crecentfilelistgetdisplayname"></a><a name="getdisplayname"></a> CRecentFileList:: GetDisplayName

MRU listesinin menü görünümü içinde kullanılmak üzere MRU dosya listesindeki bir dosya için bir görünen ad alır.

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
Dosya adı, MRU dosyalarının menü listesinde görüntülenecek olan dosyanın tam yolu.

*nDizin*<br/>
MRU dosya listesindeki dosyanın sıfır tabanlı dizini.

*lpszCurDir*<br/>
Geçerli dizini tutan dize.

*nCurDir*<br/>
Geçerli dizin dizesinin uzunluğu.

*bAtLeastName*<br/>
Sıfır değilse, en büyük görüntüleme uzunluğunu (oluşturucuya *nMaxDispLen* parametresi olarak geçirilir) aşsa bile, dosyanın temel adının döndürülmesi gerektiğini gösterir `CRecentFileList` .

### <a name="return-value"></a>Dönüş Değeri

En son kullanılanlar (MRU) dosya listesinde belirtilen dizinde dosya adı yoksa **false** .

### <a name="remarks"></a>Açıklamalar

Dosya geçerli dizinde ise, işlev dizini ekranda bırakır. Dosya adı çok uzunsa dizin ve uzantı çıkarılır. Dosya adı hala çok uzunsa, *bAtLeastName* sıfır dışında bir değer olmadığı sürece görünen ad boş bir dizeye ayarlanır.

## <a name="crecentfilelistgetsize"></a><a name="getsize"></a> CRecentFileList:: GetSize

MRU dosya listesindeki dosya sayısını alır.

```
int GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli en son kullanılan (MRU) dosya listesindeki dosyaların sayısı.

## <a name="crecentfilelistoperator--"></a><a name="operator_at"></a> CRecentFileList:: operator []

Aşırı yüklenmiş alt simge ( `[]` ) Işleci `CString` *nindex* içindeki sıfır tabanlı dizin tarafından belirtilen tek döndürür.

```
CString& operator[ ](int nindex);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Bir kümesi içindeki bir öğesinin sıfır tabanlı dizini `CString` `CString` .

## <a name="crecentfilelistreadlist"></a><a name="readlist"></a> CRecentFileList:: ReadList

Kayıt defterinden veya uygulama tarafından kullanılan en son kullanılanlar (MRU) dosya listesini okur. INı dosyası.

```
virtual void ReadList();
```

## <a name="crecentfilelistremove"></a><a name="remove"></a> CRecentFileList:: Remove

MRU dosya listesinden bir dosyayı kaldırır.

```
virtual void Remove(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
En son kullanılanlar (MRU) dosya listesinden kaldırılacak dosyanın sıfır tabanlı dizini.

## <a name="crecentfilelistupdatemenu"></a><a name="updatemenu"></a> CRecentFileList:: UpdateMenu

MRU dosya listesinin menü görüntüsünü güncelleştirir.

```
virtual void UpdateMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
En son kullanılan (MRU) dosya listesi menüsü için [CCmdUI](../../mfc/reference/ccmdui-class.md) nesnesine yönelik bir işaretçi.

## <a name="crecentfilelistwritelist"></a><a name="writelist"></a> CRecentFileList:: WriteList

En son kullanılan (MRU) dosya listesini kayıt defterine veya uygulamanın öğesine yazar. INı dosyası.

```
virtual void WriteList();
```

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
