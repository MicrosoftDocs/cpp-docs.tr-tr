---
title: CuserTool Sınıfı
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
ms.openlocfilehash: 183b30961e4a7d3079fa0d035a4ddc38bc2eebac
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752023"
---
# <a name="cusertool-class"></a>CuserTool Sınıfı

Kullanıcı aracı, harici bir uygulama çalıştıran bir menü öğesidir. **Özelleştir** iletişim kutusunun **Araçlar** sekmesi [(CMFCToolBarsCustomizeDialog Class)](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)kullanıcının kullanıcı araçları eklemesini ve her kullanıcı aracı için adı, komutu, bağımsız değişkenleri ve ilk dizini belirtmesini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CUserTool : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CUserTool::CopyIconToClipboard](#copyicontoclipboard)||
|[CUserTool::DrawToolIcon](#drawtoolicon)|Kullanıcı aracı simgesini belirli bir dikdörtgende çizer.|
|[CuserTool::Getkomut](#getcommand)|Kullanıcı aracıyla ilişkili komutun metnini içeren bir dize döndürür.|
|[CuserTool::GetCommandid](#getcommandid)|Kullanıcı aracının menü öğesinin komut kimliğini verir.|
|[CUserTool::Invoke](#invoke)|Kullanıcı aracıyla ilişkili komutu yürütür.|
|[CUserTool::Serialize](#serialize)|Bu nesneyi arşivden veya arşivden okur veya yazar. (CObject geçersiz [kılar::Serialize](../../mfc/reference/cobject-class.md#serialize).)|
|[CuserTool::Setkomut](#setcommand)|Kullanıcı aracıyla ilişkili komutu ayarlar.|
|[CuserTool::SetToolicon](#settoolicon)|Kullanıcı aracı simgesini araçla ilişkili uygulamadan yükler.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Cusertool::loaddefaulticon](#loaddefaulticon)|Bir kullanıcı aracı için varsayılan simgeyi yükler.|

### <a name="data-members"></a>Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CUserTool::m_strArguments](#m_strarguments)|Kullanıcı aracı için komut satırı bağımsız değişkenleri.|
|[CUserTool::m_strInitialDirectory](#m_strinitialdirectory)|Kullanıcı aracının ilk dizini.|
|[CUserTool::m_strLabel](#m_strlabel)|Aracın menü öğesinde görüntülenen araç adı.|

## <a name="remarks"></a>Açıklamalar

Uygulamanızda kullanıcı araçlarını etkinleştirme hakkında daha fazla bilgi için [CUserToolsManager Sınıfı'na](../../mfc/reference/cusertoolsmanager-class.md)bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesneden bir `CUserToolsManager` araç nasıl `m_strLabel` oluşturulup üye değişkenini ayarlanın ve kullanıcı aracının çalıştırdığı uygulamayı nasıl ayarlayacağını gösterir. Bu kod snippet [Visual Studio Demo örnek](../../overview/visual-cpp-samples.md)parçasıdır.

[!code-cpp[NVC_MFC_VisualStudioDemo#35](../../mfc/codesnippet/cpp/cusertool-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cusertool](../../mfc/reference/cusertool-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxusertool.h

## <a name="cusertoolcopyicontoclipboard"></a><a name="copyicontoclipboard"></a>CUserTool::CopyIconToClipboard

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

```
BOOL CopyIconToClipboard();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cusertooldrawtoolicon"></a><a name="drawtoolicon"></a>CUserTool::DrawToolIcon

Kullanıcı aracı simgesini belirli bir dikdörtgenin ortasına çizer.

```cpp
void DrawToolIcon(
    CDC* pDC,
    const CRect& rectImage);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*rectImage*<br/>
[içinde] Simgeyi görüntülemek için alanın koordinatlarını belirtir.

## <a name="cusertoolgetcommand"></a><a name="getcommand"></a>CuserTool::Getkomut

Kullanıcı aracıyla ilişkili komutun metnini içeren bir dize döndürür.

```
const CString& GetCommand() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı aracıyla ilişkili komutun metnini içeren nesneye `CString` yapılan başvuru.

## <a name="cusertoolgetcommandid"></a><a name="getcommandid"></a>CuserTool::GetCommandid

Kullanıcı aracının komut kimliğini verir.

```
UINT GetCommandId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu kullanıcı aracının komut kimliği.

## <a name="cusertoolinvoke"></a><a name="invoke"></a>CUserTool::Invoke

Kullanıcı aracıyla ilişkili komutu yürütür.

```
virtual BOOL Invoke();
```

### <a name="return-value"></a>Dönüş Değeri

Komut başarıyla yürütülürse sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kullanıcı aracıyla ilişkili bir komutu yürütmesi için [ShellExecute'ı](/windows/win32/api/shellapi/nf-shellapi-shellexecutew) çağırır. Komut boşsa veya [ShellExecute](/windows/win32/api/shellapi/nf-shellapi-shellexecutew) başarısız olursa işlev başarısız olur.

## <a name="cusertoolloaddefaulticon"></a><a name="loaddefaulticon"></a>Cusertool::loaddefaulticon

Bir kullanıcı aracı için varsayılan simgeyi yükler.

```
virtual HICON LoadDefaultIcon();
```

### <a name="return-value"></a>Dönüş Değeri

Yüklenen simgeye (HICON) veya varsayılan simge yüklenemezse NULL'a bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Çerçeve, aracın yürütülebilir dosyasından kullanıcı tanımlı bir araç için simge yükleyemediğinde bu yöntemi çağırır.

Kendi varsayılan araç simgenizi sağlamak için bu yöntemi geçersiz kılın.

## <a name="cusertoolm_strarguments"></a><a name="m_strarguments"></a>CUserTool::m_strArguments

Kullanıcı aracı için komut satırı bağımsız değişkenleri.

```
CString m_strArguments;
```

### <a name="remarks"></a>Açıklamalar

Bu dize, CUserTool'u aradiğinizde araca [aktarılır::Çağırın](#invoke) veya kullanıcı bu araçla ilişkili komutu tıklattığında.

## <a name="cusertoolm_strinitialdirectory"></a><a name="m_strinitialdirectory"></a>CUserTool::m_strInitialDirectory

Kullanıcı aracının ilk dizinini belirtir.

```
CString m_strInitialDirectory;
```

### <a name="remarks"></a>Açıklamalar

Bu değişken, CUserTool'u aradiğinizde aracın yürüttüğü ilk dizini [belirtir::ÇağırVeya](#invoke) kullanıcı bu araçla ilişkili komutu tıklattığında.

## <a name="cusertoolm_strlabel"></a><a name="m_strlabel"></a>CUserTool::m_strLabel

Aracın menü öğesinde görüntülenen etiket.

```
CString m_strLabel;
```

## <a name="cusertoolserialize"></a><a name="serialize"></a>CUserTool::Serialize

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

[içinde] *ar*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cusertoolsetcommand"></a><a name="setcommand"></a>CuserTool::Setkomut

Kullanıcı aracının çalıştırdığı uygulamayı ayarlar.

```cpp
void SetCommand(LPCTSTR lpszCmd);
```

### <a name="parameters"></a>Parametreler

*lpszCmd*<br/>
[içinde] Yeni uygulamanın kullanıcı aracıyla ilişkilendirilecek şekilde belirtilmesi.

### <a name="remarks"></a>Açıklamalar

Kullanıcı aracının çalıştırdığı yeni bir uygulama ayarlamak için bu yöntemi arayın. Yöntem eski simgeyi yok eder ve verilen uygulamadan yeni bir simge yükler. Uygulamadan bir simge yükleyemiyorsa, CUserTool'u arayarak bir kullanıcı aracı nın varsayılan simgesini [yükler::LoadDefaultIcon](#loaddefaulticon).

## <a name="cusertoolsettoolicon"></a><a name="settoolicon"></a>CuserTool::SetToolicon

Kullanıcı aracı simgesini aracın kullandığı uygulamadan yükler.

```
virtual HICON SetToolIcon();
```

### <a name="return-value"></a>Dönüş Değeri

Yüklenen simgeye bir tutamaç.

### <a name="remarks"></a>Açıklamalar

Menü öğesinde görüntülenecek simgeyi yüklemek için bu yöntemi arayın. Bu yöntem, aracın kullandığı yürütülebilir dosyadaki simgeyi arar. Varsayılan simgesi yoksa, CUserTool tarafından sağlanan [simge::LoadDefaultIcon](#loaddefaulticon) bunun yerine kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx Sınıfı](../../mfc/reference/cwinappex-class.md)<br/>
[CusertoolsManager Sınıfı](../../mfc/reference/cusertoolsmanager-class.md)
