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
ms.openlocfilehash: 2da34eacb7524168f16d05248eee97422a1fb770
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380769"
---
# <a name="cusertoolsmanager-class"></a>CUserToolsManager sınıfı

Koleksiyonunu tutar [CUserTool sınıfı](../../mfc/reference/cusertool-class.md) bir uygulamadaki nesneler. Kullanıcı aracı dış uygulamayı çalıştıran menü öğesidir. `CUserToolsManager` Kullanıcı veya uygulamaya yeni kullanıcı araçları eklemesine Geliştirici nesnesi sağlar. Kullanıcı araçlarıyla ilişkili komutların yürütülmesini destekler ve ayrıca Windows kayıt defterine kullanıcı araçlarıyla ilgili bilgileri kaydeder.

## <a name="syntax"></a>Sözdizimi

```
class CUserToolsManager : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CUserToolsManager::CUserToolsManager](#cusertoolsmanager)|Oluşturur bir `CUserToolsManager`.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CUserToolsManager::CreateNewTool](#createnewtool)|Yeni bir kullanıcı aracı oluşturur.|
|[CUserToolsManager::FindTool](#findtool)|Bir işaretçi geri döndürür `CMFCUserTool` belirtilen komut kimliğiyle ilişkili nesne|
|[CUserToolsManager::GetArgumentsMenuID](#getargumentsmenuid)|İlişkili olduğu kaynak kimliği döndürür **bağımsız değişkenleri** menüsünde **Araçları** sekmesinde **Özelleştir** iletişim kutusu.|
|[CUserToolsManager::GetDefExt](#getdefext)|Varsayılan uzantı döndüren **Dosya Aç** iletişim kutusu ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) kullanır **komut** alanını **Araçları** sekmesi **Özelleştir** iletişim kutusu.|
|[CUserToolsManager::GetFilter](#getfilter)|Dosya Filtresi döndüren **Dosya Aç** iletişim kutusu ( [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md)) kullanır **komut** alanını **Araçları** sekmesi **Özelleştir** iletişim kutusu.|
|[CUserToolsManager::GetInitialDirMenuID](#getinitialdirmenuid)|İlişkili olduğu kaynak kimliği döndürür **başlangıç dizini** menüsünde **Araçları** sekmesinde **Özelleştir** iletişim kutusu.|
|[CUserToolsManager::GetMaxTools](#getmaxtools)|Uygulamada ayrılabilen kullanıcı araçlarını maksimum sayısını döndürür.|
|[CUserToolsManager::GetToolsEntryCmd](#gettoolsentrycmd)|Kullanıcı araçlarını için menü öğesi yer tutucu komut Kimliğini döndürür.|
|[CUserToolsManager::GetUserTools](#getusertools)|Kullanıcı araçlarını listesine bir başvuru döndürür.|
|[CUserToolsManager::InvokeTool](#invoketool)|Belirtilen komut kimliğe sahip kullanıcı aracı ile ilişkili bir uygulama yürütüldüğünde|
|[CUserToolsManager::IsUserToolCmd](#isusertoolcmd)|Komut kimliği bir kullanıcı aracı ile ilişkili olup olmadığını belirler.|
|[CUserToolsManager::LoadState](#loadstate)|Kullanıcı araçlarıyla ilgili bilgileri Windows kayıt defterinden yükler.|
|[CUserToolsManager::MoveToolDown](#movetooldown)|Belirtilen kullanıcı aracı kullanıcı araçlarını listesinde aşağı taşır.|
|[CUserToolsManager::MoveToolUp](#movetoolup)|Belirtilen kullanıcı aracı kullanıcı araçlarını listesinde yukarı taşır.|
|[CUserToolsManager::RemoveTool](#removetool)|Belirtilen kullanıcı aracı, uygulamadan kaldırır.|
|[CUserToolsManager::SaveState](#savestate)|Windows kayıt defterine kullanıcı araçlarıyla ilgili bilgileri depolar.|
|[CUserToolsManager::SetDefExt](#setdefext)|Varsayılan uzantı belirtir, **Dosya Aç** iletişim kutusu ( [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md)) kullanır **komut** alanını **Araçları** sekmesi ' ın **Özelleştir** iletişim kutusu.|
|[CUserToolsManager::SetFilter](#setfilter)|Dosya filtreleme belirtir **Dosya Aç** iletişim kutusu ( [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md)) kullanır **komut** alanını **Araçları** sekmesi **Özelleştir** iletişim kutusu.|

## <a name="remarks"></a>Açıklamalar

Kullanıcı araçlarını uygulamanıza eklemenize için yapmanız gerekir:

1. Bir menü öğesi ve bir ilişkili komut kimliği için kullanıcı aracı menü girdisi saklı tutarız.

2. Bir kullanıcı uygulamanıza tanımlayabileceğiniz her kullanıcı aracı için bir sıralı komut kimliği saklı tutarız.

3. Çağrı [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) yöntemi ve aşağıdaki parametreleri girin: menü komut kimliği, ilk kullanıcı aracı komut kimliği ve son kullanıcı aracı komut kimliği.

Bulunmamalıdır yalnızca bir genel `CUserToolsManager` uygulama başına nesne.

Kullanıcı araçlarını örneği için VisualStudioDemo kodunuzla bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir başvuru almak gösterilmiştir bir `CUserToolsManager` nesne ve yeni kullanıcı araçları oluşturma. Bu kod parçacığı parçasıdır [Visual Studio gösterim örneği](../../visual-cpp-samples.md).

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

Yeni oluşturulan kullanıcı aracı ya da kullanıcı araçlarını sayısı üst sınırı aşarsa NULL bir işaretçi. Döndürülen türü geçirilir türü aynıdır `CWinAppEx::EnableUserTools` olarak *pToolRTC* parametresi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem çağrısında sağlanan aralıktaki ilk kullanılabilir menü komut Kimliğini bulur, [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) ve kullanıcı aracı, bu kimliği atar.

Araçlar sayısı üst sınıra ulaştı yöntemi başarısız olur. Kullanıcı araçlarını aralıktaki tüm komut kimlikleri atandığında gerçekleşir. Çağırarak araçları sayısı alabilirsiniz [CUserToolsManager::GetMaxTools](#getmaxtools). Çağırarak araçları listesine erişim sağlayabilmek için [CUserToolsManager::GetUserTools](#getusertools) yöntemi.

##  <a name="cusertoolsmanager"></a>  CUserToolsManager::CUserToolsManager

Oluşturur bir `CUserToolsManager`. Her uygulama, en fazla bir kullanıcı araçları Yöneticisi olması gerekir.

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
[in] Framework kullanıcı Araçlar menüsünden komut kimliği için bir yer tutucu olarak kullanan bir işaretsiz tamsayı.

*uiCmdFirst*<br/>
[in] İlk kullanıcı aracı komutu için komut kimliği.

*uiCmdLast*<br/>
[in] Son kullanıcı aracı komutu için komut kimliği.

*pToolRTC*<br/>
[in] Sınıfı, [CUserToolsManager::CreateNewTool](#createnewtool) oluşturur. Bu sınıfı kullanarak, türetilmiş bir tür kullanabilirsiniz [CUserTool sınıfı](../../mfc/reference/cusertool-class.md) yerine varsayılan uygulaması.

*uArgMenuID*<br/>
[in] Bağımsız değişken açılan menü menü kaynak kimliği.

*uInitDirMenuID*<br/>
[in] Başlangıç dizini açılan menü menü kaynak kimliği.

### <a name="remarks"></a>Açıklamalar

Bu oluşturucu çağırmanız gerekmez. Bunun yerine çağrı [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) kullanıcı Araçları'nı etkinleştirin ve çağrı [CWinAppEx::GetUserToolsManager](../../mfc/reference/cwinappex-class.md#getusertoolsmanager) bir işaretçi alma için `CUserToolsManager`. Daha fazla bilgi için [kullanıcı tanımlı Araçlar](../../mfc/user-defined-tools.md).

##  <a name="findtool"></a>  CUserToolsManager::FindTool

Bir işaretçi geri döndürür [CUserTool sınıfı](../../mfc/reference/cusertool-class.md) belirtilen komut kimliğiyle ilişkili nesne

```
CUserTool* FindTool(UINT uiCmdId) const;
```

### <a name="parameters"></a>Parametreler

*uiCmdId*<br/>
[in] Menü komut tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [CUserTool sınıfı](../../mfc/reference/cusertool-class.md) veya `CUserTool`-türetilmiş bir nesneye, başarı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Zaman `FindTool` olan başarılı, döndürülen tür ile aynı türdür *pToolRTC* parametresi [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).

##  <a name="getargumentsmenuid"></a>  CUserToolsManager::GetArgumentsMenuID

İlişkili olduğu kaynak kimliği döndürür **bağımsız değişkenleri** menüsünde **Araçları** sekmesinde **Özelleştir** iletişim kutusu.

```
UINT GetArgumentsMenuID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir menü kaynağı tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

*UArgMenuID* parametresinin [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) kaynak Kimliğini belirtir.

##  <a name="getdefext"></a>  CUserToolsManager::GetDefExt

Varsayılan uzantı döndüren **Dosya Aç** iletişim kutusu ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) kullanır **komut** alanını **Araçları** sekmesi **Özelleştir** iletişim kutusu.

```
const CString& GetDefExt() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru `CString` uzantıyı içeren nesne.

##  <a name="getfilter"></a>  CUserToolsManager::GetFilter

Dosya Filtresi döndüren **Dosya Aç** iletişim kutusu ( [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md)) kullanır **komut** alanını **Araçları** sekmesi **Özelleştir** iletişim kutusu.

```
const CString& GetFilter() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru `CString` filtre içeren nesne.

##  <a name="getinitialdirmenuid"></a>  CUserToolsManager::GetInitialDirMenuID

İlişkili olduğu kaynak kimliği döndürür **başlangıç dizini** menüsünde **Araçları** sekmesinde **Özelleştir** iletişim kutusu.

```
UINT GetInitialDirMenuID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir menü kaynak tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

Döndürülen kimliği belirtilen *uInitDirMenuID* parametresinin [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).

##  <a name="getmaxtools"></a>  CUserToolsManager::GetMaxTools

Uygulamada ayrılabilen kullanıcı araçlarını maksimum sayısını döndürür.

```
int GetMaxTools() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılabilen kullanıcı araçlarını maksimum sayısı.

### <a name="remarks"></a>Açıklamalar

Uygulamada ayrılabilen araçları maksimum sayısını almak için bu yöntemi çağırın. Bu sayı kimlikleri aralığında sayısıdır *uiCmdFirst* aracılığıyla *uiCmdLast* geçirdiğiniz parametreler [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).

##  <a name="gettoolsentrycmd"></a>  CUserToolsManager::GetToolsEntryCmd

Kullanıcı araçlarını için menü öğesi yer tutucu komut Kimliğini döndürür.

```
UINT GetToolsEntryCmd() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yer tutucu komut kimliği.

### <a name="remarks"></a>Açıklamalar

Kullanıcı araçlarını etkinleştirmek için çağrı [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools). *UiCmdToolsDummy* parametresi araçları giriş komutu komut Kimliğini belirtir. Bu yöntem araçları giriş komut kimliği döndürür Bu kimliği bir menüde kullanıldığı her yerde, menü görüntülendiğinde kullanıcı araçlarını listesi tarafından değiştirilir.

##  <a name="getusertools"></a>  CUserToolsManager::GetUserTools

Kullanıcı araçlarını listesine bir başvuru döndürür.

```
const CObList& GetUserTools() const;
```

### <a name="return-value"></a>Dönüş Değeri

Const başvuru bir [CObList sınıfı](../../mfc/reference/coblist-class.md) kullanıcı araçlarını listesini içeren nesne.

### <a name="remarks"></a>Açıklamalar

Kullanıcı listesini almak için bu yöntemi araçları çağrı [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) nesnesini saklar. Her kullanıcı aracı türünde bir nesne tarafından temsil edilen [CUserTool sınıfı](../../mfc/reference/cusertool-class.md) veya türetilmiş bir tür `CUserTool`. Türü tarafından belirtilen *pToolRTC* çağırdığınızda parametresi [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) kullanıcı araçlarını etkinleştirmek için.

##  <a name="invoketool"></a>  CUserToolsManager::InvokeTool

Belirtilen komut kimliğe sahip kullanıcı aracı ile ilişkili bir uygulama yürütüldüğünde

```
BOOL InvokeTool(UINT uiCmdId);
```

### <a name="parameters"></a>Parametreler

*uiCmdId*<br/>
[in] Kullanıcı aracı ile ilişkili menü komut kimliği.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı aracı ile ilişkili komutu sorunsuz yürüttüğünü olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem kullanıcıyla ilişkili bir uygulama yürüttüklerinde aracı çağrı tarafından belirtilen komut kimliği olan *uiCmdId*.

##  <a name="isusertoolcmd"></a>  CUserToolsManager::IsUserToolCmd

Komut kimliği bir kullanıcı aracı ile ilişkili olup olmadığını belirler.

```
BOOL IsUserToolCmd(UINT uiCmdId) const;
```

### <a name="parameters"></a>Parametreler

*uiCmdId*<br/>
[in] Menü öğesinin komut kimliği.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen komut kimliği bir kullanıcı aracı ile ilişkili ise sıfır olmayan; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen komut kimliği komut kimliği aralık içinde olup olmadığını denetler. Çağırdığınızda aralığını belirtin [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) kullanıcı araçlarını etkinleştirmek için.

##  <a name="loadstate"></a>  CUserToolsManager::LoadState

Kullanıcı araçlarıyla ilgili bilgileri Windows kayıt defterinden yükler.

```
BOOL LoadState(LPCTSTR lpszProfileName=NULL);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[in] Windows kayıt defteri anahtarının yolu.

### <a name="return-value"></a>Dönüş Değeri

Durumu başarıyla yüklendi olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem durumunu yükler `CUserToolsManager` Windows kayıt defterinden nesne.

Genellikle, bu yöntemi doğrudan çağırmanız gerekmez. [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate) çalışma başlatma işleminin parçası olarak çağırır.

##  <a name="movetooldown"></a>  CUserToolsManager::MoveToolDown

Belirtilen kullanıcı aracı kullanıcı araçlarını listesinde aşağı taşır.

```
BOOL MoveToolDown(CUserTool* pTool);
```

### <a name="parameters"></a>Parametreler

*pTool*<br/>
[in] Kullanıcı aracı taşımak için belirtir.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı aracı başarıyla taşındıktan sonra olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Yöntemi, başarısız olur. araç, *pTool* belirtir iç listesinde değil veya listesinin sonunda bir araçtır.

##  <a name="movetoolup"></a>  CUserToolsManager::MoveToolUp

Belirtilen kullanıcı aracı kullanıcı araçlarını listesinde yukarı taşır.

```
BOOL MoveToolUp(CUserTool* pTool);
```

### <a name="parameters"></a>Parametreler

*pTool*<br/>
[in] Kullanıcı aracı taşımak için belirtir.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı aracı başarıyla taşındı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Yöntemi, başarısız olur. araç, *pTool* parametresinin belirttiği değil iç listesinde veya aracı ilk aracı öğe listesinde ise.

##  <a name="removetool"></a>  CUserToolsManager::RemoveTool

Belirtilen kullanıcı aracı, uygulamadan kaldırır.

```
BOOL RemoveTool(CUserTool* pTool);
```

### <a name="parameters"></a>Parametreler

*pTool*<br/>
[out içinde] Kaldırılacak kullanıcı aracı için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Aracı başarıyla kaldırılırsa TRUE. Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Aracı başarıyla kaldırılırsa, bu yöntem siler *pTool*.

##  <a name="savestate"></a>  CUserToolsManager::SaveState

Windows kayıt defterine kullanıcı araçlarıyla ilgili bilgileri depolar.

```
BOOL SaveState(LPCTSTR lpszProfileName=NULL);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[in] Windows kayıt defteri anahtarı bir yolu.

### <a name="return-value"></a>Dönüş Değeri

Durumu başarıyla kaydedildi olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Yöntem geçerli durumunu depolar `CUserToolsManager` Windows kayıt defterinde nesne.

Genellikle, bu yöntemi doğrudan çağırmanız gerekmez [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate) uygulama çalışma alanı seri hale getirme sürecinin bir parçası olarak otomatik olarak çağırır.

##  <a name="setdefext"></a>  CUserToolsManager::SetDefExt

Varsayılan uzantı belirtir, **Dosya Aç** iletişim kutusu ( [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md)) kullanır **komut** alanını **Araçları** sekmesi ' ın **Özelleştir** iletişim kutusu.

```
void SetDefExt(const CString& strDefExt);
```

### <a name="parameters"></a>Parametreler

*strDefExt*<br/>
[in] Varsayılan dosya adı uzantısını içeren bir metin dizesi.

### <a name="remarks"></a>Açıklamalar

Bir varsayılan dosya adı uzantısı belirtmek için bu yöntemi çağırın **Dosya Aç** kullanıcı aracı ile ilişkilendirmek için bir uygulama kullanıcının seçtiği kurduğunuzda gösterilen iletişim kutusu. "Exe" varsayılandır.

##  <a name="setfilter"></a>  CUserToolsManager::SetFilter

Dosya filtreleme belirtir **Dosya Aç** iletişim kutusu ( [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md)) kullanır **komut** alanını **Araçları** sekmesi **Özelleştir** iletişim kutusu.

```
void SetFilter(const CString& strFilter);
```

### <a name="parameters"></a>Parametreler

*strFilter*<br/>
[in] Filtreyi belirtir.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx Sınıfı](../../mfc/reference/cwinappex-class.md)<br/>
[CUserTool Sınıfı](../../mfc/reference/cusertool-class.md)
