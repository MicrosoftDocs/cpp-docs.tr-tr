---
title: CWinFormsControl sınıfı
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
ms.openlocfilehash: 75a6d7ea2b4f3ab229d7e3f4d411711261bb1b82
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502192"
---
# <a name="cwinformscontrol-class"></a>CWinFormsControl sınıfı

Windows Forms denetiminin barındırılmasına yönelik temel işlevleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
template<class TManagedControl>
class CWinFormsControl : public CWnd
```

#### <a name="parameters"></a>Parametreler

*TManagedControl*<br/>
MFC uygulamasında görüntülenmek üzere bir .NET Framework Windows Forms denetimi.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CWinFormsControl::CWinFormsControl](#cwinformscontrol)|MFC Windows Forms Control sarmalayıcı nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CWinFormsControl:: CreateManagedControl](#createmanagedcontrol)|MFC kapsayıcısında bir Windows Forms denetimi oluşturur.|
|[CWinFormsControl:: GetControl](#getcontrol)|Windows Forms denetimine bir işaretçi alır.|
|[CWinFormsControl:: GetControlHandle](#getcontrolhandle)|Windows Forms denetimine bir tanıtıcı alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CWinFormsControl:: operator-&gt;](#operator_-_gt)|İfadelerde [CWinFormsControl:: GetControl](#getcontrol) yerini alır.|
|[CWinFormsControl:: operator TManagedControl ^](#operator_tmanagedcontrol)|Bir türü Windows Forms denetimine işaretçi olarak yayınlar.|

## <a name="remarks"></a>Açıklamalar

`CWinFormsControl` Sınıfı, bir Windows Forms denetiminin barındırılmasına yönelik temel işlevleri sağlar.

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC 'de Windows formu Kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

MFC kodunuz pencere tutamaçlarını önbelleğe içermemelidir (genellikle içinde `m_hWnd`depolanır). Bazı Windows Forms denetim özellikleri, ve kullanılarak `Window` `DestroyWindow` temel alınan Win32 'in yok edileceği ve yeniden `CreateWindow`oluşturulması gerekir. MFC Windows Forms uygulama, `Destroy` `m_hWnd` üyeyi güncelleştirmek için `Create` denetimlerin ve olaylarını işler.

> [!NOTE]
>  MFC Windows Forms tümleştirmesi yalnızca MFC ile dinamik olarak bağlanan projelerde (AFXDLL içinde tanımlanmıştır) kullanılabilir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwinforms. h

##  <a name="createmanagedcontrol"></a>CWinFormsControl:: CreateManagedControl

MFC kapsayıcısında bir Windows Forms denetimi oluşturur.

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

*pType*<br/>
Oluşturulacak denetimin veri türü. Bir [tür](/dotnet/api/system.type) veri türü olmalıdır.

*dwStyle*<br/>
Denetime uygulanacak pencere stili. [Pencere stillerinin](../../mfc/reference/styles-used-by-mfc.md#window-styles)birleşimini belirtin. Şu anda yalnızca aşağıdaki stiller desteklenir: WS_TABSTOP, WS_VISIBLE, WS_DISABLED ve WS_GROUP.

*Rect*<br/>
Denetimin sol üst ve sağ alt köşelerinin koordinatlarını tanımlayan bir [Rect yapısı](/windows/win32/api/windef/ns-windef-rect) (yalnızca ilk aşırı yükleme).

*nPlaceHolderID*<br/>
Kaynak düzenleyicisine yerleştirilmiş statik yer tutucu denetimi tutamacı. Yeni oluşturulan Windows Forms denetimi, konumunu, z düzenini ve stillerini kabul eden statik denetimin yerini alır (yalnızca ikinci aşırı yükleme).

*pParentWnd*<br/>
Ana pencereye yönelik bir işaretçi.

*NID*<br/>
Yeni oluşturulan denetime atanacak kaynak KIMLIĞI numarası.

*pControl*<br/>
[CWinFormsControl](../../mfc/reference/cwinformscontrol-class.md) nesnesiyle ilişkilendirilecek Windows Forms denetiminin örneği (yalnızca dördüncü aşırı yükleme).

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, sıfır dışında bir değer döndürür. Başarısız olursa, sıfır döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir MFC kapsayıcısında bir .NET Framework Windows Forms denetimi başlatır.

Yöntemin ilk aşırı yüklemesi, MFC 'nin bu türden yeni bir nesne örnekyapabilmesi için bir .NET Framework veri türü *pType* kabul eder. *pType* bir [tür](/dotnet/api/system.type) veri türü olmalıdır.

Yönteminin ikinci aşırı yüklemesi, `TManagedControl` `CWinFormsControl` sınıfının şablon parametresine bağlı olarak bir Windows Forms denetimi oluşturur. Denetimin boyutu ve konumu yöntemine geçirilen `RECT` yapıya dayalıdır. Stiller için yalnızca *dwStyle* önemlidir.

Yöntemin üçüncü aşırı yüklemesi, statik bir denetimin yerini alan, yok etme ve konumunu, z düzeni ve stillerini kabul eden bir Windows Forms denetimi oluşturur. Statik denetim yalnızca Windows Forms denetimi için bir yer tutucu olarak işlev görür. Bu aşırı yükleme, denetimi oluştururken *dwStyle* 'daki stilleri statik denetimin kaynak stilleriyle birleştirir.

Yöntemin dördüncü aşırı yüklemesi, MFC 'nin kaydıralacağı, önceden oluşturulmuş bir Windows Forms Denetim *pControl* ' i geçirmenize olanak sağlar. Bu, `TManagedControl` `CWinFormsControl` sınıfının şablon parametresiyle aynı türde olmalıdır.

Windows form denetimlerini kullanma hakkında örnekler için bkz. [MFC 'de Windows form kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md) .

##  <a name="cwinformscontrol"></a>CWinFormsControl::CWinFormsControl

MFC Windows Forms Control sarmalayıcı nesnesi oluşturur.

```
CWinFormsControl();
```

### <a name="remarks"></a>Açıklamalar

[CWinFormsControl:: CreateManagedControl](#createmanagedcontrol)' i çağırdığınızda Windows Forms denetimi oluşturulur.

##  <a name="getcontrol"></a>CWinFormsControl:: GetControl

Windows Forms denetimine bir işaretçi alır.

```
inline TManagedControl^ GetControl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Windows Forms denetimine bir işaretçi döndürür.

### <a name="example"></a>Örnek

  Bkz. [CWinFormsControl:: CreateManagedControl](#createmanagedcontrol).

##  <a name="getcontrolhandle"></a>CWinFormsControl:: GetControlHandle

Windows Forms denetimine bir tanıtıcı alır.

```
inline HWND GetControlHandle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Windows Forms denetimine bir tanıtıcı döndürür.

### <a name="remarks"></a>Açıklamalar

`GetControlHandle`, .NET Framework denetim özelliklerinde depolanan pencere tanıtıcısını döndüren yardımcı bir yöntemdir. [CWnd:: Attach](../../mfc/reference/cwnd-class.md#attach)çağrısı sırasında, Window tanıtıcı değeri [CWnd:: m_hWnd](../../mfc/reference/cwnd-class.md#m_hwnd) ' e kopyalanır.

##  <a name="operator_-_gt"></a>CWinFormsControl:: operator-&gt;

İfadelerde [CWinFormsControl:: GetControl](#getcontrol) yerini alır.

```
inline TManagedControl^  operator->() const;
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, ifadelerde yerini `GetControl` alan kullanışlı bir sözdizimi sağlar.

Windows Forms hakkında daha fazla bilgi için bkz. [MFC 'de Windows formu Kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

##  <a name="operator_tmanagedcontrol"></a>CWinFormsControl:: operator TManagedControl ^

Bir türü Windows Forms denetimine işaretçi olarak yayınlar.

```
inline operator TManagedControl^() const;
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, `CWinFormsControl<TManagedControl>` Windows Forms denetimine yönelik bir işaretçi kabul eden işlevlere geçer.

## <a name="see-also"></a>Ayrıca bkz.

[CWinFormsDialog Sınıfı](../../mfc/reference/cwinformsdialog-class.md)<br/>
[CWinFormsView Sınıfı](../../mfc/reference/cwinformsview-class.md)
