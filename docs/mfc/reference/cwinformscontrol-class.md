---
title: CWinFormsControl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CWinFormsControl
- AFXWINFORMS/CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CreateManagedControl
- AFXWINFORMS/CWinFormsControl::GetControl
- AFXWINFORMS/CWinFormsControl::GetControlHandle
helpviewer_keywords:
- CWinFormsControl [MFC], CWinFormsControl
- CWinFormsControl [MFC], CreateManagedControl
- CWinFormsControl [MFC], GetControl
- CWinFormsControl [MFC], GetControlHandle
ms.assetid: 6406dd7b-fb89-4a18-ac3a-c010d6b6289a
ms.openlocfilehash: c91f50be1ea30efac81ff67c43633bedd7b0ca03
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377177"
---
# <a name="cwinformscontrol-class"></a>CWinFormsControl Sınıfı

Windows Forms denetiminin barındırılamı için temel işlevselliği sağlar.

## <a name="syntax"></a>Sözdizimi

```
template<class TManagedControl>
class CWinFormsControl : public CWnd
```

#### <a name="parameters"></a>Parametreler

*TManagedControl*<br/>
MFC uygulamasında görüntülenecek bir .NET Framework Windows Forms denetimi.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CwinformsControl::CWinformsControl](#cwinformscontrol)|Bir MFC Windows Forms denetim sarıcı nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)|MFC kapsayıcısında Windows Forms denetimi oluşturur.|
|[CWinFormsControl::GetControl](#getcontrol)|Windows Forms denetimi için bir işaretçi alır.|
|[CwinFormsControl::GetControlHandle](#getcontrolhandle)|Windows Forms denetimine bir tanıtıcı alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CWinFormsControl::operatör -&gt;](#operator_-_gt)|[CWinFormsControl değiştirir::GetControl](#getcontrol) ifadelerinde.|
|[CWinFormsControl::operatör TManagedControl^](#operator_tmanagedcontrol)|Bir türü Windows Forms denetimine işaretçi olarak atar.|

## <a name="remarks"></a>Açıklamalar

Sınıf, `CWinFormsControl` Windows Forms denetiminin barındırılamıiçin temel işlevselliği sağlar.

Windows Formlarını kullanma hakkında daha fazla bilgi [için](../../dotnet/using-a-windows-form-user-control-in-mfc.md)bkz.

MFC kodunuz Pencere tutamaçlarını önbelleğe `m_hWnd`almamalıdır (genellikle depolanır). Bazı Windows Forms denetim özellikleri, altta `Window` yatan Win32'nin yok edilmesini ve yeniden `DestroyWindow` kullanılmasını gerektirir. `CreateWindow` MFC Windows Forms `Destroy` `Create` `m_hWnd` uygulaması, üyeyi güncelleştirmek için denetimlerin olaylarını ve olaylarını işler.

> [!NOTE]
> MFC Windows Forms tümleştirmesi yalnızca MFC ile dinamik olarak bağlantı sağlayan (AFXDLL'nin tanımlandığı) projelerde çalışır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwinforms.h

## <a name="cwinformscontrolcreatemanagedcontrol"></a><a name="createmanagedcontrol"></a>CWinFormsControl::CreateManagedControl

MFC kapsayıcısında Windows Forms denetimi oluşturur.

```
inline BOOL CreateManagedControl(
    System::Type^ pType,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID)
inline BOOL CreateManagedControl(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID);

inline BOOL CreateManagedControl(
    DWORD dwStyle,
    int nPlaceHolderID,
    CWnd* pParentWnd);

inline BOOL CreateManagedControl(
    typename TManagedControl^ pControl,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID);
```

### <a name="parameters"></a>Parametreler

*pTipi*<br/>
Oluşturulacak denetimin veri türü. [Tür](/dotnet/api/system.type) veri türü olmalıdır.

*Dwstyle*<br/>
Denetime uygulanacak pencere stili. [Pencere Stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles)nin bir birleşimini belirtin. Şu anda yalnızca aşağıdaki stilleri desteklenir: WS_TABSTOP, WS_VISIBLE, WS_DISABLED ve WS_GROUP.

*Rect*<br/>
Denetimin sol üst ve alt-sağ köşelerinin koordinatlarını tanımlayan bir [RECT Yapısı](/windows/win32/api/windef/ns-windef-rect) (yalnızca ilk aşırı yükleme).

*nPlaceHolderID*<br/>
Kaynak Düzenleyicisi'ne yerleştirilen statik yer tutucu denetiminin tutamacı. Yeni oluşturulan Windows Forms denetimi, konumunu, z sırasını ve stillerini (yalnızca ikinci aşırı yükleme) varsayerek statik denetimin yerini alır.

*pParentWnd*<br/>
Üst pencereiçin bir işaretçi.

*Nıd*<br/>
Yeni oluşturulan denetime atanacak kaynak kimlik numarası.

*pKontrol*<br/>
[CWinFormsControl](../../mfc/reference/cwinformscontrol-class.md) nesnesi ile ilişkilendirilecek bir Windows Forms denetimi örneği (yalnızca dördüncü aşırı yükleme).

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, sıfır olmayan bir değer döndürür. Başarısız olursa, sıfır döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir MFC kapsayıcısında bir .NET Framework Windows Forms denetimini anında kullanır.

Yöntemin ilk aşırı yüklemesi, MFC'nin bu tür yeni bir nesneyi anında atabilmesi için bir .NET Framework veri türü *pType'ı* kabul eder. *pType* bir [Tür](/dotnet/api/system.type) veri türü olmalıdır.

Yöntemin ikinci aşırı `TManagedControl` `CWinFormsControl` yüklemesi, sınıfın şablon parametresini temel alan bir Windows Forms denetimi oluşturur. Denetimin boyutu ve konumu yönteme `RECT` geçirilen yapıya dayanır. Sadece *dwStyle* stilleri için önemlidir.

Yöntemin üçüncü aşırı yükü, statik denetimin yerini alan, onu yok eden ve konumunu, z-sırasını ve stillerini varsayan bir Windows Forms denetimi oluşturur. Statik denetim yalnızca Windows Forms denetimi için bir yer tutucu olarak hizmet verir. Denetimi oluştururken, bu aşırı yük *dwStyle'daki* stilleri statik denetimin kaynak stilleriyle birleştirir.

Yöntemin dördüncü aşırı yüklemesi, MFC'nin saracağı zaten anında alınmış windows forms denetim *pControl'de* geçmenizi sağlar. `CWinFormsControl` Sınıfın `TManagedControl` şablon parametresi ile aynı türden olmalıdır.

Bkz. Windows Form denetimlerini kullanma yla ilgili örnekler için [MFC'de Windows Form Kullanıcı Denetimi](../../dotnet/using-a-windows-form-user-control-in-mfc.md) kullanma.

## <a name="cwinformscontrolcwinformscontrol"></a><a name="cwinformscontrol"></a>CwinformsControl::CWinformsControl

Bir MFC Windows Forms denetim sarıcı nesnesi oluşturur.

```
CWinFormsControl();
```

### <a name="remarks"></a>Açıklamalar

[CWinFormsControl::CreateManagedControl'u](#createmanagedcontrol)aradiğinizde Windows Forms denetimi anında oluşturulur.

## <a name="cwinformscontrolgetcontrol"></a><a name="getcontrol"></a>CWinFormsControl::GetControl

Windows Forms denetimi için bir işaretçi alır.

```
inline TManagedControl^ GetControl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçiyi Windows Forms denetimine döndürür.

### <a name="example"></a>Örnek

  [Bkz. CWinFormsControl::CreateManagedControl](#createmanagedcontrol).

## <a name="cwinformscontrolgetcontrolhandle"></a><a name="getcontrolhandle"></a>CwinFormsControl::GetControlHandle

Windows Forms denetimine bir tanıtıcı alır.

```
inline HWND GetControlHandle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir tanıtıcıyı Windows Forms denetimine döndürür.

### <a name="remarks"></a>Açıklamalar

`GetControlHandle`.NET Framework denetim özelliklerinde depolanan pencere tutamacını döndüren bir yardımcı yöntemdir. Pencere tutamak değeri [CWnd kopyalanır::m_hWnd](../../mfc/reference/cwnd-class.md#m_hwnd) CWnd için arama [sırasında::Ekle](../../mfc/reference/cwnd-class.md#attach).

## <a name="cwinformscontroloperator--gt"></a><a name="operator_-_gt"></a>CWinFormsControl::operatör -&gt;

[CWinFormsControl değiştirir::GetControl](#getcontrol) ifadelerinde.

```
inline TManagedControl^  operator->() const;
```

### <a name="remarks"></a>Açıklamalar

Bu işleç ifadeler `GetControl` yerine uygun bir sözdizimi sağlar.

Windows Formları hakkında daha fazla bilgi için [bkz.](../../dotnet/using-a-windows-form-user-control-in-mfc.md)

## <a name="cwinformscontroloperator-tmanagedcontrol"></a><a name="operator_tmanagedcontrol"></a>CWinFormsControl::operatör TManagedControl^

Bir türü Windows Forms denetimine işaretçi olarak atar.

```
inline operator TManagedControl^() const;
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, Windows Forms denetimi için işaretçi kabul eden işlevlere geçer. `CWinFormsControl<TManagedControl>`

## <a name="see-also"></a>Ayrıca bkz.

[CWinFormsDialog Sınıfı](../../mfc/reference/cwinformsdialog-class.md)<br/>
[CWinFormsView Sınıfı](../../mfc/reference/cwinformsview-class.md)
