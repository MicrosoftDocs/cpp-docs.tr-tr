---
title: CWndClassInfo Sınıfı
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
ms.openlocfilehash: 01706bf61c3b977c28998325ece68724cfbc7452
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330331"
---
# <a name="cwndclassinfo-class"></a>CWndClassInfo Sınıfı

Bu sınıf, bir pencere sınıfı için bilgi kaydetmek için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CWndClassInfo
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|[Kaydet](#register)|Pencere sınıfını kaydeder.|

### <a name="data-members"></a>Veri Üyeleri

|||
|-|-|
|[m_atom](#m_atom)|Kayıtlı pencere sınıfını benzersiz olarak tanımlar.|
|[m_bSystemCursor](#m_bsystemcursor)|İmleç kaynağının bir sistem imlecine mi yoksa modül kaynağında bulunan bir imleçe mi atıfta bulunduğunu belirtir.|
|[m_lpszCursorID](#m_lpszcursorid)|İmleç kaynağının adını belirtir.|
|[m_lpszOrigName](#m_lpszorigname)|Varolan bir pencere sınıfının adını içerir.|
|[m_szAutoName](#m_szautoname)|Pencere sınıfının ATL tarafından oluşturulan bir adını tutar.|
|[m_wc](#m_wc)|Pencere sınıfı bilgilerini bir `WNDCLASSEX` yapıda tutar.|
|[pWndProc](#pwndproc)|Varolan bir pencere sınıfının pencere yordamını işaret ediyor.|

## <a name="remarks"></a>Açıklamalar

`CWndClassInfo`bir pencere sınıfının bilgilerini yönetir. Genellikle aşağıdaki `CWndClassInfo` tabloda açıklandığı gibi, DECLARE_WND_CLASS, DECLARE_WND_CLASS_EX veya DECLARE_WND_SUPERCLASS olmak üzere üç makrodan birini kullanırsınız:

|Makro|Açıklama|
|-----------|-----------------|
|[Declare_wnd_class](window-class-macros.md#declare_wnd_class)|`CWndClassInfo`yeni bir pencere sınıfı için bilgileri kaydeder.|
|[Declare_wnd_class_ex](window-class-macros.md#declare_wnd_class_ex)|`CWndClassInfo`sınıf parametreleri de dahil olmak üzere yeni bir pencere sınıfı için bilgileri kaydeder.|
|[Declare_wnd_superclass](window-class-macros.md#declare_wnd_superclass)|`CWndClassInfo`varolan bir sınıfa dayanan ancak farklı bir pencere yordamı kullanan bir pencere sınıfı için bilgileri kaydeder. Bu teknik superclassing denir.|

Varsayılan olarak, [CWindowImpl](../../atl/reference/cwindowimpl-class.md) yeni bir pencere sınıfına dayalı bir pencere oluşturmak için `DECLARE_WND_CLASS` makro içerir. DECLARE_WND_CLASS denetim için varsayılan stilleri ve arka plan rengini sağlar. Stili ve arka plan rengini kendiniz belirtmek istiyorsanız, `CWindowImpl` sınıfınızdan türetin ve DECLARE_WND_CLASS_EX makroyu sınıf tanımınıza ekleyin.

Varolan bir pencere sınıfına dayalı bir pencere oluşturmak istiyorsanız, sınıfınızı türetin `CWindowImpl` ve DECLARE_WND_SUPERCLASS makroyu sınıf tanımınıza ekleyin. Örneğin:

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwndclassinfo-class_1.h)]

Pencere sınıfları hakkında daha fazla bilgi için Windows SDK'daki [Pencere Sınıfları'na](/windows/win32/winmsg/window-classes) bakın.

ATL'de pencere kullanma hakkında daha fazla bilgi için [ATL Pencere Sınıfları](../../atl/atl-window-classes.md)makalesine bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="cwndclassinfom_atom"></a><a name="m_atom"></a>CWndClassInfo::m_atom

Kayıtlı pencere sınıfı için benzersiz tanımlayıcıyı içerir.

```
ATOM m_atom;
```

## <a name="cwndclassinfom_bsystemcursor"></a><a name="m_bsystemcursor"></a>CWndClassInfo::m_bSystemCursor

TRUE ise, pencere sınıfı kaydedildiğinde sistem imleci kaynağı yüklenir.

```
BOOL m_bSystemCursor;
```

### <a name="remarks"></a>Açıklamalar

Aksi takdirde, modülünüzde bulunan imleç kaynağı yüklenir.

`CWndClassInfo`yalnızca `m_bSystemCursor` [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) [(CWindowImpl'deki](../../atl/reference/cwindowimpl-class.md)varsayılan değer) veya [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) makro belirtildiğinde kullanır. Bu durumda, `m_bSystemCursor` TRUE için başharf. Daha fazla bilgi için [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) genel görünümüne bakın.

## <a name="cwndclassinfom_lpszcursorid"></a><a name="m_lpszcursorid"></a>CWndClassInfo::m_lpszCursorID

İmleç kaynağının adını veya kaynak tanımlayıcısını düşük sıralı sözcükte ve yüksek sıralı sözcükte sıfır olarak belirtir.

```
LPCTSTR m_lpszCursorID;
```

### <a name="remarks"></a>Açıklamalar

Pencere sınıfı kaydedildiğinde, imleç tarafından `m_lpszCursorID` tanımlanan tanıtıcı [m_wc](#m_wc)tarafından alınır ve saklanır.

`CWndClassInfo`yalnızca `m_lpszCursorID` [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) [(CWindowImpl'deki](../../atl/reference/cwindowimpl-class.md)varsayılan değer) veya [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) makro belirtildiğinde kullanır. Bu durumda, `m_lpszCursorID` IDC_ARROW için başharf. Daha fazla bilgi için [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) genel görünümüne bakın.

## <a name="cwndclassinfom_lpszorigname"></a><a name="m_lpszorigname"></a>CWndClassInfo::m_lpszOrigName

Varolan bir pencere sınıfının adını içerir.

```
LPCTSTR m_lpszOrigName;
```

### <a name="remarks"></a>Açıklamalar

`CWndClassInfo`yalnızca `m_lpszOrigName` sınıf tanımınıza [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) makroyu eklediğinizde kullanır. Bu durumda, `CWndClassInfo` `m_lpszOrigName`'' tarafından adlandırılmış sınıfa göre bir pencere sınıfı kaydeder. Daha fazla bilgi için [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) genel görünümüne bakın.

## <a name="cwndclassinfom_szautoname"></a><a name="m_szautoname"></a>CWndClassInfo::m_szAutoName

Pencere sınıfının adını tutar.

```
TCHAR m_szAutoName[13];
```

### <a name="remarks"></a>Açıklamalar

`CWndClassInfo`yalnızca `m_szAutoName` NULL `WndClassName` parametresi için [DECLARE_WND_CLASS,](window-class-macros.md#declare_wnd_class) [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) veya [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)geçirilirse kullanır. Pencere sınıfı kaydedildiğinde ATL bir ad inşa edecektir.

## <a name="cwndclassinfom_wc"></a><a name="m_wc"></a>CWndClassInfo::m_wc

PENCERE sınıfı bilgilerini [WNDCLASSEX](/windows/win32/api/winuser/ns-winuser-wndclassexw) yapısında tutar.

```
WNDCLASSEX m_wc;
```

### <a name="remarks"></a>Açıklamalar

[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) [(CWindowImpl'deki](../../atl/reference/cwindowimpl-class.md)varsayılan varsayılan) veya [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) makrosu belirttiyseniz, `m_wc` yeni bir pencere sınıfı hakkında bilgi içerir.

[MakroDECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) belirttiyseniz, `m_wc` varolan bir sınıfa dayanan ancak farklı bir pencere yordamı kullanan bir pencere sınıfı olan bir üst sınıf hakkında bilgi içerir. [m_lpszOrigName](#m_lpszorigname) ve [pWndProc,](#pwndproc) sırasıyla varolan pencere sınıfının adını ve pencere yordamını kaydeder.

## <a name="cwndclassinfopwndproc"></a><a name="pwndproc"></a>CWndClassInfo::pWndProc

Varolan bir pencere sınıfının pencere yordamını işaret ediyor.

```
WNDPROC pWndProc;
```

### <a name="remarks"></a>Açıklamalar

`CWndClassInfo`yalnızca `pWndProc` sınıf tanımınıza [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) makroyu eklediğinizde kullanır. Bu durumda, `CWndClassInfo` varolan bir sınıfa dayalı ancak farklı bir pencere yordamı kullanan bir pencere sınıfı kaydeder. Varolan pencere sınıfının pencere yordamı `pWndProc`. Daha fazla bilgi için [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) genel görünümüne bakın.

## <a name="cwndclassinforegister"></a><a name="register"></a>CWndClassInfo::Kayıt

[CWindowImpl tarafından çağrılan::Henüz](../../atl/reference/cwindowimpl-class.md#create) kaydedilmemişse pencere sınıfını kaydetmek için oluştur.

```
ATOM Register(WNDPROC* pProc);
```

### <a name="parameters"></a>Parametreler

*pProc*<br/>
[çıkış] Varolan bir pencere sınıfının özgün pencere yordamını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, kayıtlı olan pencere sınıfını benzersiz olarak tanımlayan bir atom. Aksi takdirde, 0.

### <a name="remarks"></a>Açıklamalar

[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) [(CWindowImpl'deki](../../atl/reference/cwindowimpl-class.md)varsayılan varsayılan) veya [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) makroyu belirttiyseniz, `Register` yeni bir pencere sınıfı kaydeder. Bu *durumda, pProc* parametresi kullanılmaz.

[MakroDECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) belirttiyseniz, `Register` varolan bir sınıfa dayanan ancak farklı bir pencere yordamı kullanan bir pencere sınıfı olan bir üst sınıf kaydeder. Varolan pencere sınıfının pencere yordamı *pProc*döndürülür.

## <a name="see-also"></a>Ayrıca bkz.

[CComControl Sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
