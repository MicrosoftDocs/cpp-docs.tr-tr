---
title: CusertoolsManager Sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: c1f14657350c08679868299ce4878cca2ae10eec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373234"
---
# <a name="cusertoolsmanager-class"></a>CusertoolsManager Sınıfı

Bir uygulamada [CUserTool Class](../../mfc/reference/cusertool-class.md) nesnelerinin toplanmasını sağlar. Kullanıcı aracı, harici bir uygulama çalıştıran bir menü öğesidir. Nesne, `CUserToolsManager` kullanıcının veya geliştiricinin uygulamaya yeni kullanıcı araçları eklemesini sağlar. Kullanıcı araçlarıyla ilişkili komutların yürütülmesini destekler ve Windows kayıt defterinde kullanıcı araçları hakkında bilgi kaydeder.

## <a name="syntax"></a>Sözdizimi

```
class CUserToolsManager : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CusertoolsManager::CusertoolsManager](#cusertoolsmanager)|Bir `CUserToolsManager`.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CuserToolsManager::CreateNewTool](#createnewtool)|Yeni bir kullanıcı aracı oluşturur.|
|[CusertoolsManager::Findtool](#findtool)|İşaretçiyi belirtilen `CMFCUserTool` bir komut kimliğiyle ilişkili nesneye döndürür.|
|[CUserToolsManager::GetArgumentsMenuID](#getargumentsmenuid)|**Özelleştir** iletişim kutusunun **Araçlar** sekmesinde **Bağımsızlar** menüsüyle ilişkili kaynak kimliğini döndürür.|
|[CUserToolsManager::GetDefExt](#getdefext)|**Dosya Aç** iletişim kutusunun [(CFileDialog)](../../mfc/reference/cfiledialog-class.md#cfiledialog)Özelleştir iletişim kutusunun **Araçlar** sekmesindeki **Komut** alanında kullandığı varsayılan uzantıyı **döndürür.**|
|[CuserToolsManager::GetFilter](#getfilter)|**Dosya Aç** iletişim kutusunun [(CFileDialog Class)](../../mfc/reference/cfiledialog-class.md)Kullandığı Dosya Filtresini, **Özelleştir** iletişim kutusunun **Araçlar** sekmesindeki **Komut** alanında kullanır.|
|[CuserToolsManager::GetInitialDirMenuID](#getinitialdirmenuid)|**Özelleştir** iletişim kutusunun **Araçlar** sekmesinde **İlk dizin** menüsüyle ilişkili kaynak kimliğini döndürür.|
|[CusertoolsManager::GetmaxTools](#getmaxtools)|Uygulamada ayrılabilecek maksimum kullanıcı aracı sayısını verir.|
|[CUserToolsManager::GetToolsEntryCmd](#gettoolsentrycmd)|Kullanıcı araçları için menü öğesi yer tutucunun komut kimliğini verir.|
|[CusertoolsManager::GetuserTools](#getusertools)|Kullanıcı araçları listesine bir başvuru verir.|
|[CuserToolsManager::InvokeTool](#invoketool)|Belirli bir komut kimliğine sahip kullanıcı aracıyla ilişkili bir uygulamayı yürütür.|
|[CUserToolsManager::IsUserToolCmd](#isusertoolcmd)|Komut kimliğinin bir kullanıcı aracıyla ilişkili olup olmadığını belirler.|
|[CuserToolsManager::loadstate](#loadstate)|Windows kayıt defterinden kullanıcı araçları hakkında bilgi yükler.|
|[CuserToolsManager::MoveToolDown](#movetooldown)|Belirtilen kullanıcı aracını kullanıcı araçları listesinde aşağı taşır.|
|[CuserToolsManager::MoveToolUp](#movetoolup)|Belirtilen kullanıcı aracını kullanıcı araçları listesinde yukarı taşır.|
|[CusertoolsManager::Removetool](#removetool)|Belirtilen kullanıcı aracını uygulamadan kaldırır.|
|[CuserToolsManager::SaveState](#savestate)|Windows kayıt defterinde kullanıcı araçları yla ilgili bilgileri depolar.|
|[CUserToolsManager::SetDefExt](#setdefext)|**Dosya Aç** iletişim kutusunun [(CFileDialog Class)](../../mfc/reference/cfiledialog-class.md) **Özelleştir** iletişim kutusunun **Araçlar** sekmesindeki **Komut** alanında kullandığı varsayılan uzantıyı belirtir.|
|[CuserToolsManager::SetFilter](#setfilter)|**Dosya Aç** iletişim kutusunun [(CFileDialog Class)](../../mfc/reference/cfiledialog-class.md) **Özelleştir** iletişim kutusunun **Araçlar** sekmesindeki **Komut** alanında kullandığı dosya filtresini belirtir.|

## <a name="remarks"></a>Açıklamalar

Kullanıcı araçlarını uygulamanıza dahil etmek için şunları yapmalısınız:

1. Bir menü öğesi ve ilişkili komut kimliğini kullanıcı aracı menüsü girişi için ayırın.

2. Bir kullanıcının uygulamanızda tanımlayabileceği her kullanıcı aracı için sıralı bir komut kimliği ayırın.

3. [CWinAppEx'i arayın::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) yöntemini ve aşağıdaki parametreleri verin: menü komut u, ilk kullanıcı araç komut kimliği ve son kullanıcı aracı komut kimliği.

Uygulama başına yalnızca `CUserToolsManager` bir genel nesne olmalıdır.

Kullanıcı araçları nın bir örneği için VisualStudioDemo örnek projesine bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CUserToolsManager` nesneye nasıl başvuru alındığını ve yeni kullanıcı araçlarının nasıl oluşturulurtur olduğunu gösterir. Bu kod snippet [Visual Studio Demo örnek](../../overview/visual-cpp-samples.md)parçasıdır.

[!code-cpp[NVC_MFC_VisualStudioDemo#38](../../mfc/codesnippet/cpp/cusertoolsmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CUserToolsManager`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxusertoolsmanager.h

## <a name="cusertoolsmanagercreatenewtool"></a><a name="createnewtool"></a>CuserToolsManager::CreateNewTool

Yeni bir kullanıcı aracı oluşturur.

```
CUserTool* CreateNewTool();
```

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan kullanıcı aracına işaretçi veya kullanıcı araçlarının sayısı maksimumu aşmışsa NULL. Döndürülen `CWinAppEx::EnableUserTools` *tür, pToolRTC* parametresi olarak geçirilen türle aynıdır.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, CWinAppEx'e yapılan çağrıda verilen aralıktaki ilk kullanılabilir menü komut uyanının kimliğini [bulur::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) ve kullanıcı aracına bu kimliği atar.

Araç sayısı maksimuma ulaşmışsa yöntem başarısız olur. Bu, aralıktaki tüm komut d'leri kullanıcı araçlarına atandığında oluşur. CUserToolsManager'ı arayarak maksimum araç sayısını [alabilirsiniz::GetMaxTools.](#getmaxtools) [CUserToolsManager::GetUserTools](#getusertools) yöntemini arayarak araçlar listesine erişebilirsiniz.

## <a name="cusertoolsmanagercusertoolsmanager"></a><a name="cusertoolsmanager"></a>CusertoolsManager::CusertoolsManager

Bir `CUserToolsManager`. Her uygulamanın en fazla bir kullanıcı aracı yöneticisi olmalıdır.

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

*uiCmdToolsDummy*<br/>
[içinde] Çerçevenin kullanıcı araçları menüsünün komut kimliği için yer tutucu olarak kullandığı imzasız bir tamsayı.

*uiCmdİlk*<br/>
[içinde] İlk kullanıcı aracı komutu için komut kimliği.

*uiCmdSon*<br/>
[içinde] Son kullanıcı aracı komutu için komut kimliği.

*pToolRTC*<br/>
[içinde] [CUserToolsManager::CreateNewTool'un](#createnewtool) oluşturduğu sınıf. Bu sınıfı kullanarak, varsayılan uygulama yerine türetilmiş bir [CUserTool Sınıfı](../../mfc/reference/cusertool-class.md) türünü kullanabilirsiniz.

*uArgMenuID*<br/>
[içinde] Bağımsız değişkenler açılır menüsünün menü kaynak kimliği.

*uInitDirMenuID*<br/>
[içinde] İlk dizin açılır menüsünün menü kaynak kimliği.

### <a name="remarks"></a>Açıklamalar

Bu yapıcıyı aramayın. Bunun yerine, [CWinAppEx'i arayın::Kullanıcı](../../mfc/reference/cwinappex-class.md#enableusertools) araçlarını etkinleştirmek için EnableUserTools'u arayın ve [CWinAppEx'i arayın::GetUserToolsManager'a](../../mfc/reference/cwinappex-class.md#getusertoolsmanager) bir işaretçi elde etmek için `CUserToolsManager`. Daha fazla bilgi için [Kullanıcı Tanımlı Araçlar'a](../../mfc/user-defined-tools.md)bakın.

## <a name="cusertoolsmanagerfindtool"></a><a name="findtool"></a>CusertoolsManager::Findtool

İşaretçiyi, belirtilen bir komut kimliğiyle ilişkili [CUserTool Sınıfı](../../mfc/reference/cusertool-class.md) nesnesine döndürür.

```
CUserTool* FindTool(UINT uiCmdId) const;
```

### <a name="parameters"></a>Parametreler

*uiCmdId*<br/>
[içinde] Menü komut tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Bir [CUserTool Sınıfı](../../mfc/reference/cusertool-class.md) veya `CUserTool`başarılı olursa türetilmiş nesne için bir işaretçi; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Başarılı `FindTool` olduğunda, döndürülen tür CWinAppEx *için pToolRTC* parametre türü ile [aynıdır::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).

## <a name="cusertoolsmanagergetargumentsmenuid"></a><a name="getargumentsmenuid"></a>CUserToolsManager::GetArgumentsMenuID

**Özelleştir** iletişim kutusunun **Araçlar** sekmesinde **Bağımsızlar** menüsüyle ilişkili kaynak kimliğini döndürür.

```
UINT GetArgumentsMenuID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Menü kaynağının tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

[CWinAppEx'in](../../mfc/reference/cwinappex-class.md#enableusertools) *uArgMenuID* parametresi::EnableUserTools kaynağın kimliğini belirtir.

## <a name="cusertoolsmanagergetdefext"></a><a name="getdefext"></a>CUserToolsManager::GetDefExt

**Dosya Aç** iletişim kutusunun [(CFileDialog)](../../mfc/reference/cfiledialog-class.md#cfiledialog)Özelleştir iletişim kutusunun **Araçlar** sekmesindeki **Komut** alanında kullandığı varsayılan uzantıyı **döndürür.**

```
const CString& GetDefExt() const;
```

### <a name="return-value"></a>Dönüş Değeri

Uzantıyı `CString` içeren nesneye bir başvuru.

## <a name="cusertoolsmanagergetfilter"></a><a name="getfilter"></a>CuserToolsManager::GetFilter

**Dosya Aç** iletişim kutusunun [(CFileDialog Class)](../../mfc/reference/cfiledialog-class.md)Kullandığı Dosya Filtresini, **Özelleştir** iletişim kutusunun **Araçlar** sekmesindeki **Komut** alanında kullanır.

```
const CString& GetFilter() const;
```

### <a name="return-value"></a>Dönüş Değeri

Filtreyi `CString` içeren nesneye bir başvuru.

## <a name="cusertoolsmanagergetinitialdirmenuid"></a><a name="getinitialdirmenuid"></a>CuserToolsManager::GetInitialDirMenuID

**Özelleştir** iletişim kutusunun **Araçlar** sekmesinde **İlk dizin** menüsüyle ilişkili kaynak kimliğini döndürür.

```
UINT GetInitialDirMenuID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Menü kaynak tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

Döndürülen kimlik CWinAppEx *uInitDirMenuID* parametre [belirtilir::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).

## <a name="cusertoolsmanagergetmaxtools"></a><a name="getmaxtools"></a>CusertoolsManager::GetmaxTools

Uygulamada ayrılabilecek maksimum kullanıcı aracı sayısını verir.

```
int GetMaxTools() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılabilen maksimum kullanıcı aracı sayısı.

### <a name="remarks"></a>Açıklamalar

Uygulamada ayrılabilecek en fazla araç sayısını almak için bu yöntemi arayın. Bu numara, CWinAppEx'e geçtiğiniz *uiCmdLast* parametreleri aracılığıyla *uiCmdFirst aralığındaki iICmdFirst'in* [numarasıdır::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).

## <a name="cusertoolsmanagergettoolsentrycmd"></a><a name="gettoolsentrycmd"></a>CUserToolsManager::GetToolsEntryCmd

Kullanıcı araçları için menü öğesi yer tutucunun komut kimliğini verir.

```
UINT GetToolsEntryCmd() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yer tutucunun komut kimliği.

### <a name="remarks"></a>Açıklamalar

Kullanıcı araçlarını etkinleştirmek için [CWinAppEx::EnableUserTools'u](../../mfc/reference/cwinappex-class.md#enableusertools)arayabilirsiniz. *uiCmdToolsDummy* parametresi araçlar giriş komutunun komut kimliğini belirtir. Bu yöntem, araçlar giriş komut uyruşu kimliğini döndürür. Bu kimlik bir menüde nerede kullanılırsa kullanılsın, menü görüntülendiğinde kullanıcı araçları listesi yle değiştirilir.

## <a name="cusertoolsmanagergetusertools"></a><a name="getusertools"></a>CusertoolsManager::GetuserTools

Kullanıcı araçları listesine bir başvuru verir.

```
const CObList& GetUserTools() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı araçlarının listesini içeren [CObList Class](../../mfc/reference/coblist-class.md) nesnesine const başvurusu.

### <a name="remarks"></a>Açıklamalar

[CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) nesnesinin koruduğu kullanıcı araçlarının listesini almak için bu yöntemi arayın. Her kullanıcı aracı [CUserTool Sınıfı](../../mfc/reference/cusertool-class.md) türünden bir nesne veya `CUserTool`türetilen bir tür tarafından temsil edilir. [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) kullanıcı araçlarını etkinleştirmek için aradiğinizde tip *pToolRTC* parametresi tarafından belirtilir.

## <a name="cusertoolsmanagerinvoketool"></a><a name="invoketool"></a>CuserToolsManager::InvokeTool

Belirli bir komut kimliğine sahip kullanıcı aracıyla ilişkili bir uygulamayı yürütür.

```
BOOL InvokeTool(UINT uiCmdId);
```

### <a name="parameters"></a>Parametreler

*uiCmdId*<br/>
[içinde] Kullanıcı aracıyla ilişkili menü komut kimliği.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı aracıyla ilişkili komut başarıyla yürütülürse sıfıra inmez; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*uiCmdId*tarafından belirtilen komut kimliğine sahip kullanıcı aracıyla ilişkili bir uygulamayı yürütmek için bu yöntemi arayın.

## <a name="cusertoolsmanagerisusertoolcmd"></a><a name="isusertoolcmd"></a>CUserToolsManager::IsUserToolCmd

Komut kimliğinin bir kullanıcı aracıyla ilişkili olup olmadığını belirler.

```
BOOL IsUserToolCmd(UINT uiCmdId) const;
```

### <a name="parameters"></a>Parametreler

*uiCmdId*<br/>
[içinde] Menü öğesinin komut kimliği.

### <a name="return-value"></a>Dönüş Değeri

Verilen bir komut kimliği bir kullanıcı aracıyla ilişkiliyse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, verilen komut kimliği komut kimliği aralığında olup olmadığını denetler. Kullanıcı araçlarını etkinleştirmek için [CWinAppEx::EnableUserTools'u](../../mfc/reference/cwinappex-class.md#enableusertools) aradiğinizde aralığı belirtirsiniz.

## <a name="cusertoolsmanagerloadstate"></a><a name="loadstate"></a>CuserToolsManager::loadstate

Windows kayıt defterinden kullanıcı araçları hakkında bilgi yükler.

```
BOOL LoadState(LPCTSTR lpszProfileName=NULL);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[içinde] Windows kayıt defteri anahtarının yolu.

### <a name="return-value"></a>Dönüş Değeri

Devlet başarıyla yüklenmişse sıfıra inmez; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CUserToolsManager` Windows kayıt defterinden nesnenin durumunu yükler.

Genellikle, bu yöntemi doğrudan aramazsınız. [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate) bunu çalışma alanı başlatma sürecinin bir parçası olarak adlandırır.

## <a name="cusertoolsmanagermovetooldown"></a><a name="movetooldown"></a>CuserToolsManager::MoveToolDown

Belirtilen kullanıcı aracını kullanıcı araçları listesinde aşağı taşır.

```
BOOL MoveToolDown(CUserTool* pTool);
```

### <a name="parameters"></a>Parametreler

*pTool*<br/>
[içinde] Taşımak için kullanıcı aracını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı aracı başarıyla aşağı taşınmışsa sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*PTool'un* belirttiği araç iç listede değilse veya araç listede sonuncuysa yöntem başarısız olur.

## <a name="cusertoolsmanagermovetoolup"></a><a name="movetoolup"></a>CuserToolsManager::MoveToolUp

Belirtilen kullanıcı aracını kullanıcı araçları listesinde yukarı taşır.

```
BOOL MoveToolUp(CUserTool* pTool);
```

### <a name="parameters"></a>Parametreler

*pTool*<br/>
[içinde] Taşımak için kullanıcı aracını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı aracı başarıyla yukarı taşınmışsa sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

PTool parametresinin belirttiği *pTool* araç iç listede değilse veya araç listedeki ilk araç öğesiyse yöntem başarısız olur.

## <a name="cusertoolsmanagerremovetool"></a><a name="removetool"></a>CusertoolsManager::Removetool

Belirtilen kullanıcı aracını uygulamadan kaldırır.

```
BOOL RemoveTool(CUserTool* pTool);
```

### <a name="parameters"></a>Parametreler

*pTool*<br/>
[içinde, dışarı] Kaldırılacak bir kullanıcı aracına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Araç başarıyla kaldırılırsa DOĞRU. Aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Araç başarıyla kaldırılırsa, bu yöntem *pTool'u*siler.

## <a name="cusertoolsmanagersavestate"></a><a name="savestate"></a>CuserToolsManager::SaveState

Windows kayıt defterinde kullanıcı araçları yla ilgili bilgileri depolar.

```
BOOL SaveState(LPCTSTR lpszProfileName=NULL);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[içinde] Windows kayıt defteri anahtarına giden bir yol.

### <a name="return-value"></a>Dönüş Değeri

Devlet başarıyla kaydedilirse sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yöntem, `CUserToolsManager` Windows kayıt defterinde nesnenin geçerli durumunu depolar.

Genellikle, doğrudan bu yöntemi aramak gerekmez, [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate) uygulamanın çalışma alanı serileştirme sürecinin bir parçası olarak otomatik olarak çağırır.

## <a name="cusertoolsmanagersetdefext"></a><a name="setdefext"></a>CUserToolsManager::SetDefExt

**Dosya Aç** iletişim kutusunun [(CFileDialog Class)](../../mfc/reference/cfiledialog-class.md) **Özelleştir** iletişim kutusunun **Araçlar** sekmesindeki **Komut** alanında kullandığı varsayılan uzantıyı belirtir.

```
void SetDefExt(const CString& strDefExt);
```

### <a name="parameters"></a>Parametreler

*strDefExt*<br/>
[içinde] Varsayılan dosya adı uzantısını içeren bir metin dizesi.

### <a name="remarks"></a>Açıklamalar

Kullanıcı kullanıcı aracıyla ilişkilendirilecek bir uygulama seçtiğinde görüntülenen **Dosya Aç** iletişim kutusunda varsayılan dosya adı uzantısı belirtmek için bu yöntemi arayın. Varsayılan "exe"dir.

## <a name="cusertoolsmanagersetfilter"></a><a name="setfilter"></a>CuserToolsManager::SetFilter

**Dosya Aç** iletişim kutusunun [(CFileDialog Class)](../../mfc/reference/cfiledialog-class.md) **Özelleştir** iletişim kutusunun **Araçlar** sekmesindeki **Komut** alanında kullandığı dosya filtresini belirtir.

```
void SetFilter(const CString& strFilter);
```

### <a name="parameters"></a>Parametreler

*strFiltre*<br/>
[içinde] Filtreyi belirtir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx Sınıfı](../../mfc/reference/cwinappex-class.md)<br/>
[CuserTool Sınıfı](../../mfc/reference/cusertool-class.md)
