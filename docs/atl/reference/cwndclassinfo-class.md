---
title: Cwndclassınfo sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CWndClassInfo class
ms.assetid: c36fe7e1-75f1-4cf5-a06f-9f59c43fe6fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d674b2e3049d27f0e79eb082a44640f67a395dea
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097908"
---
# <a name="cwndclassinfo-class"></a>Cwndclassınfo sınıfı

Bu sınıf, bir pencere sınıfının bilgileri kaydetmek için yöntemler sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CWndClassInfo
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|[Kaydolun](#register)|Pencere sınıfını kaydeder.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[m_atom](#m_atom)|Kayıtlı pencere sınıfı benzersiz olarak tanımlar.|
|[m_bSystemCursor](#m_bsystemcursor)|İmleç kaynak sistemi imleç veya modül kaynakta yer alan bir imleç gösterir olup olmadığını belirtir.|
|[m_lpszCursorID](#m_lpszcursorid)|İmleç kaynağının adını belirtir.|
|[m_lpszOrigName](#m_lpszorigname)|Var olan bir pencere sınıfı adını içerir.|
|[m_szAutoName](#m_szautoname)|ATL tarafından oluşturulan bir pencere sınıfı adını içerir.|
|[m_wc](#m_wc)|Pencere sınıfı bilgileri tutar bir `WNDCLASSEX` yapısı.|
|[pWndProc](#pwndproc)|Pencere yordamı işaret var olan bir pencere sınıf.|

## <a name="remarks"></a>Açıklamalar

`CWndClassInfo` pencere sınıfı bilgilerini yönetir. Tipik olarak kullandığınız `CWndClassInfo` üç makroları, DECLARE_WND_CLASS, DECLARE_WND_CLASS_EX veya aşağıdaki tabloda açıklandığı gibi DECLARE_WND_SUPERCLASS biri aracılığıyla:

|Makrosu|Açıklama|
|-----------|-----------------|
|[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)|`CWndClassInfo` bilgi için yeni bir pencere sınıfını kaydeder.|
|[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)|`CWndClassInfo` sınıf parametreleri de dahil olmak üzere yeni bir pencere sınıf için bilgileri kaydeder.|
|[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)|`CWndClassInfo` bilgi için farklı pencere yordamını kullanır ancak mevcut bir sınıfı temel alan bir pencere sınıfını kaydeder. Bu teknik superclassing çağrılır.|

Varsayılan olarak, [Cwindowımpl](../../atl/reference/cwindowimpl-class.md) içerir `DECLARE_WND_CLASS` bir pencere oluşturmak için temel üzerinde yeni bir pencere sınıfı. DECLARE_WND_CLASS varsayılan stillerini ve arka plan rengi için bir denetim sağlar. Kendiniz arka plan rengi ve stilini belirtmek istiyorsanız, sınıfından türetilir `CWindowImpl` ve DECLARE_WND_CLASS_EX makrosu, sınıf tanımına ekleyin.

Var olan bir pencere sınıfını esas bir pencere oluşturmak istiyorsanız, sınıfından türetilir `CWindowImpl` ve DECLARE_WND_SUPERCLASS makrosu, sınıf tanımına ekleyin. Örneğin:

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwndclassinfo-class_1.h)]

Pencere sınıfları hakkında daha fazla bilgi için bkz: [pencere sınıfları](https://msdn.microsoft.com/library/windows/desktop/ms632596) Windows SDK.

ATL kullanarak hakkında daha fazla bilgi için bkz [ATL pencere sınıfları](../../atl/atl-window-classes.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlwin.h

##  <a name="m_atom"></a>  CWndClassInfo::m_atom

Kayıtlı pencere sınıfı için benzersiz tanımlayıcı içerir.

```
ATOM m_atom;
```

##  <a name="m_bsystemcursor"></a>  CWndClassInfo::m_bSystemCursor

TRUE ise pencere sınıfını kaydedildiğinde sistem imleç kaynak yüklenir.

```
BOOL m_bSystemCursor;
```

### <a name="remarks"></a>Açıklamalar

Aksi takdirde, bir modülde içerilen imleç kaynak yüklenir.

`CWndClassInfo` kullanan `m_bSystemCursor` yalnızca [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (varsayılan olarak [Cwindowımpl](../../atl/reference/cwindowimpl-class.md)) veya [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) makrosu belirtildi. Bu durumda, `m_bSystemCursor` TRUE olarak başlatılır. Daha fazla bilgi için [Cwndclassınfo](../../atl/reference/cwndclassinfo-class.md) genel bakış.

##  <a name="m_lpszcursorid"></a>  CWndClassInfo::m_lpszCursorID

Düşük düzey word ve sıfır dwpoint imleç kaynağının adını ya da kaynak tanımlayıcı belirtir.

```
LPCTSTR m_lpszCursorID;
```

### <a name="remarks"></a>Açıklamalar

Pencere sınıfı zaman kaydedildi, tanıtıcı tarafından tanımlanan imlece kadar `m_lpszCursorID` alınır ve tarafından depolanan [m_wc](#m_wc).

`CWndClassInfo` kullanan `m_lpszCursorID` yalnızca [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (varsayılan olarak [Cwindowımpl](../../atl/reference/cwindowimpl-class.md)) veya [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) makrosu belirtildi. Bu durumda, `m_lpszCursorID` IDC_ARROW için başlatılır. Daha fazla bilgi için [Cwndclassınfo](../../atl/reference/cwndclassinfo-class.md) genel bakış.

##  <a name="m_lpszorigname"></a>  CWndClassInfo::m_lpszOrigName

Var olan bir pencere sınıfı adını içerir.

```
LPCTSTR m_lpszOrigName;
```

### <a name="remarks"></a>Açıklamalar

`CWndClassInfo` kullanan `m_lpszOrigName` eklediğinizde yalnızca [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) sınıfı Tanımınızda makrosu. Bu durumda, `CWndClassInfo` pencere sınıfını temel alan tarafından adlandırılan sınıftaki kayıtlarla `m_lpszOrigName`. Daha fazla bilgi için [Cwndclassınfo](../../atl/reference/cwndclassinfo-class.md) genel bakış.

##  <a name="m_szautoname"></a>  CWndClassInfo::m_szAutoName

Pencere sınıfı adını içerir.

```
TCHAR m_szAutoName[13];
```

### <a name="remarks"></a>Açıklamalar

`CWndClassInfo` kullanan `m_szAutoName` NULL geçirilirse yalnızca `WndClassName` parametresi [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class), [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) veya [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) . Pencere sınıfı kaydedildiğinde ATL bir ad oluşturmak.

##  <a name="m_wc"></a>  CWndClassInfo::m_wc

Pencere sınıfı bilgileri tutar bir [WNDCLASSEX](https://msdn.microsoft.com/library/windows/desktop/ms633577) yapısı.

```
WNDCLASSEX m_wc;
```

### <a name="remarks"></a>Açıklamalar

Belirttiyseniz [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (varsayılan olarak [Cwindowımpl](../../atl/reference/cwindowimpl-class.md)) veya [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) makro `m_wc` hakkında bilgi içeren bir Yeni pencere sınıfı.

Belirttiyseniz [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) makro `m_wc` bir üst sınıf hakkında bilgi içerir — farklı pencere yordamını kullanır ancak mevcut bir sınıfı temel alan bir pencere sınıf. [m_lpszOrigName](#m_lpszorigname) ve [pWndProc](#pwndproc) mevcut pencere sınıfının adını ve pencere yordamını sırasıyla kaydedin.

##  <a name="pwndproc"></a>  CWndClassInfo::pWndProc

Pencere yordamı işaret var olan bir pencere sınıf.

```
WNDPROC pWndProc;
```

### <a name="remarks"></a>Açıklamalar

`CWndClassInfo` kullanan `pWndProc` eklediğinizde yalnızca [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) sınıfı Tanımınızda makrosu. Bu durumda, `CWndClassInfo` farklı pencere yordamını kullanır ancak mevcut bir sınıfı temel alan bir pencere sınıfını kaydeder. Var olan pencereyi sınıfın pencere yordamını kaydedilir `pWndProc`. Daha fazla bilgi için [Cwndclassınfo](../../atl/reference/cwndclassinfo-class.md) genel bakış.

##  <a name="register"></a>  CWndClassInfo::Register

Çağıran [CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create) henüz kayıtlı değilse, pencere sınıfını kaydedilecek.

```
ATOM Register(WNDPROC* pProc);
```

### <a name="parameters"></a>Parametreler

*pProc*<br/>
[out] Özgün pencere yordamını, var olan bir pencere sınıfını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, atom, benzersiz olarak Kaydedilmekte pencere sınıfını tanımlar. Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Belirttiyseniz [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (varsayılan olarak [Cwindowımpl](../../atl/reference/cwindowimpl-class.md)) veya [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) makro `Register` yeni bir pencere sınıfını kaydeder. Bu durumda, *pProc* parametre kullanılmaz.

Belirttiyseniz [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) makro `Register` bir sınıfın kaydeder; farklı pencere yordamını kullanır ancak mevcut bir sınıfı temel alan bir pencere sınıf. Var olan pencereyi sınıfın pencere yordamını döndürülür *pProc*.

## <a name="see-also"></a>Ayrıca Bkz.

[CComControl Sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)