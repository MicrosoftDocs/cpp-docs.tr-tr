---
description: 'Daha fazla bilgi edinin: Cuseraraçları Yöneticisi sınıfı'
title: Cuser, yönetici sınıfı
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
ms.openlocfilehash: 1c6b3b6ec2912a0093929ac117d878d54ed9757f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344958"
---
# <a name="cusertoolsmanager-class"></a>Cuser, yönetici sınıfı

Bir uygulamadaki [CUserTool sınıf](../../mfc/reference/cusertool-class.md) nesnelerinin koleksiyonunu tutar. Kullanıcı Aracı, dış uygulama çalıştıran bir menü öğesidir. `CUserToolsManager`Nesnesi, kullanıcının veya geliştiricinin uygulamaya Yeni Kullanıcı araçları eklemesini sağlar. Kullanıcı araçlarıyla ilişkili komutların yürütülmesini destekler ve ayrıca Windows kayıt defterindeki Kullanıcı araçlarıyla ilgili bilgileri kaydeder.

## <a name="syntax"></a>Syntax

```
class CUserToolsManager : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cuserdentitymanager:: Cuserbir yönetim Yöneticisi](#cusertoolsmanager)|Bir oluşturur `CUserToolsManager` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cuseraraçlar Manager:: CreateNewTool](#createnewtool)|Yeni bir Kullanıcı aracı oluşturur.|
|[Cuserdentitymanager:: FindTool](#findtool)|`CMFCUserTool`Belirtilen komut Kimliğiyle ilişkili nesneye yönelik işaretçiyi döndürür.|
|[Cuserdentitymanager:: GetArgumentsMenuID](#getargumentsmenuid)|**Özelleştirme** Iletişim kutusunun **Araçlar** sekmesindeki **BAĞıMSıZ değişkenler** menüsüyle ilişkili kaynak kimliğini döndürür.|
|[Cuserdentitymanager:: GetDefExt](#getdefext)|**Dosya Aç** iletişim kutusunun ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)), **Özelleştir** iletişim kutusunun **Araçlar** sekmesinde **komut** alanında kullandığı varsayılan uzantıyı döndürür.|
|[Cuserdentitymanager:: GetFilter](#getfilter)|**Dosya Aç** iletişim kutusunun ( [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md)), **Özelleştir** iletişim kutusunun **Araçlar** sekmesinde **komut** alanında kullandığı dosya filtresini döndürür.|
|[Cuserdentitymanager:: Getınitialdirmenuid](#getinitialdirmenuid)|**Özelleştir** Iletişim kutusunun **Araçlar** sekmesindeki **Ilk Dizin** menüsüyle ilişkili kaynak kimliğini döndürür.|
|[Cuseraraçlarý Manager:: GetMaxTools](#getmaxtools)|Uygulamada ayrılabilen en fazla Kullanıcı aracı sayısını döndürür.|
|[Cuserdentitymanager:: GetToolsEntryCmd](#gettoolsentrycmd)|Kullanıcı araçları için menü öğesi yer tutucusunun komut KIMLIĞINI döndürür.|
|[Cuseraraçlarý Manager:: GetUserTools](#getusertools)|Kullanıcı araçları listesine bir başvuru döndürür.|
|[Cuserdentitymanager:: ınvoketool](#invoketool)|Belirtilen komut KIMLIĞINE sahip Kullanıcı aracıyla ilişkili bir uygulamayı yürütür.|
|[Cuser\tools Manager:: ısusertoolcmd](#isusertoolcmd)|Bir komut KIMLIĞININ bir Kullanıcı aracıyla ilişkilendirilip ilişkilendirilmediğini belirler.|
|[Cuserdentitymanager:: LoadState](#loadstate)|Windows kayıt defterinden Kullanıcı araçları hakkında bilgi yükler.|
|[Cuser\tools Manager:: Movetoolın](#movetooldown)|Kullanıcı araçları listesinde belirtilen kullanıcı aracını aşağı kaydırır.|
|[Cuserdentitymanager:: MoveToolUp](#movetoolup)|Kullanıcı araçları listesinde belirtilen kullanıcı aracını yukarı kaydırır.|
|[Cuseraraçlar Manager:: RemoveTool](#removetool)|Belirtilen kullanıcı aracını uygulamadan kaldırır.|
|[Cuserdentitymanager:: Sava](#savestate)|Windows kayıt defterindeki Kullanıcı araçlarıyla ilgili bilgileri depolar.|
|[Cuserdentitymanager:: SetDefExt](#setdefext)|**Dosya Aç** iletişim kutusunun ( [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md)), **Özelleştir** iletişim kutusunun **Araçlar** sekmesinde **komut** alanında kullandığı varsayılan uzantıyı belirtir.|
|[Cuserdentitymanager:: SetFilter](#setfilter)|**Dosya Aç** iletişim kutusunun ( [CFileDialog Class](../../mfc/reference/cfiledialog-class.md)), **Özelleştir** iletişim kutusunun **Araçlar** sekmesinde **komut** alanında kullandığı dosya filtresini belirtir.|

## <a name="remarks"></a>Açıklamalar

Kullanıcı araçlarını uygulamanıza eklemek için şunları yapmanız gerekir:

1. Bir menü öğesini ve Kullanıcı aracı menü girişi için ilişkili bir komut KIMLIĞINI ayırın.

2. Bir kullanıcının uygulamanızda tanımlayabileceği her kullanıcı aracı için sıralı bir komut KIMLIĞI ayırın.

3. [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) metodunu çağırın ve şu parametreleri sağlayın: menü komut kimliği, ilk Kullanıcı aracı komut kimliği ve son kullanıcı aracı komut kimliği.

Uygulama başına yalnızca bir genel `CUserToolsManager` nesne olmalıdır.

Kullanıcı araçlarının bir örneği için bkz. VisualStudioDemo örnek projesi.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesnenin başvurusunun nasıl alınacağını `CUserToolsManager` ve Yeni Kullanıcı araçlarının nasıl oluşturulacağını göstermektedir. Bu kod parçacığı, [Visual Studio Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_VisualStudioDemo#38](../../mfc/codesnippet/cpp/cusertoolsmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CUserToolsManager`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxuseraraçları Yöneticisi. h

## <a name="cusertoolsmanagercreatenewtool"></a><a name="createnewtool"></a> Cuseraraçlar Manager:: CreateNewTool

Yeni bir Kullanıcı aracı oluşturur.

```
CUserTool* CreateNewTool();
```

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan kullanıcı aracına yönelik bir işaretçi veya Kullanıcı araçlarının sayısı maksimum değeri aşarsa NULL. Döndürülen tür, `CWinAppEx::EnableUserTools` *pToolRTC* parametresi olarak geçirilen türle aynıdır.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) çağrısında sağlanan aralıktaki ilk kullanılabilir menü komut kimliğini bulur ve Kullanıcı ARACıNı bu kimliğe atar.

Araç sayısı üst sınıra ulaştığında yöntem başarısız olur. Bu, Aralık içindeki tüm komut kimlikleri Kullanıcı araçlarına atandığında meydana gelir. [Cuseraraçlarý Manager:: GetMaxTools](#getmaxtools)öğesini çağırarak en fazla araç sayısını alabilirsiniz. [Cuseraraçlarý Manager:: GetUserTools](#getusertools) yöntemini çağırarak araçlar listesine erişebilirsiniz.

## <a name="cusertoolsmanagercusertoolsmanager"></a><a name="cusertoolsmanager"></a> Cuserdentitymanager:: Cuserbir yönetim Yöneticisi

Bir oluşturur `CUserToolsManager` . Her uygulamanın en çok bir Kullanıcı araçları Yöneticisi olmalıdır.

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

*Uıımdtoolsdummy*<br/>
'ndaki Çerçevenin Kullanıcı araçları menüsünün komut KIMLIĞI için yer tutucu olarak kullandığı işaretsiz bir tamsayı.

*Uıımdfirst*<br/>
'ndaki İlk Kullanıcı aracı komutu için komut KIMLIĞI.

*uiCmdLast*<br/>
'ndaki Son Kullanıcı aracı komutu için komut KIMLIĞI.

*pToolRTC*<br/>
'ndaki [Cuseraraçlar Manager:: CreateNewTool](#createnewtool) 'un oluşturduğu sınıf. Bu sınıfı kullanarak, varsayılan uygulama yerine türetilmiş bir [CUserTool sınıfı](../../mfc/reference/cusertool-class.md) türü kullanabilirsiniz.

*Uıargmenuid*<br/>
'ndaki Bağımsız değişkenler açılan menüsünün menü kaynak KIMLIĞI.

*Uııd*<br/>
'ndaki İlk dizin açılan menüsünün menü kaynak KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Bu oluşturucuyu çağırmayın. Bunun yerine, kullanıcı araçlarını etkinleştirmek için [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) komutunu çağırın ve ' a bir işaretçi almak için [CWinAppEx:: GetUserTools Manager](../../mfc/reference/cwinappex-class.md#getusertoolsmanager) ' ı çağırın `CUserToolsManager` . Daha fazla bilgi için bkz. [Kullanıcı tanımlı araçlar](../../mfc/user-defined-tools.md).

## <a name="cusertoolsmanagerfindtool"></a><a name="findtool"></a> Cuserdentitymanager:: FindTool

Belirtilen komut KIMLIĞIYLE ilişkili olan [CUserTool sınıfı](../../mfc/reference/cusertool-class.md) nesnesine yönelik işaretçiyi döndürür.

```
CUserTool* FindTool(UINT uiCmdId) const;
```

### <a name="parameters"></a>Parametreler

*Uıımıdıd*<br/>
'ndaki Bir menü komutu tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Eğer başarılı olursa bir [CUserTool sınıfı](../../mfc/reference/cusertool-class.md) veya `CUserTool` türetilmiş nesne işaretçisi; Aksi takdirde null.

### <a name="remarks"></a>Açıklamalar

`FindTool`Başarılı olduğunda döndürülen tür, [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)Için *pToolRTC* parametresinin türüyle aynıdır.

## <a name="cusertoolsmanagergetargumentsmenuid"></a><a name="getargumentsmenuid"></a> Cuserdentitymanager:: GetArgumentsMenuID

**Özelleştirme** Iletişim kutusunun **Araçlar** sekmesindeki **BAĞıMSıZ değişkenler** menüsüyle ilişkili kaynak kimliğini döndürür.

```
UINT GetArgumentsMenuID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir menü kaynağının tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

[CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) Için *Uıargmenuid* parametresi kaynağın kimliğini belirtir.

## <a name="cusertoolsmanagergetdefext"></a><a name="getdefext"></a> Cuserdentitymanager:: GetDefExt

**Dosya Aç** iletişim kutusunun ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)), **Özelleştir** iletişim kutusunun **Araçlar** sekmesinde **komut** alanında kullandığı varsayılan uzantıyı döndürür.

```
const CString& GetDefExt() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CString`Uzantıyı içeren nesneye bir başvuru.

## <a name="cusertoolsmanagergetfilter"></a><a name="getfilter"></a> Cuserdentitymanager:: GetFilter

**Dosya Aç** iletişim kutusunun ( [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md)), **Özelleştir** iletişim kutusunun **Araçlar** sekmesinde **komut** alanında kullandığı dosya filtresini döndürür.

```
const CString& GetFilter() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CString`Filtreyi içeren nesnesine bir başvuru.

## <a name="cusertoolsmanagergetinitialdirmenuid"></a><a name="getinitialdirmenuid"></a> Cuserdentitymanager:: Getınitialdirmenuid

**Özelleştir** Iletişim kutusunun **Araçlar** sekmesindeki **Ilk Dizin** menüsüyle ilişkili kaynak kimliğini döndürür.

```
UINT GetInitialDirMenuID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir menü kaynak tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

Döndürülen KIMLIK, [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)öğesinin *Uinitdirmenuid* parametresinde belirtilir.

## <a name="cusertoolsmanagergetmaxtools"></a><a name="getmaxtools"></a> Cuseraraçlarý Manager:: GetMaxTools

Uygulamada ayrılabilen en fazla Kullanıcı aracı sayısını döndürür.

```
int GetMaxTools() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılabilen en fazla kullanıcı araç sayısı.

### <a name="remarks"></a>Açıklamalar

Uygulamada ayrılabilen en fazla araç sayısını almak için bu yöntemi çağırın. Bu sayı, [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)'A geçirdiğiniz *Uıımdlast* parametreleri aracılığıyla *uiCmdFirst* aralığındaki kimlik sayısıdır.

## <a name="cusertoolsmanagergettoolsentrycmd"></a><a name="gettoolsentrycmd"></a> Cuserdentitymanager:: GetToolsEntryCmd

Kullanıcı araçları için menü öğesi yer tutucusunun komut KIMLIĞINI döndürür.

```
UINT GetToolsEntryCmd() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yer tutucunun komut KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Kullanıcı araçları 'nı etkinleştirmek için [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)komutunu çağırın. *Uıımdtoolsdummy* parametresi, Araçlar giriş KOMUTUNUN komut kimliğini belirtir. Bu yöntem, Araçlar girdisi komut KIMLIĞINI döndürür. Bu KIMLIğIN bir menüde kullanıldığı her yerde, menü göründüğünde Kullanıcı araçlarının listesi ile değiştirilmiştir.

## <a name="cusertoolsmanagergetusertools"></a><a name="getusertools"></a> Cuseraraçlarý Manager:: GetUserTools

Kullanıcı araçları listesine bir başvuru döndürür.

```
const CObList& GetUserTools() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı araçlarının listesini içeren bir [CObList sınıfı](../../mfc/reference/coblist-class.md) nesnesine bir const başvurusu.

### <a name="remarks"></a>Açıklamalar

[Cuseraraçlarý Manager](../../mfc/reference/cusertoolsmanager-class.md) nesnesinin koruduğu Kullanıcı araçlarının listesini almak için bu yöntemi çağırın. Her Kullanıcı Aracı, [CUserTool sınıfı](../../mfc/reference/cusertool-class.md) türünde bir nesne veya öğesinden türetilmiş bir tür tarafından temsil edilir `CUserTool` . Kullanıcı araçlarını etkinleştirmek için [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) öğesini çağırdığınızda tür *pToolRTC* parametresi tarafından belirtilir.

## <a name="cusertoolsmanagerinvoketool"></a><a name="invoketool"></a> Cuserdentitymanager:: ınvoketool

Belirtilen komut KIMLIĞINE sahip Kullanıcı aracıyla ilişkili bir uygulamayı yürütür.

```
BOOL InvokeTool(UINT uiCmdId);
```

### <a name="parameters"></a>Parametreler

*Uıımıdıd*<br/>
'ndaki Kullanıcı aracıyla ilişkili menü komut KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı aracıyla ilişkili komut başarıyla yürütülürse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*Uıımdıd* tarafından BELIRTILEN komut kimliğine sahip Kullanıcı aracıyla ilişkili bir uygulamayı yürütmek için bu yöntemi çağırın.

## <a name="cusertoolsmanagerisusertoolcmd"></a><a name="isusertoolcmd"></a> Cuser\tools Manager:: ısusertoolcmd

Bir komut KIMLIĞININ bir Kullanıcı aracıyla ilişkilendirilip ilişkilendirilmediğini belirler.

```
BOOL IsUserToolCmd(UINT uiCmdId) const;
```

### <a name="parameters"></a>Parametreler

*Uıımıdıd*<br/>
'ndaki Menü öğesinin komut KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Belirli bir komut KIMLIĞI bir Kullanıcı aracıyla ilişkilendirilirse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, verilen komut KIMLIĞININ komut KIMLIĞI aralığında olup olmadığını denetler. Kullanıcı araçlarını etkinleştirmek için [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) öğesini çağırdığınızda aralığı belirtirsiniz.

## <a name="cusertoolsmanagerloadstate"></a><a name="loadstate"></a> Cuserdentitymanager:: LoadState

Windows kayıt defterinden Kullanıcı araçları hakkında bilgi yükler.

```
BOOL LoadState(LPCTSTR lpszProfileName=NULL);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
'ndaki Windows kayıt defteri anahtarının yolu.

### <a name="return-value"></a>Dönüş Değeri

Durum başarıyla yüklenmişse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CUserToolsManager` Windows kayıt defterinden nesnenin durumunu yükler.

Genellikle, bu yöntemi doğrudan çağırmayın. [CWinAppEx:: LoadState](../../mfc/reference/cwinappex-class.md#loadstate) , çalışma alanı başlatma sürecinin bir parçası olarak çağırır.

## <a name="cusertoolsmanagermovetooldown"></a><a name="movetooldown"></a> Cuser\tools Manager:: Movetoolın

Kullanıcı araçları listesinde belirtilen kullanıcı aracını aşağı kaydırır.

```
BOOL MoveToolDown(CUserTool* pTool);
```

### <a name="parameters"></a>Parametreler

*pTool*<br/>
'ndaki Taşınacak Kullanıcı aracını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı aracı başarıyla taşınmışsa, sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*PTool* 'un belirttiği araç iç listede değilse veya araç listede en son ise yöntem başarısız olur.

## <a name="cusertoolsmanagermovetoolup"></a><a name="movetoolup"></a> Cuserdentitymanager:: MoveToolUp

Kullanıcı araçları listesinde belirtilen kullanıcı aracını yukarı kaydırır.

```
BOOL MoveToolUp(CUserTool* pTool);
```

### <a name="parameters"></a>Parametreler

*pTool*<br/>
'ndaki Taşınacak Kullanıcı aracını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı aracı başarıyla taşınmışsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*PTool* parametresinin belirttiği araç iç listede değilse veya araç listedeki ilk araç öğesi ise, yöntemi başarısız olur.

## <a name="cusertoolsmanagerremovetool"></a><a name="removetool"></a> Cuseraraçlar Manager:: RemoveTool

Belirtilen kullanıcı aracını uygulamadan kaldırır.

```
BOOL RemoveTool(CUserTool* pTool);
```

### <a name="parameters"></a>Parametreler

*pTool*<br/>
[in, out] Kaldırılacak Kullanıcı aracına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Araç başarıyla kaldırılırsa doğru. Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Araç başarıyla kaldırılırsa, bu yöntem *pTool*'u siler.

## <a name="cusertoolsmanagersavestate"></a><a name="savestate"></a> Cuserdentitymanager:: Sava

Windows kayıt defterindeki Kullanıcı araçlarıyla ilgili bilgileri depolar.

```
BOOL SaveState(LPCTSTR lpszProfileName=NULL);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
'ndaki Windows kayıt defteri anahtarı için bir yol.

### <a name="return-value"></a>Dönüş Değeri

Durum başarıyla kaydedildiyse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yöntemi, `CUserToolsManager` Windows kayıt defterinde nesnenin geçerli durumunu depolar.

Genellikle, bu yöntemi doğrudan çağırmanız gerekmez, [CWinAppEx:: sav,](../../mfc/reference/cwinappex-class.md#savestate) uygulamanın çalışma alanı serileştirme sürecinin bir parçası olarak otomatik olarak çağırır.

## <a name="cusertoolsmanagersetdefext"></a><a name="setdefext"></a> Cuserdentitymanager:: SetDefExt

**Dosya Aç** iletişim kutusunun ( [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md)), **Özelleştir** iletişim kutusunun **Araçlar** sekmesinde **komut** alanında kullandığı varsayılan uzantıyı belirtir.

```cpp
void SetDefExt(const CString& strDefExt);
```

### <a name="parameters"></a>Parametreler

*strDefExt*<br/>
'ndaki Varsayılan dosya adı uzantısını içeren bir metin dizesi.

### <a name="remarks"></a>Açıklamalar

Kullanıcı aracıyla ilişkilendirilecek uygulamayı seçtiğinde görüntülenecek olan **Dosya Aç** iletişim kutusunda varsayılan dosya adı uzantısını belirtmek için bu yöntemi çağırın. Varsayılan değer "exe" dir.

## <a name="cusertoolsmanagersetfilter"></a><a name="setfilter"></a> Cuserdentitymanager:: SetFilter

**Dosya Aç** iletişim kutusunun ( [CFileDialog Class](../../mfc/reference/cfiledialog-class.md)), **Özelleştir** iletişim kutusunun **Araçlar** sekmesinde **komut** alanında kullandığı dosya filtresini belirtir.

```cpp
void SetFilter(const CString& strFilter);
```

### <a name="parameters"></a>Parametreler

*strFilter*<br/>
'ndaki Filtreyi belirtir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md)<br/>
[CUserTool sınıfı](../../mfc/reference/cusertool-class.md)
