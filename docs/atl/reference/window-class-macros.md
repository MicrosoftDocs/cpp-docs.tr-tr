---
title: Pencere Sınıfı Makroları
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::DECLARE_WND_CLASS
- atlwin/ATL::DECLARE_WND_SUPERCLASS
- atlwin/ATL::DECLARE_WND_CLASS_EX
ms.assetid: ce18681a-2bab-4453-9895-0f3ea47c2b24
ms.openlocfilehash: 18c0912c506bc52421b18d36346204b557c0fc5c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325728"
---
# <a name="window-class-macros"></a>Pencere Sınıfı Makroları

Bu makrolar pencere sınıfı yardımcı programları tanımlar.

|||
|-|-|
|[Declare_wnd_class](#declare_wnd_class)|Yeni bir pencere sınıfının adını belirtmenizi sağlar.|
|[DECLARE_WND_CLASS2](#declare_wnd_class2)|(Visual Studio 2017) Yeni bir pencere sınıfının adını ve yeni sınıfın pencere yordamını kullanacağı çevreleyen sınıfın adını belirtmenizi sağlar.|
|[Declare_wnd_superclass](#declare_wnd_superclass)|Yeni bir pencere sınıfının temel alınacağı varolan bir pencere sınıfının adını belirtmenizi sağlar.|
|[Declare_wnd_class_ex](#declare_wnd_class_ex)|Sınıfın parametrelerini belirtmenizi sağlar.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="declare_wnd_class"></a><a name="declare_wnd_class"></a>Declare_wnd_class

Yeni bir pencere sınıfının adını belirtmenizi sağlar. Bu makroyu ATL ActiveX denetiminin denetim sınıfına yerleştirin.

```
DECLARE_WND_CLASS( WndClassName )
```

### <a name="parameters"></a>Parametreler

*WndClassName*<br/>
[içinde] Yeni pencere sınıfının adı. NULL ise, ATL bir pencere sınıfı adı oluşturur.

### <a name="remarks"></a>Açıklamalar

/izin verici- derleyici seçeneğini kullanıyorsanız, DECLARE_WND_CLASS derleyici hatasına neden olur; bunun yerine DECLARE_WND_CLASS2 kullanın.

DECLARE_WND_CLASS bilgileri [CWndClassInfo](cwndclassinfo-class.md)tarafından yönetilecek yeni bir pencere sınıfının adını belirtmenizi sağlar. DECLARE_WND_CLASS aşağıdaki statik işlevi uygulayarak yeni pencere sınıfını tanımlar:

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

DECLARE_WND_CLASS, yeni pencere için aşağıdaki stilleri belirtir:

- CS_HREDRAW

- CS_VREDRAW

- CS_DBLCLKS

DECLARE_WND_CLASS ayrıca varsayılan pencerenin arka plan rengini de belirtir. Kendi stilleri ve arka plan rengi sağlamak için [DECLARE_WND_CLASS_EX](#declare_wnd_class_ex) makro kullanın.

[CWindowImpl,](cwindowimpl-class.md) yeni bir pencere sınıfına dayalı bir pencere oluşturmak için DECLARE_WND_CLASS makroyu kullanır. Bu davranışı geçersiz kılmak için [DECLARE_WND_SUPERCLASS](#declare_wnd_superclass) makrosunu kullanın veya [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) işlevinikendi uygulamanızı sağlayın.

ATL'de pencere kullanma hakkında daha fazla bilgi için [ATL Pencere Sınıfları](../../atl/atl-window-classes.md)makalesine bakın.

## <a name="declare_wnd_class2"></a><a name="declare_wnd_class2"></a>DECLARE_WND_CLASS2

(Visual Studio 2017) DECLARE_WND_CLASS benzer, ancak /izin verme seçeneği ile derlerken bağımlı ad hatasını önleyen ek bir parametre ile.

```
DECLARE_WND_CLASS2( WndClassName, EnclosingClass )
```

### <a name="parameters"></a>Parametreler

*WndClassName*<br/>
[içinde] Yeni pencere sınıfının adı. NULL ise, ATL bir pencere sınıfı adı oluşturur.

*EnclosingClass*<br/>
[içinde] Yeni pencere sınıfını içine alan pencere sınıfının adı. NULL olamaz.

### <a name="remarks"></a>Açıklamalar

/izin- seçeneğini kullanıyorsanız, DECLARE_WND_CLASS bağımlı bir ad içerdiğinden bir derleme hatasına neden olur. DECLARE_WND_CLASS2, bu makronun kullanıldığı sınıfa açıkça isim vermenizi gerektirir ve /izin veren bayrak altında hataya neden olmaz.
Aksi takdirde bu makro [DECLARE_WND_CLASS](#declare_wnd_class)ile aynıdır.

## <a name="declare_wnd_superclass"></a><a name="declare_wnd_superclass"></a>Declare_wnd_superclass

Sınıfın parametrelerini belirtmenizi sağlar. Bu makroyu ATL ActiveX denetiminin denetim sınıfına yerleştirin.

```
DECLARE_WND_SUPERCLASS( WndClassName, OrigWndClassName )
```

### <a name="parameters"></a>Parametreler

*WndClassName*<br/>
[içinde] *OrigWndClassName*superclass olacak pencere sınıfının adı. NULL ise, ATL bir pencere sınıfı adı oluşturur.

*OrigWndClassName*<br/>
[içinde] Varolan bir pencere sınıfının adı.

### <a name="remarks"></a>Açıklamalar

Bu makro, varolan bir pencere sınıfının üst sınıfını üst sınıfa alacak bir pencere sınıfının adını belirtmenizi sağlar. [CWndClassInfo,](cwndclassinfo-class.md) üst sınıfın bilgilerini yönetir.

DECLARE_WND_SUPERCLASS aşağıdaki statik işlevi uygular:

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

Varsayılan olarak, [CWindowImpl](cwindowimpl-class.md) yeni bir pencere sınıfına dayalı bir pencere oluşturmak için [DECLARE_WND_CLASS](#declare_wnd_class) makrokullanır. DECLARE_WND_SUPERCLASS makroyu türetilmiş `CWindowImpl`bir sınıfta belirterek, pencere sınıfı varolan bir sınıfa dayalı olacaktır, ancak pencere yordamınızı kullanır. Bu teknik superclassing denir.

DECLARE_WND_CLASS ve DECLARE_WND_SUPERCLASS makroları kullanmanın yanı sıra, kendi uygulamanızla [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) işlevini geçersiz kılabilirsiniz.

ATL'de pencere kullanma hakkında daha fazla bilgi için [ATL Pencere Sınıfları](../../atl/atl-window-classes.md)makalesine bakın.

## <a name="declare_wnd_class_ex"></a><a name="declare_wnd_class_ex"></a>Declare_wnd_class_ex

Yeni bir pencere sınıfının temel alınacağı varolan bir pencere sınıfının adını belirtmenizi sağlar. Bu makroyu ATL ActiveX denetiminin denetim sınıfına yerleştirin.

```
DECLARE_WND_CLASS_EX( WndClassName, style, bkgnd )
```

### <a name="parameters"></a>Parametreler

*WndClassName*<br/>
[içinde] Yeni pencere sınıfının adı. NULL ise, ATL bir pencere sınıfı adı oluşturur.

* stili*<br/>
[içinde] Pencerenin stili.

*bkgnd*<br/>
[içinde] Pencerenin arka plan rengi.

### <a name="remarks"></a>Açıklamalar

Bu makro, bilgileri [CWndClassInfo](cwndclassinfo-class.md)tarafından yönetilecek olan yeni bir pencere sınıfının sınıf parametrelerini belirtmenizi sağlar. DECLARE_WND_CLASS_EX aşağıdaki statik işlevi uygulayarak yeni pencere sınıfını tanımlar:

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

Varsayılan stilleri ve arka plan rengini kullanmak istiyorsanız, [makroDECLARE_WND_CLASS](#declare_wnd_class) kullanın. ATL'de pencere kullanma hakkında daha fazla bilgi için [ATL Pencere Sınıfları](../../atl/atl-window-classes.md)makalesine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](atl-macros.md)
