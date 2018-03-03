---
title: "CShellManager sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3e1e3fcff06b2937df8218ce1ab32b91ddf22a7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cshellmanager-class"></a>CShellManager sınıfı
Tanımlayıcı listeleri (PIDLs) işaretçilerle çalışmanıza olanak sağlayan birkaç yöntemler uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CShellManager : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CShellManager::CShellManager](#cshellmanager)|Oluşturan bir `CShellManager` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CShellManager::BrowseForFolder](#browseforfolder)|Kullanıcının Kabuk klasörünün seçmesine olanak sağlayan bir iletişim kutusu görüntüler.|  
|[CShellManager::ConcatenateItem](#concatenateitem)|İki PIDLs art arda ekler.|  
|[CShellManager::CopyItem](#copyitem)|Yeni bir PIDL işaretçisiyle birlikte oluşturur ve sağlanan PIDL işaretçisiyle birlikte kopyalar.|  
|[CShellManager::CreateItem](#createitem)|Belirtilen boyut yeni PIDL işaretçisiyle birlikte oluşturur.|  
|[CShellManager::FreeItem](#freeitem)|Sağlanan PIDL işaretçisiyle birlikte siler.|  
|[CShellManager::GetItemCount](#getitemcount)|Sağlanan PIDL işaretçisiyle birlikte öğe sayısını döndürür.|  
|[CShellManager::GetItemSize](#getitemsize)|Sağlanan PIDL işaretçisiyle birlikte boyutu döndürür.|  
|[CShellManager::GetNextItem](#getnextitem)|PIDL işaretçisiyle birlikte sonraki öğeye döndürür.|  
|[CShellManager::GetParentItem](#getparentitem)|Sağlanan öğesinin üst öğesi alır.|  
|[CShellManager::ItemFromPath](#itemfrompath)|Sağlanan yol tarafından tanımlanan öğe için PIDL işaretçisiyle birlikte alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yöntemlerinin `CShellManager` PIDLs ile tüm anlaşma sınıfı. Bir PIDL işaretçisiyle birlikte bir kabuk nesnesi için benzersiz bir tanımlayıcı değil.  
  
 Değil oluşturmalısınız bir `CShellManager` el ile nesne. Uygulamanızı çerçevesi tarafından otomatik olarak yeniden oluşturulur. Ancak, çağırmalıdır [CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager) , uygulamanızın başlatma işlemi sırasında. Uygulamanız için kabuk Yöneticisi bir işaretçi almak için arama [CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CShellManager](../../mfc/reference/cshellmanager-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxshellmanager.h  
  
##  <a name="browseforfolder"></a>CShellManager::BrowseForFolder  
 Kullanıcının Kabuk klasörünün seçmesine olanak sağlayan bir iletişim kutusu görüntüler.  
  
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
 [out]`strOutFolder`  
 Seçilen klasör yolu depolamak için yöntemi tarafından kullanılan dize.  
  
 [in]`pWndParent`  
 Üst pencere için bir işaretçi.  
  
 [in]`lplszInitialFolder`  
 İletişim kutusu görüntülendiğinde, varsayılan olarak seçili klasörü içeren bir dize.  
  
 [in]`lpszTitle`  
 İletişim kutusu başlığı.  
  
 [in]`ulFlags`  
 Seçenekler iletişim kutusu için belirterek bayraklar. Bkz: [BROWSEINFO](http://msdn.microsoft.com/library/windows/desktop/bb773205) ayrıntılı açıklaması.  
  
 [out]`piFolderImage`  
 Yöntemi seçilen klasörün görüntü dizini nereye yazdığını tamsayı değeri için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı iletişim kutusundan bir klasör seçerse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırdığınızda, uygulama oluşturur ve bir klasör seçmek kullanıcının sağlayan bir iletişim kutusu gösterir. Yöntem klasöre yolunu yazacak `strOutFolder` parametresi.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte bir başvuru almak nasıl gösteren bir `CShellManager` kullanarak nesne `CWinAppEx::GetShellManager` yöntemi ve nasıl kullanılacağını `BrowseForFolder` yöntemi. Bu kod parçacığını parçası olan [Gezgini örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer#6](../../mfc/reference/codesnippet/cpp/cshellmanager-class_1.cpp)]  
  
##  <a name="concatenateitem"></a>CShellManager::ConcatenateItem  
 İki PIDLs içeren yeni bir liste oluşturur.  
  
```  
LPITEMIDLIST ConcatenateItem(
    LPCITEMIDLIST pidl1,  
    LPCITEMIDLIST pidl2);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pidl1`  
 İlk öğe.  
  
 [in]`pidl2`  
 İkinci öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi işlevi başarılı, aksi takdirde, yeni bir öğe listesi `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem yeni bir oluşturur [ITEMIDLIST](http://msdn.microsoft.com/library/windows/desktop/bb773321) büyüklükte her ikisi de içerecek şekilde `pidl1` ve `pidl2`. Ardından kopyalar `pidl1` ve `pidl2` yeni listesine.  
  
##  <a name="copyitem"></a>CShellManager::CopyItem  
 Bir öğe listesi kopyalar.  
  
```  
LPITEMIDLIST CopyItem(LPCITEMIDLIST pidlSource);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pidlSource`  
 Özgün öğe listesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan öğeyi listenin başarılı olursa bir işaretçi; Aksi takdirde `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni oluşturulan öğeyi listenin boyutu ile aynı kaynak öğe listesi vardır.  
  
##  <a name="createitem"></a>CShellManager::CreateItem  
 Yeni bir PIDL işaretçisiyle birlikte oluşturur.  
  
```  
LPITEMIDLIST CreateItem(UINT cbSize);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`cbSize`  
 Öğe listesi boyutu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa oluşturulan öğe listesinden bir işaretçi; Aksi takdirde `NULL`.  
  
##  <a name="cshellmanager"></a>CShellManager::CShellManager  
 Oluşturan bir `CShellManager` nesnesi.  
  
```  
CShellManager();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çoğu durumda, oluşturmanız gerekmez bir `CShellManager` doğrudan. Varsayılan olarak, sizin için bir çerçeve oluşturur. Bir işaretçi almak için `CShellManager`, çağrı [CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager). Oluşturursanız, bir `CShellManager` el ile yöntemiyle başlatmalıdır [CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager).  
  
##  <a name="freeitem"></a>CShellManager::FreeItem  
 Bir öğe listesi siler.  
  
```  
void FreeItem(LPITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pidl`  
 Silmek için bir öğe listesi.  
  
##  <a name="getitemcount"></a>CShellManager::GetItemCount  
 Bir öğe listesinden öğe sayısını döndürür.  
  
```  
UINT GetItemCount(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pidl`  
 Bir işaretçi bir öğe listesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe listesindeki öğe sayısı.  
  
##  <a name="getitemsize"></a>CShellManager::GetItemSize  
 Bir öğe listesi boyutu döndürür.  
  
```  
UINT GetItemSize(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pidl`  
 Bir işaretçi bir öğe listesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe listesi boyutu.  
  
##  <a name="getnextitem"></a>CShellManager::GetNextItem  
 Sonraki öğe arasında bir işaretçi bir öğe tanımlayıcı listesi (PIDL işaretçisiyle birlikte) alır.  
  
```  
LPITEMIDLIST GetNextItem(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pidl`  
 Yinelemek için öğeleri listesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Listedeki bir sonraki öğe için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa daha fazla öğe listede yok, bu yöntem `NULL`.  
  
##  <a name="getparentitem"></a>CShellManager::GetParentItem  
 Bir öğe tanımlayıcı listesi (PIDL işaretçisiyle birlikte) gösteren bir işaretçi üst alır.  
  
```  
int GetParentItem(
    LPCITEMIDLIST lpidl,  
    LPITEMIDLIST& lpidlParent);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpidl`  
 Olan üst alınan bir PIDL işaretçisiyle birlikte.  
  
 [out]`lpidlParent`  
 Yöntem sonuç depolayacağınız bir PIDL işaretçisiyle birlikte referansı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 PIDL işaretçisiyle birlikte üst düzeyi.  
  
### <a name="remarks"></a>Açıklamalar  
 Masaüstü göreli bir PIDL işaretçisiyle birlikte düzeyidir. Masaüstü PIDL işaretçisiyle birlikte 0 düzeyine sahip kabul edilir.  
  
##  <a name="itemfrompath"></a>CShellManager::ItemFromPath  
 İşaretçinin bir öğe tanımlayıcı listesi (PIDL işaretçisiyle birlikte) bir dize yol tarafından tanımlanan öğesi alır.  
  
```  
HRESULT ItemFromPath(
    LPCTSTR lpszPath,  
    LPITEMIDLIST& pidl);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszPath`  
 Öğesinin yolu belirten bir dize.  
  
 [out]`pidl`  
 Bir PIDL işaretçisiyle birlikte referansı. Yöntemi, dönüş değeri işaretçisine depolamak için bu PIDL işaretçisiyle birlikte kullanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `NOERROR` başarılıysa; OLE tanımlı hata değeri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıflar](../../mfc/reference/mfc-classes.md)
