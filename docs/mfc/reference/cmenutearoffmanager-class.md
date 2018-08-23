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
ms.openlocfilehash: b05c93bbdfd09bc28288b27a55520c5ac664b723
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42465732"
---
# <a name="cmenutearoffmanager-class"></a>CMenuTearOffManager sınıfı
Etiket menülerini yönetir. Bir etiket menü menü çubuğunda bir menü ' dir. Kullanıcının bir etiket menü menü çubuğundan kaydırmak ayrılabilir menüyü menü neden kaldırabilirsiniz.  
  
   Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.  
   
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMenuTearOffManager : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMenuTearOffManager::CMenuTearOffManager](#cmenutearoffmanager)|Oluşturur bir `CMenuTearOffManager` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMenuTearOffManager::Build](#build)||  
|[CMenuTearOffManager::GetRegPath](#getregpath)||  
|[CMenuTearOffManager::Initialize](#initialize)|Başlatan bir `CMenuTearOffManager` nesne.|  
|[CMenuTearOffManager::IsDynamicID](#isdynamicid)||  
|[CMenuTearOffManager::Parse](#parse)||  
|[CMenuTearOffManager::Reset](#reset)||  
|[CMenuTearOffManager::SetInUse](#setinuse)||  
|[CMenuTearOffManager::SetupTearOffMenus](#setuptearoffmenus)||  
  
## <a name="remarks"></a>Açıklamalar  
 Etiket menülerini kullanmak için olmalıdır bir `CMenuTearOffManager` nesne. Çoğu durumda, oluşturduğunuz başlatmak veya olmaz bir `CMenuTearOffManager` doğrudan nesne. Çağırdığınızda bu sizin için işlenir [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus) işlevi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, oluşturmak ve başlatmak gösterilmiştir bir `CMenuTearOffManager` çağırarak `CWinAppEX::EnableTearOffMenus` yöntemi. Bu kod parçacığı parçasıdır [Word paneli örnek](../../visual-cpp-samples.md).  
  
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
 [in] *uiTearOffBarID*  
 [in] *strText*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="cmenutearoffmanager"></a>  CMenuTearOffManager::CMenuTearOffManager  
 Oluşturur bir [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) nesne.  
  
```  
CMenuTearOffManager();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çoğu durumda, değil oluşturmalısınız bir `CMenuTearOffManager` el ile. Uygulama Framework'ü oluşturur `CMenuTearOffManager` nesne çağırdığınızda [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus).  
  
##  <a name="getregpath"></a>  CMenuTearOffManager::GetRegPath  

  
```  
LPCTSTR GetRegPath() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="initialize"></a>  CMenuTearOffManager::Initialize  
 Başlatan bir [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) nesne.  
  
```  
BOOL Initialize(
    LPCTSTR lpszRegEntry,  
    UINT uiTearOffMenuFirst,  
    UINT uiTearOffMenuLast);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszRegEntry*  
 Bir kayıt defteri girişi yolunu içeren bir dize. Uygulamalarınız bu kayıt defteri girdisi etkinleştiriliyorken çubukları için ayarları depolar.  
  
 [in] *uiTearOffMenuFirst*  
 Bir etiket menü ilk menü kimliği.  
  
 [in] *uiTearOffMenuLast*  
 Bir etiket menü son menü kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Menü kimlikleri aralığını *uiTearOffMenuFirst* için *uiTearOffMenuLast* sürekli aralığı olmalıdır. Aralık, uygulamanın aynı anda görünen etiket menülerini sayısını tanımlar.  
  
##  <a name="isdynamicid"></a>  CMenuTearOffManager::IsDynamicID  

  
```  
BOOL IsDynamicID(UINT uiID) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiID*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="parse"></a>  CMenuTearOffManager::Parse  

  
```  
UINT Parse(CString& str);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *str*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="reset"></a>  CMenuTearOffManager::Reset  

  
```  
void Reset(HMENU hmenu);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *hmenu*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setinuse"></a>  CMenuTearOffManager::SetInUse  

  
```  
void SetInUse(
    UINT uiCmdId,  
    BOOL bUse = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiCmdId*  
 [in] *bBilinmeyen*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setuptearoffmenus"></a>  CMenuTearOffManager::SetupTearOffMenus  

  
```  
void SetupTearOffMenus(HMENU hMenu);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *hMenu*  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Sınıfı](../../mfc/reference/cwinappex-class.md)
