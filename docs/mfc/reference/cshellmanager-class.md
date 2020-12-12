---
description: 'Daha fazla bilgi edinin: CShellManager sınıfı'
title: CShellManager sınıfı
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
ms.openlocfilehash: 67145782432c11ed62512eb618444fa19a4909ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264654"
---
# <a name="cshellmanager-class"></a>CShellManager sınıfı

, Tanımlayıcı listelerine yönelik işaretçilerle çalışmanızı sağlayan çeşitli yöntemler uygular (PIDLs).

## <a name="syntax"></a>Syntax

```
class CShellManager : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CShellManager:: CShellManager](#cshellmanager)|Bir `CShellManager` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CShellManager:: BrowseForFolder](#browseforfolder)|Kullanıcının bir kabuk klasörü seçmesini sağlayan bir iletişim kutusu görüntüler.|
|[CShellManager:: ConcatenateItem](#concatenateitem)|İki PIDLs art arda ekler.|
|[CShellManager:: CopyItem](#copyitem)|Yeni bir PIDL oluşturur ve sağlanan PIDL 'yi buna kopyalar.|
|[CShellManager:: CreateItem](#createitem)|Belirtilen boyutta yeni bir PIDL oluşturur.|
|[CShellManager:: Freeıtem](#freeitem)|Sağlanan PIDL 'yi siler.|
|[CShellManager:: GetItemCount](#getitemcount)|Sağlanan PIDL içindeki öğelerin sayısını döndürür.|
|[CShellManager:: Getıtemsize](#getitemsize)|Sağlanan PIDL boyutunu döndürür.|
|[CShellManager:: GetNextItem](#getnextitem)|IDL 'den sonraki öğeyi döndürür.|
|[CShellManager:: Getparentidıtem](#getparentitem)|Sağlanan öğenin üst öğesini alır.|
|[CShellManager:: ıtemfrompath](#itemfrompath)|Sağlanan yol tarafından tanımlanan öğe için PIDL 'yi alır.|

## <a name="remarks"></a>Açıklamalar

`CShellManager`Sınıfının yöntemleri PIDLs ile ilgilidir. IDL, bir kabuk nesnesi için benzersiz bir tanımlayıcıdır.

`CShellManager`El ile bir nesne oluşturmamalıdır. Bu, uygulamanızın çerçevesi tarafından otomatik olarak oluşturulur. Ancak, uygulamanızın başlatma işlemi sırasında [CWinAppEx:: InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager) ' ı çağırmanız gerekir. Uygulamanızın Shell Manager 'a yönelik bir işaretçi almak için, [CWinAppEx:: GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager)' ı çağırın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CShellManager](../../mfc/reference/cshellmanager-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxshellmanager. h

## <a name="cshellmanagerbrowseforfolder"></a><a name="browseforfolder"></a> CShellManager:: BrowseForFolder

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
dışı Yöntemi tarafından seçilen klasörün yolunu depolamak için kullanılan dize.

*pWndParent*<br/>
'ndaki Ana pencereye yönelik bir işaretçi.

*Lplszınitialfolder*<br/>
'ndaki İletişim kutusu görüntülendiğinde varsayılan olarak seçilen klasörü içeren bir dize.

*lpszTitle*<br/>
'ndaki İletişim kutusu için başlık.

*ulFlags*<br/>
'ndaki İletişim kutusu seçeneklerini belirten bayraklar. Ayrıntılı açıklama için bkz. [BROWSEINFO](/windows/win32/api/shlobj_core/ns-shlobj_core-browseinfow) .

*piFolderImage*<br/>
dışı Metodun seçili klasörün görüntü dizinini yazdığı tamsayı değerine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı iletişim kutusundan bir klasör seçerse sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi çağırdığınızda, uygulama, kullanıcının bir klasörü seçmesini sağlayan bir iletişim kutusu oluşturur ve gösterir. Yöntemi, klasörün yolunu *strOutFolder* parametresine yazar.

### <a name="example"></a>Örnek

Aşağıdaki örnek yöntemi kullanarak bir nesneye nasıl bir başvuru alınacağını `CShellManager` `CWinAppEx::GetShellManager` ve yönteminin nasıl kullanılacağını gösterir `BrowseForFolder` . Bu kod parçacığı, [Gezgin örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_Explorer#6](../../mfc/reference/codesnippet/cpp/cshellmanager-class_1.cpp)]

## <a name="cshellmanagerconcatenateitem"></a><a name="concatenateitem"></a> CShellManager:: ConcatenateItem

İki PIDLs içeren yeni bir liste oluşturur.

```
LPITEMIDLIST ConcatenateItem(
    LPCITEMIDLIST pidl1,
    LPCITEMIDLIST pidl2);
```

### <a name="parameters"></a>Parametreler

*pidl1*<br/>
'ndaki İlk öğe.

*pidl2*<br/>
'ndaki İkinci öğe.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa yeni öğe listesine yönelik bir işaretçi, aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, hem *pidl1* hem de *pidl2* içermesi için yeterince büyük olan yeni bir [ımidlist](/windows/win32/api/shtypes/ns-shtypes-itemidlist) oluşturur. Daha sonra *pidl1* ve *pidl2* öğesini yeni listeye kopyalar.

## <a name="cshellmanagercopyitem"></a><a name="copyitem"></a> CShellManager:: CopyItem

Öğe listesini kopyalar.

```
LPITEMIDLIST CopyItem(LPCITEMIDLIST pidlSource);
```

### <a name="parameters"></a>Parametreler

*ıdlsource*<br/>
'ndaki Özgün öğe listesi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa yeni oluşturulan öğe listesine yönelik bir işaretçi; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Yeni oluşturulan öğe listesi, kaynak öğe listesi ile aynı boyuta sahiptir.

## <a name="cshellmanagercreateitem"></a><a name="createitem"></a> CShellManager:: CreateItem

Yeni bir PIDL oluşturur.

```
LPITEMIDLIST CreateItem(UINT cbSize);
```

### <a name="parameters"></a>Parametreler

*cbSize*<br/>
'ndaki Öğe listesinin boyutu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa oluşturulan öğe listesine yönelik bir işaretçi; Aksi takdirde NULL.

## <a name="cshellmanagercshellmanager"></a><a name="cshellmanager"></a> CShellManager:: CShellManager

Bir `CShellManager` nesnesi oluşturur.

```
CShellManager();
```

### <a name="remarks"></a>Açıklamalar

Çoğu durumda, doğrudan oluşturmanız gerekmez `CShellManager` . Varsayılan olarak, çerçeve sizin için bir tane oluşturur. ' A bir işaretçi almak için `CShellManager` , [CWinAppEx:: GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager)' ı çağırın. `CShellManager`El ile oluşturursanız, [CWinAppEx:: InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager)yöntemiyle onu başlatmalısınız.

## <a name="cshellmanagerfreeitem"></a><a name="freeitem"></a> CShellManager:: Freeıtem

Öğe listesini siler.

```cpp
void FreeItem(LPITEMIDLIST pidl);
```

### <a name="parameters"></a>Parametreler

*pidl*<br/>
'ndaki Silinecek öğe listesi.

## <a name="cshellmanagergetitemcount"></a><a name="getitemcount"></a> CShellManager:: GetItemCount

Öğe listesindeki öğe sayısını döndürür.

```
UINT GetItemCount(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>Parametreler

*pidl*<br/>
'ndaki Öğe listesi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Öğe listesindeki öğe sayısı.

## <a name="cshellmanagergetitemsize"></a><a name="getitemsize"></a> CShellManager:: Getıtemsize

Bir öğe listesinin boyutunu döndürür.

```
UINT GetItemSize(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>Parametreler

*pidl*<br/>
'ndaki Öğe listesi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Öğe listesinin boyutu.

## <a name="cshellmanagergetnextitem"></a><a name="getnextitem"></a> CShellManager:: GetNextItem

Bir işaretçiden bir öğe tanımlayıcı listesine (PIDL) sonraki öğeyi alır.

```
LPITEMIDLIST GetNextItem(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>Parametreler

*pidl*<br/>
'ndaki Yineedilecek öğelerin listesi.

### <a name="return-value"></a>Dönüş Değeri

Listedeki bir sonraki öğeye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Listede daha fazla öğe yoksa, bu yöntem NULL değerini döndürür.

## <a name="cshellmanagergetparentitem"></a><a name="getparentitem"></a> CShellManager:: Getparentidıtem

Bir öğe tanımlayıcı listesinin (PIDL) bir işaretçisinin üst öğesini alır.

```
int GetParentItem(
    LPCITEMIDLIST lpidl,
    LPITEMIDLIST& lpidlParent);
```

### <a name="parameters"></a>Parametreler

*lpidl*<br/>
'ndaki Üst öğesi alınacak bir PIDL.

*lpidlParent*<br/>
dışı Yöntemin sonucu depolayacağı bir PIDL başvurusu.

### <a name="return-value"></a>Dönüş Değeri

Üst IDL düzeyi.

### <a name="remarks"></a>Açıklamalar

Bir PIDL düzeyi masaüstü ile ilişkilidir. Masaüstü PIDL, düzeyi 0 olan olarak değerlendirilir.

## <a name="cshellmanageritemfrompath"></a><a name="itemfrompath"></a> CShellManager:: ıtemfrompath

Bir dize yolu tarafından tanımlanan öğeden bir öğe tanımlayıcı listesi (PIDL) işaretçisini alır.

```
HRESULT ItemFromPath(
    LPCTSTR lpszPath,
    LPITEMIDLIST& pidl);
```

### <a name="parameters"></a>Parametreler

*lpszPath*<br/>
'ndaki Öğenin yolunu belirten bir dize.

*pidl*<br/>
dışı Bir PIDL başvurusu. Yöntemi bu PIDL 'yi, dönüş değerine işaretçiyi depolamak için kullanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa NOERROR döndürür; OLE tanımlı bir hata değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
