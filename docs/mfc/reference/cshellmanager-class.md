---
title: CShellManager Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CShellManager
- AFXSHELLMANAGER/CShellManager
- AFXSHELLMANAGER/CShellManager::CShellManager
- AFXSHELLMANAGER/CShellManager::BrowseForFolder
- AFXSHELLMANAGER/CShellManager::ConcatenateItem
- AFXSHELLMANAGER/CShellManager::CopyItem
- AFXSHELLMANAGER/CShellManager::CreateItem
- AFXSHELLMANAGER/CShellManager::FreeItem
- AFXSHELLMANAGER/CShellManager::GetItemCount
- AFXSHELLMANAGER/CShellManager::GetItemSize
- AFXSHELLMANAGER/CShellManager::GetNextItem
- AFXSHELLMANAGER/CShellManager::GetParentItem
- AFXSHELLMANAGER/CShellManager::ItemFromPath
helpviewer_keywords:
- CShellManager [MFC], CShellManager
- CShellManager [MFC], BrowseForFolder
- CShellManager [MFC], ConcatenateItem
- CShellManager [MFC], CopyItem
- CShellManager [MFC], CreateItem
- CShellManager [MFC], FreeItem
- CShellManager [MFC], GetItemCount
- CShellManager [MFC], GetItemSize
- CShellManager [MFC], GetNextItem
- CShellManager [MFC], GetParentItem
- CShellManager [MFC], ItemFromPath
ms.assetid: f15c4c1a-6fae-487d-9913-9b7369b33da0
ms.openlocfilehash: 1c2f9ac1658f50f0ec5bd9e2f53d270c09bfcb6a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750329"
---
# <a name="cshellmanager-class"></a>CShellManager Sınıfı

Tanımlayıcı listeleri (PIDLs) işaretçileri ile çalışmanızı sağlayan çeşitli yöntemler uygular.

## <a name="syntax"></a>Sözdizimi

```
class CShellManager : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CShellManager::CShellManager](#cshellmanager)|Bir `CShellManager` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CShellManager::GözatForFolder](#browseforfolder)|Kullanıcının bir kabuk klasörü seçmesini sağlayan bir iletişim kutusu görüntüler.|
|[CShellManager::ConcatenateItem](#concatenateitem)|İki PIDL'i birleştirir.|
|[CShellManager::CopyItem](#copyitem)|Yeni bir PIDL oluşturur ve verilen PIDL'yi kopyalar.|
|[CShellManager::CreateItem](#createitem)|Belirtilen boyutta yeni bir PIDL oluşturur.|
|[CShellManager::FreeItem](#freeitem)|Sağlanan PIDL'yi siler.|
|[CShellManager::GetItemCount](#getitemcount)|Verilen PIDL'deki madde sayısını verir.|
|[CShellManager::GetItemSize](#getitemsize)|Verilen PIDL boyutunu döndürür.|
|[CShellManager::GetNextItem](#getnextitem)|PIDL'den sonraki öğeyi döndürür.|
|[CShellManager::GetParentItem](#getparentitem)|Sağlanan öğenin üst öğesini alır.|
|[CShellManager::ItemFromPath](#itemfrompath)|Verilen yol tarafından tanımlanan öğe için PIDL'yi alır.|

## <a name="remarks"></a>Açıklamalar

`CShellManager` Sınıfın tüm yöntemleri PIDLs ile ilgili. PIDL, kabuk nesnesi için benzersiz bir tanımlayıcıdır.

Bir `CShellManager` nesneyi el ile oluşturmamalısınız. Uygulamanızın çerçevesi tarafından otomatik olarak oluşturulur. Ancak, uygulamanızın başlatma işlemi sırasında [CWinAppEx::InitShellManager'ı](../../mfc/reference/cwinappex-class.md#initshellmanager) aramalısınız. Uygulamanız için shell yöneticisine bir işaretçi almak için [CWinAppEx::GetShellManager'ı](../../mfc/reference/cwinappex-class.md#getshellmanager)arayın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cshellmanager](../../mfc/reference/cshellmanager-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxshellmanager.h

## <a name="cshellmanagerbrowseforfolder"></a><a name="browseforfolder"></a>CShellManager::GözatForFolder

Kullanıcının bir kabuk klasörü seçmesini sağlayan bir iletişim kutusu görüntüler.

```
BOOL BrowseForFolder(
    CString& strOutFolder,
    CWnd* pWndParent = NULL,
    LPCTSTR lplszInitialFolder = NULL,
    LPCTSTR lpszTitle = NULL,
    UINT ulFlags = BIF_RETURNONLYFSDIRS,
    LPINT piFolderImage = NULL);
```

### <a name="parameters"></a>Parametreler

*strOutFolder*<br/>
[çıkış] Seçili klasörün yolunu depolamak için yöntem tarafından kullanılan dize.

*pWndParent*<br/>
[içinde] Üst pencereiçin bir işaretçi.

*lplszInitialKlasör*<br/>
[içinde] İletişim kutusu görüntülendiğinde varsayılan olarak seçilen klasörü içeren dize.

*lpszTitle*<br/>
[içinde] İletişim kutusunun başlığı.

*ulFlags*<br/>
[içinde] İletişim kutusu için seçenekleri belirten bayraklar. Ayrıntılı açıklama için [BROWSEINFO'ya](/windows/win32/api/shlobj_core/ns-shlobj_core-browseinfow) bakın.

*piFolderImage*<br/>
[çıkış] Yöntemin seçili klasörün görüntü dizini yazdığı tamsayı değerine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı iletişim kutusundan bir klasör seçerse sıfıra doğru değil; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi çağırdığınızda, uygulama kullanıcının bir klasör seçmesini sağlayan bir iletişim kutusu oluşturur ve gösterir. Yöntem, klasörün yolunu *strOutFolder* parametresine yazar.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CShellManager` `CWinAppEx::GetShellManager` yöntemi kullanarak bir nesneye başvurunun nasıl alındığını `BrowseForFolder` ve yöntemi nasıl kullanılacağını gösterir. Bu kod parçacığı [Explorer örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_Explorer#6](../../mfc/reference/codesnippet/cpp/cshellmanager-class_1.cpp)]

## <a name="cshellmanagerconcatenateitem"></a><a name="concatenateitem"></a>CShellManager::ConcatenateItem

İki PIDL içeren yeni bir liste oluşturur.

```
LPITEMIDLIST ConcatenateItem(
    LPCITEMIDLIST pidl1,
    LPCITEMIDLIST pidl2);
```

### <a name="parameters"></a>Parametreler

*pidl1*<br/>
[içinde] İlk parça.

*pidl2*<br/>
[içinde] İkinci parça.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa yeni öğe listesine işaretçi, aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, *hem pidl1* hem de *pidl2*içerecek kadar büyük yeni bir [ITEMIDLIST](/windows/win32/api/shtypes/ns-shtypes-itemidlist) oluşturur. Daha sonra *pidl1* ve *pidl2'yi* yeni listeye kopyalar.

## <a name="cshellmanagercopyitem"></a><a name="copyitem"></a>CShellManager::CopyItem

Öğe listesini kopyalar.

```
LPITEMIDLIST CopyItem(LPCITEMIDLIST pidlSource);
```

### <a name="parameters"></a>Parametreler

*pidlKaynak*<br/>
[içinde] Özgün madde listesi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa yeni oluşturulan madde listesiiçin bir işaretçi; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Yeni oluşturulan madde listesi, kaynak madde listesiyle aynı boyuta sahiptir.

## <a name="cshellmanagercreateitem"></a><a name="createitem"></a>CShellManager::CreateItem

Yeni bir PIDL oluşturur.

```
LPITEMIDLIST CreateItem(UINT cbSize);
```

### <a name="parameters"></a>Parametreler

*cbSize*<br/>
[içinde] Öğe listesinin boyutu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa oluşturulan madde listesiiçin bir işaretçi; aksi takdirde NULL.

## <a name="cshellmanagercshellmanager"></a><a name="cshellmanager"></a>CShellManager::CShellManager

Bir `CShellManager` nesne inşa eder.

```
CShellManager();
```

### <a name="remarks"></a>Açıklamalar

Çoğu durumda, doğrudan bir `CShellManager` oluşturmak zorunda değildir. Varsayılan olarak, çerçeve sizin için bir tane oluşturur. Bir işaretçi almak `CShellManager` [için, CWinAppEx'i arayın::GetShellManager.](../../mfc/reference/cwinappex-class.md#getshellmanager) Eğer el ile `CShellManager` oluşturursanız, cWinAppEx yöntemi ile başlatılması [gerekir::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager).

## <a name="cshellmanagerfreeitem"></a><a name="freeitem"></a>CShellManager::FreeItem

Öğe listesini siler.

```cpp
void FreeItem(LPITEMIDLIST pidl);
```

### <a name="parameters"></a>Parametreler

*pidl*<br/>
[içinde] Silmek için bir madde listesi.

## <a name="cshellmanagergetitemcount"></a><a name="getitemcount"></a>CShellManager::GetItemCount

Madde listesindeki madde sayısını verir.

```
UINT GetItemCount(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>Parametreler

*pidl*<br/>
[içinde] Öğe listesiiçin işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Madde listesindeki öğe sayısı.

## <a name="cshellmanagergetitemsize"></a><a name="getitemsize"></a>CShellManager::GetItemSize

Öğe listesiboyutunu döndürür.

```
UINT GetItemSize(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>Parametreler

*pidl*<br/>
[içinde] Öğe listesiiçin işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Öğe listesinin boyutu.

## <a name="cshellmanagergetnextitem"></a><a name="getnextitem"></a>CShellManager::GetNextItem

Bir sonraki öğeyi işaretçiden bir öğe tanımlayıcı listesine (PIDL) alır.

```
LPITEMIDLIST GetNextItem(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>Parametreler

*pidl*<br/>
[içinde] Yinelemek için öğelerin listesi.

### <a name="return-value"></a>Dönüş Değeri

Listedeki bir sonraki öğenin işaretçisi.

### <a name="remarks"></a>Açıklamalar

Listede başka öğe yoksa, bu yöntem NULL döndürür.

## <a name="cshellmanagergetparentitem"></a><a name="getparentitem"></a>CShellManager::GetParentItem

Bir öğe tanımlayıcı listesine (PIDL) işaretçinin üst öğesini alır.

```
int GetParentItem(
    LPCITEMIDLIST lpidl,
    LPITEMIDLIST& lpidlParent);
```

### <a name="parameters"></a>Parametreler

*lpidl*<br/>
[içinde] Ebeveyni geri alınacak bir PIDL.

*lpidlEbeveyn*<br/>
[çıkış] Yöntemin sonucu depoladığı bir PIDL başvurusu.

### <a name="return-value"></a>Dönüş Değeri

Üst PIDL düzeyi.

### <a name="remarks"></a>Açıklamalar

PIDL düzeyi masaüstüne göredir. Masaüstü PIDL 0 düzeyine sahip olarak kabul edilir.

## <a name="cshellmanageritemfrompath"></a><a name="itemfrompath"></a>CShellManager::ItemFromPath

İşaretçiyi bir dize yolu tarafından tanımlanan öğeden bir öğe tanımlayıcı listesine (PIDL) alır.

```
HRESULT ItemFromPath(
    LPCTSTR lpszPath,
    LPITEMIDLIST& pidl);
```

### <a name="parameters"></a>Parametreler

*lpszPath*<br/>
[içinde] Öğenin yolunu belirten bir dize.

*pidl*<br/>
[çıkış] PIDL'ye bir gönderme. Yöntem, işaretçiyi iade değerine depolamak için bu PIDL'yi kullanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa NOERROR verir; OLE tanımlı bir hata değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
