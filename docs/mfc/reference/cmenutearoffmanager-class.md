---
title: CMenuTearOffManager sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Build
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::GetRegPath
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Initialize
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::IsDynamicID
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Parse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Reset
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetInUse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetupTearOffMenus
dev_langs:
- C++
helpviewer_keywords:
- CMenuTearOffManager [MFC], CMenuTearOffManager
- CMenuTearOffManager [MFC], Build
- CMenuTearOffManager [MFC], GetRegPath
- CMenuTearOffManager [MFC], Initialize
- CMenuTearOffManager [MFC], IsDynamicID
- CMenuTearOffManager [MFC], Parse
- CMenuTearOffManager [MFC], Reset
- CMenuTearOffManager [MFC], SetInUse
- CMenuTearOffManager [MFC], SetupTearOffMenus
ms.assetid: ab7ca272-ce42-4678-95f7-6ad75038f5a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4dcbd5ea33b50e66d1c9e858669a3174042a19e0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cmenutearoffmanager-class"></a>CMenuTearOffManager sınıfı
Etiketleri menüleri yönetir. Etiketleri menü menü çubuğu menüsünde bulunur. Kullanıcı bir etiketleri menü menü çubuğu, etiketleri menü float neden kaldırabilirsiniz.  
  
   [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
   
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMenuTearOffManager : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMenuTearOffManager::CMenuTearOffManager](#cmenutearoffmanager)|Oluşturan bir `CMenuTearOffManager` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMenuTearOffManager::Build](#build)||  
|[CMenuTearOffManager::GetRegPath](#getregpath)||  
|[CMenuTearOffManager::Initialize](#initialize)|Başlatır bir `CMenuTearOffManager` nesnesi.|  
|[CMenuTearOffManager::IsDynamicID](#isdynamicid)||  
|[CMenuTearOffManager::Parse](#parse)||  
|[CMenuTearOffManager::Reset](#reset)||  
|[CMenuTearOffManager::SetInUse](#setinuse)||  
|[CMenuTearOffManager::SetupTearOffMenus](#setuptearoffmenus)||  
  
## <a name="remarks"></a>Açıklamalar  
 Etiketleri menüleri, uygulamanızda kullanmak için bilmeniz gereken bir `CMenuTearOffManager` nesnesi. Çoğu durumda, oluşturduğunuz başlatmak veya olmaz bir `CMenuTearOffManager` doğrudan nesne. Çağırdığınızda bu sizin için işlenir [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus) işlevi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek oluşturmak ve başlatma yapmayı gösteren bir `CMenuTearOffManager` çağırarak nesne `CWinAppEX::EnableTearOffMenus` yöntemi. Bu kod parçacığını parçası olan [Word paneli örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#12](../../mfc/reference/codesnippet/cpp/cmenutearoffmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMenuTearOffManager`   
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmenutearoffmanager.h  
  
##  <a name="build"></a>  CMenuTearOffManager::Build  

  
```  
void Build(
    UINT uiTearOffBarID,  
    CString& strText);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `uiTearOffBarID`  
 [in] `strText`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="cmenutearoffmanager"></a>  CMenuTearOffManager::CMenuTearOffManager  
 Oluşturan bir [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) nesnesi.  
  
```  
CMenuTearOffManager();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çoğu durumda, değil oluşturmalısınız bir `CMenuTearOffManager` el ile. Uygulamanızı çerçevesini oluşturur `CMenuTearOffManager` nesne çağırdığınızda [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus).  
  
##  <a name="getregpath"></a>  CMenuTearOffManager::GetRegPath  

  
```  
LPCTSTR GetRegPath() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="initialize"></a>  CMenuTearOffManager::Initialize  
 Başlatır bir [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) nesnesi.  
  
```  
BOOL Initialize(
    LPCTSTR lpszRegEntry,  
    UINT uiTearOffMenuFirst,  
    UINT uiTearOffMenuLast);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszRegEntry`  
 Bir kayıt defteri girdisi yolunu içeren bir dize. Uygulamalarınız, bu kayıt defteri girdisi etiketleri çubukları ayarlarını depolar.  
  
 [in] `uiTearOffMenuFirst`  
 Etiketleri menü ilk menü kimliği.  
  
 [in] `uiTearOffMenuLast`  
 Etiketleri menü son menü kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Menü kimlikleri aralığını `uiTearOffMenuFirst` için `uiTearOffMenuLast` sürekli bir aralık olmalıdır. Aralık uygulamada aynı anda görünebilir etiketleri menüleri sayısını tanımlar.  
  
##  <a name="isdynamicid"></a>  CMenuTearOffManager::IsDynamicID  

  
```  
BOOL IsDynamicID(UINT uiID) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `uiID`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="parse"></a>  CMenuTearOffManager::Parse  

  
```  
UINT Parse(CString& str);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `str`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="reset"></a>  CMenuTearOffManager::Reset  

  
```  
void Reset(HMENU hmenu);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `hmenu`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setinuse"></a>  CMenuTearOffManager::SetInUse  

  
```  
void SetInUse(
    UINT uiCmdId,  
    BOOL bUse = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `uiCmdId`  
 [in] `bUse`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setuptearoffmenus"></a>  CMenuTearOffManager::SetupTearOffMenus  

  
```  
void SetupTearOffMenus(HMENU hMenu);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `hMenu`  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Sınıfı](../../mfc/reference/cwinappex-class.md)
