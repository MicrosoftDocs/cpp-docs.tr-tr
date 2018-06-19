---
title: CUserToolsManager sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager::CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager::CreateNewTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::FindTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetArgumentsMenuID
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetDefExt
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetFilter
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetInitialDirMenuID
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetMaxTools
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetToolsEntryCmd
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetUserTools
- AFXUSERTOOLSMANAGER/CUserToolsManager::InvokeTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::IsUserToolCmd
- AFXUSERTOOLSMANAGER/CUserToolsManager::LoadState
- AFXUSERTOOLSMANAGER/CUserToolsManager::MoveToolDown
- AFXUSERTOOLSMANAGER/CUserToolsManager::MoveToolUp
- AFXUSERTOOLSMANAGER/CUserToolsManager::RemoveTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::SaveState
- AFXUSERTOOLSMANAGER/CUserToolsManager::SetDefExt
- AFXUSERTOOLSMANAGER/CUserToolsManager::SetFilter
dev_langs:
- C++
helpviewer_keywords:
- CUserToolsManager [MFC], CUserToolsManager
- CUserToolsManager [MFC], CreateNewTool
- CUserToolsManager [MFC], FindTool
- CUserToolsManager [MFC], GetArgumentsMenuID
- CUserToolsManager [MFC], GetDefExt
- CUserToolsManager [MFC], GetFilter
- CUserToolsManager [MFC], GetInitialDirMenuID
- CUserToolsManager [MFC], GetMaxTools
- CUserToolsManager [MFC], GetToolsEntryCmd
- CUserToolsManager [MFC], GetUserTools
- CUserToolsManager [MFC], InvokeTool
- CUserToolsManager [MFC], IsUserToolCmd
- CUserToolsManager [MFC], LoadState
- CUserToolsManager [MFC], MoveToolDown
- CUserToolsManager [MFC], MoveToolUp
- CUserToolsManager [MFC], RemoveTool
- CUserToolsManager [MFC], SaveState
- CUserToolsManager [MFC], SetDefExt
- CUserToolsManager [MFC], SetFilter
ms.assetid: bdfa37ae-efca-4616-abb5-9d0dcd2d335b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eaa99952daf401132768d9be5d4c589b5fdbee52
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376203"
---
# <a name="cusertoolsmanager-class"></a>CUserToolsManager sınıfı
Koleksiyonunu tutan [CUserTool sınıfı](../../mfc/reference/cusertool-class.md) bir uygulamadaki nesneler. Bir dış uygulama çalıştıran bir menü öğesi bir kullanıcı aracıdır. `CUserToolsManager` Kullanıcı ya da yeni kullanıcı araçları uygulama eklemek için geliştirici nesnesi sağlar. Kullanıcı araçları ile ilişkili komutlarının yürütülmesini destekler ve ayrıca Windows kayıt defterinde kullanıcı araçları hakkında bilgi kaydeder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CUserToolsManager : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CUserToolsManager::CUserToolsManager](#cusertoolsmanager)|Oluşturan bir `CUserToolsManager`.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CUserToolsManager::CreateNewTool](#createnewtool)|Yeni bir kullanıcı aracı oluşturur.|  
|[CUserToolsManager::FindTool](#findtool)|İşaretçi döndürür `CMFCUserTool` belirtilen komut kimliğiyle ilişkili nesne|  
|[CUserToolsManager::GetArgumentsMenuID](#getargumentsmenuid)|İle ilişkili kaynak kimliği döndürür **bağımsız değişkenleri** menüsünde **Araçları** sekmesinde **Özelleştir** iletişim kutusu.|  
|[CUserToolsManager::GetDefExt](#getdefext)|Varsayılan uzantısı döndüren **Dosya Aç** iletişim kutusu ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) kullanır **komutu** alanını **Araçları** sekmesi **Özelleştir** iletişim kutusu.|  
|[CUserToolsManager::GetFilter](#getfilter)|Dosya Filtresi döndüren **Dosya Aç** iletişim kutusu ( [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md)) kullanır **komutu** alanını **Araçları** sekmesi **Özelleştir** iletişim kutusu.|  
|[CUserToolsManager::GetInitialDirMenuID](#getinitialdirmenuid)|İle ilişkili kaynak kimliği döndürür **başlangıç dizini** menüsünde **Araçları** sekmesinde **Özelleştir** iletişim kutusu.|  
|[CUserToolsManager::GetMaxTools](#getmaxtools)|Uygulamada ayrılabilen kullanıcı araçlarını en fazla sayısını döndürür.|  
|[CUserToolsManager::GetToolsEntryCmd](#gettoolsentrycmd)|Kullanıcı araçları için menü öğesi yer tutucu komut Kimliğini döndürür.|  
|[CUserToolsManager::GetUserTools](#getusertools)|Kullanıcı araçlarını listesine bir başvuru döndürür.|  
|[CUserToolsManager::InvokeTool](#invoketool)|Belirtilen komut kimliğine sahip kullanıcı aracı ile ilişkili bir uygulama yürütür|  
|[CUserToolsManager::IsUserToolCmd](#isusertoolcmd)|Komut Kimliği kullanıcı aracı ile ilişkili olup olmadığını belirler.|  
|[CUserToolsManager::LoadState](#loadstate)|Kullanıcı araçları hakkında bilgileri Windows kayıt defterinden yükler.|  
|[CUserToolsManager::MoveToolDown](#movetooldown)|Belirtilen kullanıcı aracı kullanıcı araçlarını listede aşağı taşır.|  
|[CUserToolsManager::MoveToolUp](#movetoolup)|Belirtilen kullanıcı aracı kullanıcı araçlarını listesinde yukarı taşır.|  
|[CUserToolsManager::RemoveTool](#removetool)|Belirtilen kullanıcı aracı, uygulamadan kaldırır.|  
|[CUserToolsManager::SaveState](#savestate)|Windows kayıt defterinde kullanıcı araçları hakkında bilgi depolar.|  
|[CUserToolsManager::SetDefExt](#setdefext)|Varsayılan uzantısını belirtir, **Dosya Aç** iletişim kutusu ( [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md)) kullanır **komutu** alanını **Araçları** sekmesi **Özelleştir** iletişim kutusu.|  
|[CUserToolsManager::SetFilter](#setfilter)|Dosya filtre belirtir **Dosya Aç** iletişim kutusu ( [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md)) kullanır **komutu** alanını **Araçları** sekmesi **Özelleştir** iletişim kutusu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanıcı araçlarını uygulamanıza eklemenizi yapmanız gerekir:  
  
 1. Menü öğesi ve bir kullanıcı aracı menü girişi ilişkili komut Kimliğini ayırır.  
  
 2. Bir kullanıcı, uygulamanızda tanımlayabilirsiniz her kullanıcı aracı için bir sıralı komut kimliği ayırın.  
  
 3. Çağrı [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) yöntemi ve aşağıdaki parametreleri sağlayın: menü komut kimliği, ilk kullanıcı aracını komut kimliği ve son kullanıcı aracını komut kimliği.  
  
 Olmamalıdır yalnızca bir genel `CUserToolsManager` uygulama başına nesne.  
  
 Bir kullanıcı araçlarını örneğin VisualStudioDemo örnek proje bakın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte bir başvuru almak nasıl gösteren bir `CUserToolsManager` nesnesi ve yeni kullanıcı Araçlar oluşturma. Bu kod parçacığını parçası olan [Visual Studio gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#38](../../mfc/codesnippet/cpp/cusertoolsmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CUserToolsManager`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxusertoolsmanager.h  
  
##  <a name="createnewtool"></a>  CUserToolsManager::CreateNewTool  
 Yeni bir kullanıcı aracı oluşturur.  
  
```  
CUserTool* CreateNewTool();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan kullanıcı aracı için bir işaretçi veya `NULL` kullanıcı araçlarını sayısı üst sınırı aştı değilse. Döndürülen tür geçirilir türü ile aynıdır `CWinAppEx::EnableUserTools` olarak `pToolRTC` parametresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem çağrısında sağlanan aralıktaki ilk kullanılabilen menü komut kimliği bulur [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) ve kullanıcı aracı bu kimliği atar.  
  
 Araçlar sayısı maksimum sınıra ulaştığı yöntemi başarısız olur. Bu durum, tüm komut kimlikleri aralığı içinde kullanıcı araçları atanan oluşur. Çağırarak araçları en fazla sayısını alabilir [CUserToolsManager::GetMaxTools](#getmaxtools). Çağırarak araçları listesine erişim sağlayabilmek için [CUserToolsManager::GetUserTools](#getusertools) yöntemi.  
  
##  <a name="cusertoolsmanager"></a>  CUserToolsManager::CUserToolsManager  
 Oluşturan bir `CUserToolsManager`. Her uygulama, en çok bir kullanıcı araçları Yöneticisi olmalıdır.  
  
```  
CUserToolsManager();

 
CUserToolsManager(
    const UINT uiCmdToolsDummy,  
    const UINT uiCmdFirst,  
    const UINT uiCmdLast,  
    CRuntimeClass* pToolRTC=RUNTIME_CLASS(CUserTool),  
    UINT uArgMenuID=0,  
    UINT uInitDirMenuID=0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `uiCmdToolsDummy`  
 Framework'te kullanıcı Araçlar menüsünü komut kimliği için bir yer tutucu olarak kullanan imzalanmamış tamsayı.  
  
 [in] `uiCmdFirst`  
 İlk kullanıcı aracını komut komut kimliği.  
  
 [in] `uiCmdLast`  
 Son kullanıcı aracını komut komut kimliği.  
  
 [in] `pToolRTC`  
 Sınıfı, [CUserToolsManager::CreateNewTool](#createnewtool) oluşturur. Bu sınıf kullanarak türetme bir türü kullanabilirsiniz [CUserTool sınıfı](../../mfc/reference/cusertool-class.md) yerine varsayılan uygulaması.  
  
 [in] `uArgMenuID`  
 Bağımsız değişkenler menü menüsü kaynak kimliği.  
  
 [in] `uInitDirMenuID`  
 Başlangıç dizini menü menüsü kaynak kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu oluşturucu çağırmayın. Bunun yerine, çağrı [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) etkinleştir kullanıcı araçlarını ve çağrısı [CWinAppEx::GetUserToolsManager](../../mfc/reference/cwinappex-class.md#getusertoolsmanager) gösteren bir işaretçi almak için `CUserToolsManager`. Daha fazla bilgi için bkz: [kullanıcı tanımlı Araçlar](../../mfc/user-defined-tools.md).  
  
##  <a name="findtool"></a>  CUserToolsManager::FindTool  
 İşaretçi döndürür [CUserTool sınıfı](../../mfc/reference/cusertool-class.md) belirtilen komut kimliğiyle ilişkili nesne  
  
```  
CUserTool* FindTool(UINT uiCmdId) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `uiCmdId`  
 Menü komut tanımlayıcısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [CUserTool sınıfı](../../mfc/reference/cusertool-class.md) veya `CUserTool`-nesne varsa türetilmiş başarı; Aksi halde `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman `FindTool` olan başarılı, döndürülen tür türünü aynıdır `pToolRTC` parametresi [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).  
  
##  <a name="getargumentsmenuid"></a>  CUserToolsManager::GetArgumentsMenuID  
 İle ilişkili kaynak kimliği döndürür **bağımsız değişkenleri** menüsünde **Araçları** sekmesinde **Özelleştir** iletişim kutusu.  
  
```  
UINT GetArgumentsMenuID() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Menü kaynak tanımlayıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 `uArgMenuID` Parametresinin [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) kaynak Kimliğini belirtir.  
  
##  <a name="getdefext"></a>  CUserToolsManager::GetDefExt  
 Varsayılan uzantısı döndüren **Dosya Aç** iletişim kutusu ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) kullanır **komutu** alanını **Araçları** sekmesi **Özelleştir** iletişim kutusu.  
  
```  
const CString& GetDefExt() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru `CString` uzantısı içeren nesne.  
  
##  <a name="getfilter"></a>  CUserToolsManager::GetFilter  
 Dosya Filtresi döndüren **Dosya Aç** iletişim kutusu ( [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md)) kullanır **komutu** alanını **Araçları** sekmesi **Özelleştir** iletişim kutusu.  
  
```  
const CString& GetFilter() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru `CString` filtre içeren nesne.  
  
##  <a name="getinitialdirmenuid"></a>  CUserToolsManager::GetInitialDirMenuID  
 İle ilişkili kaynak kimliği döndürür **başlangıç dizini** menüsünde **Araçları** sekmesinde **Özelleştir** iletişim kutusu.  
  
```  
UINT GetInitialDirMenuID() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Menü kaynak tanımlayıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen kimliği belirtilen `uInitDirMenuID` parametresinin [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).  
  
##  <a name="getmaxtools"></a>  CUserToolsManager::GetMaxTools  
 Uygulamada ayrılabilen kullanıcı araçlarını en fazla sayısını döndürür.  
  
```  
int GetMaxTools() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrılabilen kullanıcı araçlarını maksimum sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamada ayrılabilen araçları maksimum sayısını almak için bu yöntemi çağırın. Bu sayı kimlikleri aralığında sayısıdır `uiCmdFirst` aracılığıyla `uiCmdLast` için geçirdiğiniz parametreler [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).  
  
##  <a name="gettoolsentrycmd"></a>  CUserToolsManager::GetToolsEntryCmd  
 Kullanıcı araçları için menü öğesi yer tutucu komut Kimliğini döndürür.  
  
```  
UINT GetToolsEntryCmd() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yer tutucu komut kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı araçlarını etkinleştirmek için arama [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools). `uiCmdToolsDummy` Parametresi araçları girişi komutunu komut Kimliğini belirtir. Bu yöntem araçları girişi komut kimliği döndürür Bu kimlik menüde kullanıldığı her yerde menüsü görüntülendiğinde kullanıcı araçları listesi tarafından değiştirilir.  
  
##  <a name="getusertools"></a>  CUserToolsManager::GetUserTools  
 Kullanıcı araçlarını listesine bir başvuru döndürür.  
  
```  
const CObList& GetUserTools() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir const başvuru bir [CObList sınıfı](../../mfc/reference/coblist-class.md) kullanıcı araçlarını listesini içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı listesini almak için bu yöntemi araçları çağrı [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) nesne korur. Her kullanıcı aracı türünde bir nesne tarafından temsil edilen [CUserTool sınıfı](../../mfc/reference/cusertool-class.md) veya türetilmiş bir tür `CUserTool`. Türü tarafından belirtilen `pToolRTC` çağırdığınızda parametresi [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) kullanıcı araçlarını etkinleştirmek için.  
  
##  <a name="invoketool"></a>  CUserToolsManager::InvokeTool  
 Belirtilen komut kimliğine sahip kullanıcı aracı ile ilişkili bir uygulama yürütür  
  
```  
BOOL InvokeTool(UINT uiCmdId);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `uiCmdId`  
 Kullanıcı aracı ile ilişkili menü komut kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı aracı ile ilişkili komutu başarıyla yürütülürse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemin kullanıcıyla ilişkili bir uygulama aracı çağrısı tarafından belirtilen komut Kimliğe sahip `uiCmdId`.  
  
##  <a name="isusertoolcmd"></a>  CUserToolsManager::IsUserToolCmd  
 Komut Kimliği kullanıcı aracı ile ilişkili olup olmadığını belirler.  
  
```  
BOOL IsUserToolCmd(UINT uiCmdId) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `uiCmdId`  
 Menü öğesi bir komut kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Verilen komut kimliği kullanıcı aracı ile ilişkili ise sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, belirtilen komut Kimliğini komut kimliği aralığı içinde olup olmadığını denetler. Çağırdığınızda aralığını belirtin [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) kullanıcı araçlarını etkinleştirmek için.  
  
##  <a name="loadstate"></a>  CUserToolsManager::LoadState  
 Kullanıcı araçları hakkında bilgileri Windows kayıt defterinden yükler.  
  
```  
BOOL LoadState(LPCTSTR lpszProfileName=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszProfileName`  
 Windows kayıt defteri anahtarı yolu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Durumu başarıyla yüklendiyse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem durumunu yükler `CUserToolsManager` Windows kayıt defterinden nesnesi.  
  
 Genellikle, bu yöntemi doğrudan çağırmanız gerekmez. [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate) çalışma başlatma işleminin bir parçası olarak çağırır.  
  
##  <a name="movetooldown"></a>  CUserToolsManager::MoveToolDown  
 Belirtilen kullanıcı aracı kullanıcı araçlarını listede aşağı taşır.  
  
```  
BOOL MoveToolDown(CUserTool* pTool);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pTool`  
 Taşımak için kullanıcı aracı belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı aracı başarıyla taşındıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntemi, başarısız olur aracı, `pTool` belirtir iç listesinde değil veya listedeki son bir araçtır.  
  
##  <a name="movetoolup"></a>  CUserToolsManager::MoveToolUp  
 Belirtilen kullanıcı aracı kullanıcı araçlarını listesinde yukarı taşır.  
  
```  
BOOL MoveToolUp(CUserTool* pTool);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pTool`  
 Taşımak için kullanıcı aracı belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı aracı başarıyla taşındı, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntemi, başarısız olur aracı, `pTool` parametresi belirtir değil iç listesinde veya aracı listedeki ilk aracı öğe ise.  
  
##  <a name="removetool"></a>  CUserToolsManager::RemoveTool  
 Belirtilen kullanıcı aracı, uygulamadan kaldırır.  
  
```  
BOOL RemoveTool(CUserTool* pTool);
```  
  
### <a name="parameters"></a>Parametreler  
 [içinde out] `pTool`  
 Kaldırılacak kullanıcı aracı için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Aracı başarıyla kaldırılırsa. Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Aracı başarıyla kaldırılırsa, bu yöntem siler `pTool`.  
  
##  <a name="savestate"></a>  CUserToolsManager::SaveState  
 Windows kayıt defterinde kullanıcı araçları hakkında bilgi depolar.  
  
```  
BOOL SaveState(LPCTSTR lpszProfileName=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszProfileName`  
 Windows kayıt defteri anahtarı bir yolu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Durumu başarıyla kaydedildi, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli durumunu yöntemi depolar `CUserToolsManager` Windows kayıt defterinde nesnesi.  
  
 Genellikle, bu yöntemi doğrudan çağırmanız gerekmez [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate) uygulama çalışma seri hale getirme sürecinin bir parçası olarak otomatik olarak çağırır.  
  
##  <a name="setdefext"></a>  CUserToolsManager::SetDefExt  
 Varsayılan uzantısını belirtir, **Dosya Aç** iletişim kutusu ( [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md)) kullanır **komutu** alanını **Araçları** sekmesi **Özelleştir** iletişim kutusu.  
  
```  
void SetDefExt(const CString& strDefExt);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `strDefExt`  
 Varsayılan dosya adı uzantısını içeren bir metin dizesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir varsayılan dosya adı uzantısıyla belirtmek için bu yöntemi çağırın **Dosya Aç** kullanıcı bir uygulamanın kullanıcı aracıyla ilişkilendirme seçtiğinde görüntülenen iletişim kutusu. Varsayılan değer "exe" dir.  
  
##  <a name="setfilter"></a>  CUserToolsManager::SetFilter  
 Dosya filtre belirtir **Dosya Aç** iletişim kutusu ( [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md)) kullanır **komutu** alanını **Araçları** sekmesi **Özelleştir** iletişim kutusu.  
  
```  
void SetFilter(const CString& strFilter);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `strFilter`  
 Filtre belirtir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md)   
 [CUserTool Sınıfı](../../mfc/reference/cusertool-class.md)
