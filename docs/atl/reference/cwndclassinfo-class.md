---
description: 'Daha fazla bilgi edinin: CWndClassInfo sınıfı'
title: CWndClassInfo sınıfı
ms.date: 11/04/2016
f1_keywords:
- CWndClassInfo
- ATLWIN/ATL::CWndClassInfo
- ATLWIN/ATL::Register
- ATLWIN/ATL::m_atom
- ATLWIN/ATL::m_bSystemCursor
- ATLWIN/ATL::m_lpszCursorID
- ATLWIN/ATL::m_lpszOrigName
- ATLWIN/ATL::m_szAutoName
- ATLWIN/ATL::m_wc
- ATLWIN/ATL::pWndProc
helpviewer_keywords:
- CWndClassInfo class
ms.assetid: c36fe7e1-75f1-4cf5-a06f-9f59c43fe6fb
ms.openlocfilehash: 7a857812fa35743fbab0968fb94095bf8fdcabcf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140029"
---
# <a name="cwndclassinfo-class"></a>CWndClassInfo sınıfı

Bu sınıf, bir pencere sınıfının bilgilerini kaydetmek için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
class CWndClassInfo
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|-|-|
|[Kaydet](#register)|Pencere sınıfını kaydeder.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|-|-|
|[m_atom](#m_atom)|Kayıtlı pencere sınıfını benzersiz şekilde tanımlar.|
|[m_bSystemCursor](#m_bsystemcursor)|İmleç kaynağının bir sistem imlecine mi yoksa bir modül kaynağında bulunan bir imlece mi başvurmadığını belirtir.|
|[m_lpszCursorID](#m_lpszcursorid)|İmleç kaynağının adını belirtir.|
|[m_lpszOrigName](#m_lpszorigname)|Varolan bir pencere sınıfının adını içerir.|
|[m_szAutoName](#m_szautoname)|, Window sınıfının ATL tarafından oluşturulan bir adını tutar.|
|[m_wc](#m_wc)|Pencere sınıfı bilgilerini bir yapıda tutar `WNDCLASSEX` .|
|[pWndProc](#pwndproc)|Varolan bir pencere sınıfının pencere yordamına işaret eder.|

## <a name="remarks"></a>Açıklamalar

`CWndClassInfo` pencere sınıfının bilgilerini yönetir. `CWndClassInfo`Aşağıdaki tabloda açıklandığı gibi, genellikle üç makro DECLARE_WND_CLASS, declare_wnd_class_ex veya declare_wnd_superclass kullanın:

|Makroya|Açıklama|
|-----------|-----------------|
|[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)|`CWndClassInfo` Yeni bir pencere sınıfı için bilgileri kaydeder.|
|[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)|`CWndClassInfo` sınıf parametreleri de dahil olmak üzere yeni bir pencere sınıfının bilgilerini kaydeder.|
|[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)|`CWndClassInfo` Mevcut bir sınıfı temel alan ancak farklı bir pencere yordamı kullanan bir pencere sınıfı için bilgileri kaydeder. Bu teknik, superclassing olarak adlandırılır.|

Varsayılan olarak, [CWindowImpl](../../atl/reference/cwindowimpl-class.md) yeni bir `DECLARE_WND_CLASS` pencere sınıfına dayalı bir pencere oluşturmak için makroyu içerir. DECLARE_WND_CLASS, denetimin varsayılan stillerini ve arka plan rengini sağlar. Stili ve arka plan rengini kendiniz belirtmek istiyorsanız, sınıfınızı sınıfından türetebilir `CWindowImpl` ve sınıf tanımınızda declare_wnd_class_ex makrosunu ekleyin.

Varolan bir pencere sınıfına dayalı bir pencere oluşturmak isterseniz, sınıfınızı sınıfından türetebilir `CWindowImpl` ve declare_wnd_superclass makrosunu sınıf tanımınıza ekleyin. Örneğin:

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwndclassinfo-class_1.h)]

Pencere sınıfları hakkında daha fazla bilgi için bkz. Windows SDK [pencere sınıfları](/windows/win32/winmsg/window-classes) .

ATL 'de Windows kullanımı hakkında daha fazla bilgi için bkz. [atl pencere sınıfları](../../atl/atl-window-classes.md)makalesi.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

## <a name="cwndclassinfom_atom"></a><a name="m_atom"></a> CWndClassInfo:: m_atom

Kayıtlı pencere sınıfı için benzersiz tanımlayıcıyı içerir.

```
ATOM m_atom;
```

## <a name="cwndclassinfom_bsystemcursor"></a><a name="m_bsystemcursor"></a> CWndClassInfo:: m_bSystemCursor

TRUE ise, pencere sınıfı kaydedildiğinde sistem imleç kaynağı yüklenir.

```
BOOL m_bSystemCursor;
```

### <a name="remarks"></a>Açıklamalar

Aksi halde, modülünüzün içerdiği imleç kaynağı yüklenir.

`CWndClassInfo``m_bSystemCursor`yalnızca [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) ( [CWindowImpl](../../atl/reference/cwindowimpl-class.md)'de varsayılan) veya [declare_wnd_class_ex](window-class-macros.md#declare_wnd_class_ex) makrosu belirtildiğinde kullanır. Bu durumda, `m_bSystemCursor` true olarak başlatılır. Daha fazla bilgi için bkz. [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) 'ya genel bakış.

## <a name="cwndclassinfom_lpszcursorid"></a><a name="m_lpszcursorid"></a> CWndClassInfo:: m_lpszCursorID

İmleç kaynağının adını ya da düşük sıralı sözcükteki kaynak tanımlayıcısını ve yüksek sıralı sözcükteki sıfırı belirtir.

```
LPCTSTR m_lpszCursorID;
```

### <a name="remarks"></a>Açıklamalar

Pencere sınıfı kaydedildiğinde, tarafından tanımlanan imlece tanıtıcısı `m_lpszCursorID` alınır ve [m_wc](#m_wc)tarafından depolanır.

`CWndClassInfo``m_lpszCursorID`yalnızca [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) ( [CWindowImpl](../../atl/reference/cwindowimpl-class.md)'de varsayılan) veya [declare_wnd_class_ex](window-class-macros.md#declare_wnd_class_ex) makrosu belirtildiğinde kullanır. Bu durumda, `m_lpszCursorID` IDC_ARROW için başlatılır. Daha fazla bilgi için bkz. [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) 'ya genel bakış.

## <a name="cwndclassinfom_lpszorigname"></a><a name="m_lpszorigname"></a> CWndClassInfo:: m_lpszOrigName

Varolan bir pencere sınıfının adını içerir.

```
LPCTSTR m_lpszOrigName;
```

### <a name="remarks"></a>Açıklamalar

`CWndClassInfo``m_lpszOrigName`yalnızca sınıf tanımınızda [declare_wnd_superclass](window-class-macros.md#declare_wnd_superclass) makrosunu dahil ettiğinizde kullanır. Bu durumda, `CWndClassInfo` tarafından adlandırılan sınıfına dayalı bir pencere sınıfını kaydeder `m_lpszOrigName` . Daha fazla bilgi için bkz. [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) 'ya genel bakış.

## <a name="cwndclassinfom_szautoname"></a><a name="m_szautoname"></a> CWndClassInfo:: m_szAutoName

Pencere sınıfının adını tutar.

```
TCHAR m_szAutoName[13];
```

### <a name="remarks"></a>Açıklamalar

`CWndClassInfo``m_szAutoName`yalnızca `WndClassName` parametresi için [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class), [declare_wnd_class_ex](window-class-macros.md#declare_wnd_class_ex) veya [declare_wnd_superclass](window-class-macros.md#declare_wnd_superclass)için null geçirildiğinde kullanılır. Windows sınıfı kaydedildiğinde ATL bir ad oluşturur.

## <a name="cwndclassinfom_wc"></a><a name="m_wc"></a> CWndClassInfo:: m_wc

Bir [WNDCLASSEX](/windows/win32/api/winuser/ns-winuser-wndclassexw) yapısında pencere sınıfı bilgilerini korur.

```
WNDCLASSEX m_wc;
```

### <a name="remarks"></a>Açıklamalar

[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) ( [CWindowImpl](../../atl/reference/cwindowimpl-class.md)'de varsayılan) veya [declare_wnd_class_ex](window-class-macros.md#declare_wnd_class_ex) makrosu belirttiyseniz, `m_wc` Yeni bir pencere sınıfıyla ilgili bilgiler içerir.

[Declare_wnd_superclass](window-class-macros.md#declare_wnd_superclass) makrosunu belirttiyseniz, `m_wc` var olan bir sınıfı temel alan ancak farklı bir pencere yordamı kullanan bir pencere sınıfı olan bir üst sınıf hakkındaki bilgileri içerir. [m_lpszOrigName](#m_lpszorigname) ve [pWndProc](#pwndproc) , sırasıyla varolan pencere sınıfının adını ve pencere yordamını kaydeder.

## <a name="cwndclassinfopwndproc"></a><a name="pwndproc"></a> CWndClassInfo::p WndProc

Varolan bir pencere sınıfının pencere yordamına işaret eder.

```
WNDPROC pWndProc;
```

### <a name="remarks"></a>Açıklamalar

`CWndClassInfo``pWndProc`yalnızca sınıf tanımınızda [declare_wnd_superclass](window-class-macros.md#declare_wnd_superclass) makrosunu dahil ettiğinizde kullanır. Bu durumda, `CWndClassInfo` varolan bir sınıfa dayalı ancak farklı bir pencere yordamı kullanan bir pencere sınıfını kaydeder. Varolan pencere sınıfının pencere yordamı ' de kaydedilir `pWndProc` . Daha fazla bilgi için bkz. [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) 'ya genel bakış.

## <a name="cwndclassinforegister"></a><a name="register"></a> CWndClassInfo:: Register

Henüz kayıtlı değilse, bir pencere sınıfını kaydetmek için [CWindowImpl:: Create](../../atl/reference/cwindowimpl-class.md#create) tarafından çağırılır.

```
ATOM Register(WNDPROC* pProc);
```

### <a name="parameters"></a>Parametreler

*pProc*<br/>
dışı Varolan bir pencere sınıfının orijinal pencere yordamını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, kayıtlı olan pencere sınıfını benzersiz bir şekilde tanımlayan bir atom. Aksi takdirde, 0.

### <a name="remarks"></a>Açıklamalar

[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) ( [CWindowImpl](../../atl/reference/cwindowimpl-class.md)içinde varsayılan) veya [declare_wnd_class_ex](window-class-macros.md#declare_wnd_class_ex) makrosu belirttiyseniz, `Register` Yeni bir pencere sınıfını kaydeder. Bu durumda, *pProc* parametresi kullanılmaz.

[Declare_wnd_superclass](window-class-macros.md#declare_wnd_superclass) makrosunu belirttiyseniz, `Register` var olan bir sınıfı temel alan ancak farklı bir pencere yordamı kullanan bir pencere sınıfı olan bir üst sınıf kaydeder. Mevcut pencere sınıfının pencere yordamı *pProc* içinde döndürülür.

## <a name="see-also"></a>Ayrıca bkz.

[CComControl sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
