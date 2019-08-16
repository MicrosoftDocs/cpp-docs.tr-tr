---
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
ms.openlocfilehash: c416155ed103f1345c42e6680c2329ab98d35926
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496119"
---
# <a name="cwndclassinfo-class"></a>CWndClassInfo sınıfı

Bu sınıf, bir pencere sınıfının bilgilerini kaydetmek için yöntemler sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CWndClassInfo
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|[Kaydolunamadı](#register)|Pencere sınıfını kaydeder.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[m_atom](#m_atom)|Kayıtlı pencere sınıfını benzersiz şekilde tanımlar.|
|[m_bSystemCursor](#m_bsystemcursor)|İmleç kaynağının bir sistem imlecine mi yoksa bir modül kaynağında bulunan bir imlece mi başvurmadığını belirtir.|
|[m_lpszCursorID](#m_lpszcursorid)|İmleç kaynağının adını belirtir.|
|[m_lpszOrigName](#m_lpszorigname)|Varolan bir pencere sınıfının adını içerir.|
|[m_szAutoName](#m_szautoname)|, Window sınıfının ATL tarafından oluşturulan bir adını tutar.|
|[m_wc](#m_wc)|Pencere sınıfı bilgilerini bir `WNDCLASSEX` yapıda tutar.|
|[pWndProc](#pwndproc)|Varolan bir pencere sınıfının pencere yordamına işaret eder.|

## <a name="remarks"></a>Açıklamalar

`CWndClassInfo`pencere sınıfının bilgilerini yönetir. Aşağıdaki tabloda açıklandığı `CWndClassInfo` gibi, genellikle üç makro, DECLARE_WND_CLASS, declare_wnd_class_ex veya declare_wnd_superclass aracılığıyla kullanılır:

|Makrosu|Açıklama|
|-----------|-----------------|
|[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)|`CWndClassInfo`Yeni bir pencere sınıfı için bilgileri kaydeder.|
|[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)|`CWndClassInfo`sınıf parametreleri de dahil olmak üzere yeni bir pencere sınıfının bilgilerini kaydeder.|
|[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)|`CWndClassInfo`Mevcut bir sınıfı temel alan ancak farklı bir pencere yordamı kullanan bir pencere sınıfı için bilgileri kaydeder. Bu teknik, superclassing olarak adlandırılır.|

Varsayılan olarak, [CWindowImpl](../../atl/reference/cwindowimpl-class.md) yeni bir `DECLARE_WND_CLASS` pencere sınıfına dayalı bir pencere oluşturmak için makroyu içerir. DECLARE_WND_CLASS, denetim için varsayılan stilleri ve arka plan rengini sağlar. Stili ve arka plan rengini kendiniz belirtmek istiyorsanız, sınıfınızı sınıfından türetebilir `CWindowImpl` ve sınıf tanımınızda declare_wnd_class_ex makrosunu ekleyin.

Varolan bir pencere sınıfına dayalı bir pencere oluşturmak isterseniz, sınıfınızı sınıfından türetebilir `CWindowImpl` ve sınıf tanımınızda declare_wnd_superclass makrosunu ekleyin. Örneğin:

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwndclassinfo-class_1.h)]

Pencere sınıfları hakkında daha fazla bilgi için bkz. Windows SDK [pencere sınıfları](/windows/win32/winmsg/window-classes) .

ATL 'de Windows kullanımı hakkında daha fazla bilgi için bkz. [atl pencere sınıfları](../../atl/atl-window-classes.md)makalesi.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="m_atom"></a>CWndClassInfo:: m_atom

Kayıtlı pencere sınıfı için benzersiz tanımlayıcıyı içerir.

```
ATOM m_atom;
```

##  <a name="m_bsystemcursor"></a>CWndClassInfo:: m_bSystemCursor

TRUE ise, pencere sınıfı kaydedildiğinde sistem imleç kaynağı yüklenir.

```
BOOL m_bSystemCursor;
```

### <a name="remarks"></a>Açıklamalar

Aksi halde, modülünüzün içerdiği imleç kaynağı yüklenir.

`CWndClassInfo`yalnızca `m_bSystemCursor` [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) ( [CWindowImpl](../../atl/reference/cwindowimpl-class.md)içinde varsayılan) veya [declare_wnd_class_ex](window-class-macros.md#declare_wnd_class_ex) makrosu belirtildiğinde kullanır. Bu durumda, `m_bSystemCursor` true olarak başlatılır. Daha fazla bilgi için bkz. [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) 'ya genel bakış.

##  <a name="m_lpszcursorid"></a>CWndClassInfo:: m_lpszCursorID

İmleç kaynağının adını ya da düşük sıralı sözcükteki kaynak tanımlayıcısını ve yüksek sıralı sözcükteki sıfırı belirtir.

```
LPCTSTR m_lpszCursorID;
```

### <a name="remarks"></a>Açıklamalar

Pencere sınıfı kaydedildiğinde, tarafından `m_lpszCursorID` tanımlanan imlece tanıtıcısı alınır ve [m_wc](#m_wc)tarafından depolanır.

`CWndClassInfo`yalnızca `m_lpszCursorID` [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) ( [CWindowImpl](../../atl/reference/cwindowimpl-class.md)içinde varsayılan) veya [declare_wnd_class_ex](window-class-macros.md#declare_wnd_class_ex) makrosu belirtildiğinde kullanır. Bu durumda, `m_lpszCursorID` IDC_ARROW olarak başlatılır. Daha fazla bilgi için bkz. [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) 'ya genel bakış.

##  <a name="m_lpszorigname"></a>CWndClassInfo:: m_lpszOrigName

Varolan bir pencere sınıfının adını içerir.

```
LPCTSTR m_lpszOrigName;
```

### <a name="remarks"></a>Açıklamalar

`CWndClassInfo`yalnızca `m_lpszOrigName` sınıf tanımınızda [declare_wnd_superclass](window-class-macros.md#declare_wnd_superclass) makrosunu dahil ettiğinizde kullanır. Bu durumda, `CWndClassInfo` tarafından `m_lpszOrigName`adlandırılan sınıfına dayalı bir pencere sınıfını kaydeder. Daha fazla bilgi için bkz. [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) 'ya genel bakış.

##  <a name="m_szautoname"></a>CWndClassInfo:: m_szAutoName

Pencere sınıfının adını tutar.

```
TCHAR m_szAutoName[13];
```

### <a name="remarks"></a>Açıklamalar

`CWndClassInfo`yalnızca `m_szAutoName` parametre`WndClassName` için [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class), [declare_wnd_class_ex](window-class-macros.md#declare_wnd_class_ex) veya [declare_wnd_superclass](window-class-macros.md#declare_wnd_superclass)için null geçirildiğinde kullanılır. Windows sınıfı kaydedildiğinde ATL bir ad oluşturur.

##  <a name="m_wc"></a>CWndClassInfo:: m_wc

Bir [WNDCLASSEX](/windows/win32/api/winuser/ns-winuser-wndclassexw) yapısında pencere sınıfı bilgilerini korur.

```
WNDCLASSEX m_wc;
```

### <a name="remarks"></a>Açıklamalar

[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) ( [CWindowImpl](../../atl/reference/cwindowimpl-class.md)içinde varsayılan) veya [declare_wnd_class_ex](window-class-macros.md#declare_wnd_class_ex) makrosunu belirttiyseniz, `m_wc` yeni bir pencere sınıfıyla ilgili bilgiler içerir.

[Declare_wnd_superclass](window-class-macros.md#declare_wnd_superclass) makrosunu belirttiyseniz, `m_wc` var olan bir sınıfı temel alan ancak farklı bir pencere yordamı kullanan bir pencere sınıfı olan bir üst sınıf hakkında bilgi içerir. [m_lpszOrigName](#m_lpszorigname) ve [pWndProc](#pwndproc) , sırasıyla varolan pencere sınıfının adını ve pencere yordamını kaydeder.

##  <a name="pwndproc"></a>CWndClassInfo::p WndProc

Varolan bir pencere sınıfının pencere yordamına işaret eder.

```
WNDPROC pWndProc;
```

### <a name="remarks"></a>Açıklamalar

`CWndClassInfo`yalnızca `pWndProc` sınıf tanımınızda [declare_wnd_superclass](window-class-macros.md#declare_wnd_superclass) makrosunu dahil ettiğinizde kullanır. Bu durumda, `CWndClassInfo` varolan bir sınıfa dayalı ancak farklı bir pencere yordamı kullanan bir pencere sınıfını kaydeder. Varolan pencere sınıfının pencere yordamı ' de `pWndProc`kaydedilir. Daha fazla bilgi için bkz. [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) 'ya genel bakış.

##  <a name="register"></a>CWndClassInfo:: Register

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

[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) ( [CWindowImpl](../../atl/reference/cwindowimpl-class.md)içinde varsayılan) veya [declare_wnd_class_ex](window-class-macros.md#declare_wnd_class_ex) makrosunu belirttiyseniz, `Register` yeni bir pencere sınıfı kaydeder. Bu durumda, *pProc* parametresi kullanılmaz.

[Declare_wnd_superclass](window-class-macros.md#declare_wnd_superclass) makrosunu belirttiyseniz, `Register` var olan bir sınıfı temel alan ancak farklı bir pencere yordamı kullanan bir pencere sınıfı olan bir üst sınıf kaydeder. Mevcut pencere sınıfının pencere yordamı *pProc*içinde döndürülür.

## <a name="see-also"></a>Ayrıca bkz.

[CComControl Sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
