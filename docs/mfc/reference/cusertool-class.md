---
title: CUserTool sınıfı
ms.date: 11/04/2016
f1_keywords:
- CUserTool
- AFXUSERTOOL/CUserTool
- AFXUSERTOOL/CUserTool::CopyIconToClipboard
- AFXUSERTOOL/CUserTool::DrawToolIcon
- AFXUSERTOOL/CUserTool::GetCommand
- AFXUSERTOOL/CUserTool::GetCommandId
- AFXUSERTOOL/CUserTool::Invoke
- AFXUSERTOOL/CUserTool::Serialize
- AFXUSERTOOL/CUserTool::SetCommand
- AFXUSERTOOL/CUserTool::SetToolIcon
- AFXUSERTOOL/CUserTool::LoadDefaultIcon
- AFXUSERTOOL/CUserTool::m_strArguments
- AFXUSERTOOL/CUserTool::m_strInitialDirectory
- AFXUSERTOOL/CUserTool::m_strLabel
helpviewer_keywords:
- CUserTool [MFC], CopyIconToClipboard
- CUserTool [MFC], DrawToolIcon
- CUserTool [MFC], GetCommand
- CUserTool [MFC], GetCommandId
- CUserTool [MFC], Invoke
- CUserTool [MFC], Serialize
- CUserTool [MFC], SetCommand
- CUserTool [MFC], SetToolIcon
- CUserTool [MFC], LoadDefaultIcon
- CUserTool [MFC], m_strArguments
- CUserTool [MFC], m_strInitialDirectory
- CUserTool [MFC], m_strLabel
ms.assetid: 7c287d3e-d012-488d-b4e1-aa0f83f294bb
ms.openlocfilehash: 5bb0ae073b722c97e8e30158f8f7832fd88b2fbc
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58779046"
---
# <a name="cusertool-class"></a>CUserTool sınıfı

Kullanıcı aracı dış uygulamayı çalıştıran menü öğesidir. **Araçları** sekmesinde **Özelleştir** iletişim kutusu ( [CMFCToolBarsCustomizeDialog sınıfı](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)) kullanıcının kullanıcı araçları eklemesine ve adını, komut, bağımsız değişken belirtmenizi sağlar ve Her kullanıcı aracı için başlangıç dizini.

## <a name="syntax"></a>Sözdizimi

```
class CUserTool : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CUserTool::CopyIconToClipboard](#copyicontoclipboard)||
|[CUserTool::DrawToolIcon](#drawtoolicon)|Kullanıcı Aracı simgesi içinde belirtilen bir dikdörtgen çizer.|
|[CUserTool::GetCommand](#getcommand)|Kullanıcı aracı ile ilişkili komut metnini içeren bir dize döndürür.|
|[CUserTool::GetCommandId](#getcommandid)|Menü öğesi kullanıcı aracının komut Kimliğini döndürür.|
|[CUserTool::Invoke](#invoke)|Kullanıcı aracı ile ilişkili komutu yürütür.|
|[CUserTool::Serialize](#serialize)|Okur veya ya da bir arşivden bu nesneyi yazar. (Geçersiz kılmaları [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|
|[CUserTool::SetCommand](#setcommand)|Kullanıcı aracı ile ilişkili komutu ayarlar.|
|[CUserTool::SetToolIcon](#settoolicon)|Kullanıcı Aracı simgesi aracı ile ilişkili uygulama yükler.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CUserTool::LoadDefaultIcon](#loaddefaulticon)|Kullanıcı aracı için varsayılan simgeyi yükler.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CUserTool::m_strArguments](#m_strarguments)|Kullanıcı aracı için komut satırı bağımsız değişkenleri.|
|[CUserTool::m_strInitialDirectory](#m_strinitialdirectory)|Kullanıcı aracı için başlangıç dizini.|
|[CUserTool::m_strLabel](#m_strlabel)|Menü öğesi için araç görüntülenir aracı adı.|

## <a name="remarks"></a>Açıklamalar

Kullanıcı araçlarını uygulamanızdaki etkinleştirme hakkında daha fazla bilgi için bkz. [CUserToolsManager sınıfı](../../mfc/reference/cusertoolsmanager-class.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek bir aracından oluşturma işlemini gösterir. bir `CUserToolsManager` nesne, ayarlama `m_strLabel` üye değişkeni ve kullanıcı aracını çalıştıran uygulama kümesi. Bu kod parçacığı parçasıdır [Visual Studio gösterim örneği](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#35](../../mfc/codesnippet/cpp/cusertool-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CUserTool](../../mfc/reference/cusertool-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxusertool.h

##  <a name="copyicontoclipboard"></a>  CUserTool::CopyIconToClipboard

Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.

```
BOOL CopyIconToClipboard();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="drawtoolicon"></a>  CUserTool::DrawToolIcon

Kullanıcı Aracı simgesi belirtilen dikdörtgen merkezinde çizer.

```
void DrawToolIcon(
    CDC* pDC,
    const CRect& rectImage);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçi.

*rectImage*<br/>
[in] Simge görüntülenecek alanın koordinatları belirtir.

##  <a name="getcommand"></a>  CUserTool::GetCommand

Kullanıcı aracı ile ilişkili komut metnini içeren bir dize döndürür.

```
const CString& GetCommand() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru `CString` kullanıcı aracı ile ilişkili komut metnini içeren nesne.

##  <a name="getcommandid"></a>  CUserTool::GetCommandId

Kullanıcı aracı komut Kimliğini döndürür.

```
UINT GetCommandId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı bu aracı komut kimliği.

##  <a name="invoke"></a>  CUserTool::Invoke

Kullanıcı aracı ile ilişkili komutu yürütür.

```
virtual BOOL Invoke();
```

### <a name="return-value"></a>Dönüş Değeri

Komut başarıyla yürütüldü olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Çağrıları [ShellExecute](/windows/desktop/api/shellapi/nf-shellapi-shellexecutea) kullanıcı aracı ile ilişkili bir komutu yürütülemedi. Komut boş ise veya işlev başarısız [ShellExecute](/windows/desktop/api/shellapi/nf-shellapi-shellexecutea) başarısız olur.

##  <a name="loaddefaulticon"></a>  CUserTool::LoadDefaultIcon

Kullanıcı aracı için varsayılan simgeyi yükler.

```
virtual HICON LoadDefaultIcon();
```

### <a name="return-value"></a>Dönüş Değeri

Yüklü simgesi (HICON) ya da varsayılan simgeyi yüklenemezse NULL işleyici.

### <a name="remarks"></a>Açıklamalar

Bir kullanıcı tanımlı araç için bir simge aracının yürütülebilir dosyadan yüklenemiyor olduğunda framework bu yöntemi çağırır.

Kendi varsayılan Aracı simgesi sağlamak için bu yöntemi yok sayın.

##  <a name="m_strarguments"></a>  CUserTool::m_strArguments

Kullanıcı aracı için komut satırı bağımsız değişkenleri.

```
CString m_strArguments;
```

### <a name="remarks"></a>Açıklamalar

Çağırdığınızda Bu dize aracına geçirilen [CUserTool::Invoke](#invoke) veya bir kullanıcı bu aracı ile ilişkili komutu tıkladığında.

##  <a name="m_strinitialdirectory"></a>  CUserTool::m_strInitialDirectory

Kullanıcı aracı için başlangıç dizinini belirtir.

```
CString m_strInitialDirectory;
```

### <a name="remarks"></a>Açıklamalar

Bu değişken çağırdığınızda, aracın yürütülen başlangıç dizini belirtir [CUserTool::Invoke](#invoke) veya bir kullanıcı bu aracı ile ilişkili komutu tıkladığında.

##  <a name="m_strlabel"></a>  CUserTool::m_strLabel

Etiket menü öğesi için araç görüntülenir.

```
CString m_strLabel;
```

##  <a name="serialize"></a>  CUserTool::Serialize

Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

[in] *ar*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="setcommand"></a>  CUserTool::SetCommand

Kullanıcı aracı çalıştıran uygulama ayarlar.

```
void SetCommand(LPCTSTR lpszCmd);
```

### <a name="parameters"></a>Parametreler

*lpszCmd*<br/>
[in] Kullanıcı aracı ile ilişkilendirilecek yeni uygulamayı belirtir.

### <a name="remarks"></a>Açıklamalar

Kullanıcı aracı çalıştıran yeni bir uygulama ayarlamak için bu yöntemi çağırın. Yöntemi, eski simgesi yok eder ve belirtilen uygulamayı yeni bir simge yükler. Uygulamadan bir simge yüklenemiyor, çağırarak kullanıcı aracı için varsayılan simgeyi yükler [CUserTool::LoadDefaultIcon](#loaddefaulticon).

##  <a name="settoolicon"></a>  CUserTool::SetToolIcon

Kullanıcı Aracı simgesi aracını kullanan uygulamayı yükler.

```
virtual HICON SetToolIcon();
```

### <a name="return-value"></a>Dönüş Değeri

Yüklü simgesi için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Menü öğesi üzerinde görüntülenecek simge yüklemek için bu yöntemi çağırın. Bu yöntem aracını kullanan yürütülebilir dosya simge arar. Varsayılan bir simge yoksa simgesi sağlanan [CUserTool::LoadDefaultIcon](#loaddefaulticon) yerine kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx Class](../../mfc/reference/cwinappex-class.md)<br/>
[CUserToolsManager sınıfı](../../mfc/reference/cusertoolsmanager-class.md)
