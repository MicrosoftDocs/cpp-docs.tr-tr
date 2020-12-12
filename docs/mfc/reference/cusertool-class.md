---
description: 'Daha fazla bilgi edinin: CUserTool sınıfı'
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
ms.openlocfilehash: 1a05d89543bdf3c0f873dadf9d2fbffb87ce680f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318513"
---
# <a name="cusertool-class"></a>CUserTool sınıfı

Kullanıcı Aracı, dış uygulama çalıştıran bir menü öğesidir. **Özelleştir** Iletişim kutusunun **Araçlar** sekmesi ( [CMFCToolBarsCustomizeDialog sınıfı](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)), kullanıcının Kullanıcı araçları eklemesini ve her kullanıcı aracı için ad, komut, bağımsız değişkenler ve başlangıç dizinini belirtmesini sağlar.

## <a name="syntax"></a>Syntax

```
class CUserTool : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CUserTool:: CopyIconToClipboard](#copyicontoclipboard)||
|[CUserTool::D rawToolIcon](#drawtoolicon)|Kullanıcı araç simgesini belirtilen dikdörtgende çizer.|
|[CUserTool:: GetCommand](#getcommand)|Kullanıcı aracıyla ilişkili komutun metnini içeren bir dize döndürür.|
|[CUserTool:: Getcommandıd](#getcommandid)|Kullanıcı aracının menü öğesinin komut KIMLIĞINI döndürür.|
|[CUserTool:: Invoke](#invoke)|Kullanıcı aracıyla ilişkili komutu yürütür.|
|[CUserTool:: serileştirme](#serialize)|Bu nesneyi veya bir arşivden okur veya yazar. ( [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize)geçersiz kılar.)|
|[CUserTool:: Setkomutu](#setcommand)|Kullanıcı aracıyla ilişkili komutu ayarlar.|
|[CUserTool:: SetToolIcon](#settoolicon)|Araçla ilişkili uygulamadan Kullanıcı aracı simgesini yükler.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CUserTool:: LoadDefaultIcon](#loaddefaulticon)|Bir Kullanıcı aracı için varsayılan simgeyi yükler.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CUserTool:: m_strArguments](#m_strarguments)|Kullanıcı aracı için komut satırı bağımsız değişkenleri.|
|[CUserTool:: m_strInitialDirectory](#m_strinitialdirectory)|Kullanıcı aracı için başlangıç dizini.|
|[CUserTool:: m_strLabel](#m_strlabel)|Araç için menü öğesinde görüntülenen araç adı.|

## <a name="remarks"></a>Açıklamalar

Uygulamanızdaki Kullanıcı araçlarının nasıl etkinleştirileceği hakkında daha fazla bilgi için bkz. [Cuseraraçlarý Manager sınıfı](../../mfc/reference/cusertoolsmanager-class.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesnesinden bir araç oluşturmayı `CUserToolsManager` , `m_strLabel` üye değişkenini ayarlamayı ve Kullanıcı aracının çalıştırdığı uygulamayı nasıl ayarlayabileceğinizi gösterir. Bu kod parçacığı, [Visual Studio Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_VisualStudioDemo#35](../../mfc/codesnippet/cpp/cusertool-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CUserTool](../../mfc/reference/cusertool-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxusertool. h

## <a name="cusertoolcopyicontoclipboard"></a><a name="copyicontoclipboard"></a> CUserTool:: CopyIconToClipboard

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

```
BOOL CopyIconToClipboard();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cusertooldrawtoolicon"></a><a name="drawtoolicon"></a> CUserTool::D rawToolIcon

Belirtilen dikdörtgenin ortasına Kullanıcı araç simgesini çizer.

```cpp
void DrawToolIcon(
    CDC* pDC,
    const CRect& rectImage);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*rectImage*<br/>
'ndaki Simgenin görüntüleneceği alanın koordinatlarını belirtir.

## <a name="cusertoolgetcommand"></a><a name="getcommand"></a> CUserTool:: GetCommand

Kullanıcı aracıyla ilişkili komutun metnini içeren bir dize döndürür.

```
const CString& GetCommand() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CString`Kullanıcı aracıyla ilişkili komutun metnini içeren nesnesine bir başvuru.

## <a name="cusertoolgetcommandid"></a><a name="getcommandid"></a> CUserTool:: Getcommandıd

Kullanıcı aracının komut KIMLIĞINI döndürür.

```
UINT GetCommandId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu Kullanıcı aracının komut KIMLIĞI.

## <a name="cusertoolinvoke"></a><a name="invoke"></a> CUserTool:: Invoke

Kullanıcı aracıyla ilişkili komutu yürütür.

```
virtual BOOL Invoke();
```

### <a name="return-value"></a>Dönüş Değeri

Komut başarıyla yürütülürse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kullanıcı aracıyla ilişkili bir komutu yürütmek için [ShellExecute](/windows/win32/api/shellapi/nf-shellapi-shellexecutew) ' i çağırır. Komut boşsa veya [ShellExecute](/windows/win32/api/shellapi/nf-shellapi-shellexecutew) başarısız olursa işlev başarısız olur.

## <a name="cusertoolloaddefaulticon"></a><a name="loaddefaulticon"></a> CUserTool:: LoadDefaultIcon

Bir Kullanıcı aracı için varsayılan simgeyi yükler.

```
virtual HICON LoadDefaultIcon();
```

### <a name="return-value"></a>Dönüş Değeri

Yüklenen simgenin (HıCON) bir tutamacı veya varsayılan simge yüklenemezse NULL.

### <a name="remarks"></a>Açıklamalar

Framework, aracın yürütülebilir dosyasındaki kullanıcı tanımlı bir araç için bir simge yükleyemadığında bu yöntemi çağırır.

Kendi varsayılan araç simgenizi sağlamak için bu yöntemi geçersiz kılın.

## <a name="cusertoolm_strarguments"></a><a name="m_strarguments"></a> CUserTool:: m_strArguments

Kullanıcı aracı için komut satırı bağımsız değişkenleri.

```
CString m_strArguments;
```

### <a name="remarks"></a>Açıklamalar

Bu dize, [CUserTool:: Invoke](#invoke) ' i çağırdığınızda veya bir Kullanıcı bu araçla ilişkili komutu tıklattığında araca geçirilir.

## <a name="cusertoolm_strinitialdirectory"></a><a name="m_strinitialdirectory"></a> CUserTool:: m_strInitialDirectory

Kullanıcı aracının başlangıç dizinini belirtir.

```
CString m_strInitialDirectory;
```

### <a name="remarks"></a>Açıklamalar

Bu değişken, [CUserTool:: Invoke](#invoke) ' i çağırdığınızda veya bir Kullanıcı bu araçla ilişkili komuta tıkladığında, aracının üzerinde çalıştırdığı başlangıç dizinini belirtir.

## <a name="cusertoolm_strlabel"></a><a name="m_strlabel"></a> CUserTool:: m_strLabel

Araç için menü öğesinde görüntülenen etiket.

```
CString m_strLabel;
```

## <a name="cusertoolserialize"></a><a name="serialize"></a> CUserTool:: serileştirme

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

'ndaki *ar*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cusertoolsetcommand"></a><a name="setcommand"></a> CUserTool:: Setkomutu

Kullanıcı aracının çalıştırdığı uygulamayı ayarlar.

```cpp
void SetCommand(LPCTSTR lpszCmd);
```

### <a name="parameters"></a>Parametreler

*lpszCmd*<br/>
'ndaki Kullanıcı aracıyla ilişkilendirilecek yeni uygulamayı belirtir.

### <a name="remarks"></a>Açıklamalar

Kullanıcı aracının çalıştırdığı yeni bir uygulama ayarlamak için bu yöntemi çağırın. Yöntemi eski simgeyi yok eder ve belirtilen uygulamadan yeni bir simge yükler. Uygulamadan bir simge yükleye, bir Kullanıcı aracının varsayılan simgesini, [CUserTool:: LoadDefaultIcon](#loaddefaulticon)çağırarak yükler.

## <a name="cusertoolsettoolicon"></a><a name="settoolicon"></a> CUserTool:: SetToolIcon

Aracın kullandığı uygulamadan Kullanıcı aracı simgesini yükler.

```
virtual HICON SetToolIcon();
```

### <a name="return-value"></a>Dönüş Değeri

Yüklenen simgeye yönelik bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Menü öğesinde görüntülenecek simgeyi yüklemek için bu yöntemi çağırın. Bu yöntem, aracın kullandığı çalıştırılabilir dosyadaki simgeyi arar. Varsayılan bir simge yoksa, bunun yerine [CUserTool:: LoadDefaultIcon](#loaddefaulticon) tarafından sunulan simge kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md)<br/>
[Cuser, yönetici sınıfı](../../mfc/reference/cusertoolsmanager-class.md)
