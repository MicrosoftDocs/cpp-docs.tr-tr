---
title: CShellManager sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0752d278f0459c3558021d02fbcddb6ba234df53
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852392"
---
# <a name="cshellmanager-class"></a>CShellManager sınıfı
Tanımlayıcı listeleri (Pıdl'ler) için işaretçilerle çalışmanıza olanak tanıyan çeşitli yöntemler uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CShellManager : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CShellManager::CShellManager](#cshellmanager)|Oluşturur bir `CShellManager` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CShellManager::BrowseForFolder](#browseforfolder)|Bir kabuk klasörünün seçmesini sağlayan bir iletişim kutusu görüntüler.|  
|[CShellManager::ConcatenateItem](#concatenateitem)|İki Pıdl'ler art arda ekler.|  
|[CShellManager::CopyItem](#copyitem)|Yeni bir PIDL işaretçisiyle birlikte oluşturur ve sağlanan PIDL işaretçisiyle birlikte buna kopyalar.|  
|[CShellManager::CreateItem](#createitem)|Belirtilen boyutta yeni bir PIDL işaretçisiyle birlikte oluşturur.|  
|[CShellManager::FreeItem](#freeitem)|Sağlanan PIDL işaretçisiyle birlikte siler.|  
|[CShellManager::GetItemCount](#getitemcount)|Sağlanan PIDL işaretçisiyle birlikte öğe sayısını döndürür.|  
|[CShellManager::GetItemSize](#getitemsize)|Sağlanan PIDL işaretçisiyle birlikte boyutunu döndürür.|  
|[CShellManager::GetNextItem](#getnextitem)|PIDL işaretçisiyle birlikte sonraki öğeyi döndürür.|  
|[CShellManager::GetParentItem](#getparentitem)|Sağlanan öğe üst öğesini alır.|  
|[CShellManager::ItemFromPath](#itemfrompath)|Sağlanan yol tarafından tanımlanan öğe için PIDL işaretçisiyle birlikte alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yöntemlerinin `CShellManager` Pıdl'ler tüm ilgilenme sınıfı. Bir PIDL işaretçisiyle birlikte bir kabuk nesnesi için benzersiz bir tanımlayıcıdır.  
  
 Oluşturacağınız değil bir `CShellManager` el ile nesne. Uygulamanızın framework tarafından otomatik olarak yeniden oluşturulur. Ancak, çağırmalıdır [CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager) , uygulamanızın başlatma işlemi sırasında. Bir işaretçi, uygulamanız için kabuk Manager'a almak için arama [CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CShellManager](../../mfc/reference/cshellmanager-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxshellmanager.h  
  
##  <a name="browseforfolder"></a>  CShellManager::BrowseForFolder  
 Bir kabuk klasörünün seçmesini sağlayan bir iletişim kutusu görüntüler.  
  
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
 [out] *strOutFolder*  
 Yöntem tarafından seçilen klasör yolu depolamak için kullanılan dize.  
  
 [in] *pWndParent*  
 Üst penceresine bir işaretçi.  
  
 [in] *lplszInitialFolder*  
 İletişim kutusu görüntülendiğinde, varsayılan olarak seçilen klasörü içeren bir dize.  
  
 [in] *lpszTitle*  
 İletişim kutusunun başlığı.  
  
 [in] *ulFlags*  
 İletişim kutusu için seçenekleri belirten bayraklar. Bkz: [BROWSEINFO](http://msdn.microsoft.com/library/windows/desktop/bb773205) ayrıntılı bir açıklaması için.  
  
 [out] *piFolderImage*  
 Yöntem seçili klasör görüntü dizini nereye yazdığını tamsayı değerini bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İletişim kutusundan bir klasör kullanıcının seçtiği olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırdığınızda, bir uygulama oluşturur ve bir klasör seçmek kullanıcının sağlayan bir iletişim kutusu gösterir. Yöntem klasöre yolunu yazacak *strOutFolder* parametresi.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir başvuru almak gösterilmiştir bir `CShellManager` kullanarak nesne `CWinAppEx::GetShellManager` yöntemi ve nasıl kullanılacağını `BrowseForFolder` yöntemi. Bu kod parçacığı parçasıdır [Gezgini örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer#6](../../mfc/reference/codesnippet/cpp/cshellmanager-class_1.cpp)]  
  
##  <a name="concatenateitem"></a>  CShellManager::ConcatenateItem  
 İki Pıdl'ler içeren yeni bir liste oluşturur.  
  
```  
LPITEMIDLIST ConcatenateItem(
    LPCITEMIDLIST pidl1,  
    LPCITEMIDLIST pidl2);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pidl1*  
 İlk öğe.  
  
 [in] *pidl2*  
 İkinci öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa, yeni bir öğe listesine bir işaretçi bulunmazsa null değerini DÖNDÜRÜR.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem yeni bir oluşturur [ITEMIDLIST](http://msdn.microsoft.com/library/windows/desktop/bb773321) hem de içerecek yeteri kadar büyük *pidl1* ve *pidl2*. Ardından kopyalar *pidl1* ve *pidl2* yeni listesi.  
  
##  <a name="copyitem"></a>  CShellManager::CopyItem  
 Bir öğe listesi kopyalar.  
  
```  
LPITEMIDLIST CopyItem(LPCITEMIDLIST pidlSource);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pidlSource*  
 Orijinal öğe listesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa yeni oluşturulan öğeyi listesine bir işaretçi; bulunmazsa null değerini DÖNDÜRÜR.  
  
### <a name="remarks"></a>Açıklamalar  
 Kaynak öğe listesi olarak aynı boyutta yeni oluşturulan bir öğe listesine sahiptir.  
  
##  <a name="createitem"></a>  CShellManager::CreateItem  
 Yeni bir PIDL işaretçisiyle birlikte oluşturur.  
  
```  
LPITEMIDLIST CreateItem(UINT cbSize);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *cbSize*  
 Öğesi listenin boyutu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa oluşturulan öğeyi listesine bir işaretçi; bulunmazsa null değerini DÖNDÜRÜR.  
  
##  <a name="cshellmanager"></a>  CShellManager::CShellManager  
 Oluşturur bir `CShellManager` nesne.  
  
```  
CShellManager();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çoğu durumda, oluşturma gerekmez bir `CShellManager` doğrudan. Varsayılan olarak, framework sizin için oluşturur. Bir işaretçi almaya `CShellManager`, çağrı [CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager). Oluşturursanız, bir `CShellManager` el yöntemi ile başlatmalısınız [CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager).  
  
##  <a name="freeitem"></a>  CShellManager::FreeItem  
 Bir öğe listesi siler.  
  
```  
void FreeItem(LPITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *PIDL işaretçisiyle birlikte*  
 Silmek için bir öğe listesi.  
  
##  <a name="getitemcount"></a>  CShellManager::GetItemCount  
 Bir öğe listesinden öğe sayısını döndürür.  
  
```  
UINT GetItemCount(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *PIDL işaretçisiyle birlikte*  
 Bir öğe listesine bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe listesindeki öğe sayısı.  
  
##  <a name="getitemsize"></a>  CShellManager::GetItemSize  
 Bir öğe listesi boyutunu döndürür.  
  
```  
UINT GetItemSize(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *PIDL işaretçisiyle birlikte*  
 Bir öğe listesine bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğesi listenin boyutu.  
  
##  <a name="getnextitem"></a>  CShellManager::GetNextItem  
 Sonraki öğeyi bir öğe tanımlayıcı listesi (PIDL işaretçisiyle birlikte) arasında bir işaretçi alır.  
  
```  
LPITEMIDLIST GetNextItem(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *PIDL işaretçisiyle birlikte*  
 Yinelemek için öğeleri listesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Listede bir sonraki öğeye bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Listede daha fazla öğe varsa, bu yöntem NULL döndürür.  
  
##  <a name="getparentitem"></a>  CShellManager::GetParentItem  
 Üst öğe tanımlayıcı listesi (PIDL işaretçisiyle birlikte) için bir işaretçi alır.  
  
```  
int GetParentItem(
    LPCITEMIDLIST lpidl,  
    LPITEMIDLIST& lpidlParent);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpidl*  
 Ana alınan bir PIDL işaretçisiyle birlikte.  
  
 [out] *lpidlParent*  
 Yöntemin sonucu depolayacağınız PIDL işaretçisiyle birlikte bir başvuru.  
  
### <a name="return-value"></a>Dönüş Değeri  
 PIDL işaretçisiyle birlikte üst düzeyi.  
  
### <a name="remarks"></a>Açıklamalar  
 Masaüstü göreli bir PIDL işaretçisiyle birlikte düzeyidir. Masaüstü PIDL işaretçisiyle birlikte bir düzeyde 0 olduğu kabul edilir.  
  
##  <a name="itemfrompath"></a>  CShellManager::ItemFromPath  
 İşaretçiyi bir dize yolu tarafından belirtilen öğe bir öğe tanımlayıcı listesi (PIDL işaretçisiyle birlikte) alır.  
  
```  
HRESULT ItemFromPath(
    LPCTSTR lpszPath,  
    LPITEMIDLIST& pidl);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszPath*  
 Öğesinin yolu belirten bir dize.  
  
 [out] *PIDL işaretçisiyle birlikte*  
 Bir PIDL işaretçisiyle birlikte bir başvuru. Yöntemi, işaretçi dönüş değerini depolamak için bu PIDL işaretçisiyle birlikte kullanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa; NOERROR döndürür bir OLE tanımlı hata değeri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıflar](../../mfc/reference/mfc-classes.md)
