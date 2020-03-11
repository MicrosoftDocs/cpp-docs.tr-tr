---
title: Pencere sınıfı makroları
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::DECLARE_WND_CLASS
- atlwin/ATL::DECLARE_WND_SUPERCLASS
- atlwin/ATL::DECLARE_WND_CLASS_EX
ms.assetid: ce18681a-2bab-4453-9895-0f3ea47c2b24
ms.openlocfilehash: c4617a04c199741b97316122456e417a94275e89
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78862986"
---
# <a name="window-class-macros"></a>Pencere sınıfı makroları

Bu makrolar pencere sınıfı yardımcı programlarını tanımlar.

|||
|-|-|
|[DECLARE_WND_CLASS](#declare_wnd_class)|Yeni bir pencere sınıfının adını belirtmenize izin verir.|
|[DECLARE_WND_CLASS2](#declare_wnd_class2)|(Visual Studio 2017) Yeni bir pencere sınıfının adını ve pencere yordamını yeni sınıfın kullanacağı kapsayan sınıfı belirtmenize olanak tanır.|
|[DECLARE_WND_SUPERCLASS](#declare_wnd_superclass)|Yeni bir pencere sınıfının temel alınacağı varolan bir pencere sınıfının adını belirtmenize olanak tanır.|
|[DECLARE_WND_CLASS_EX](#declare_wnd_class_ex)|Bir sınıfın parametrelerini belirtmenize izin verir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="declare_wnd_class"></a>DECLARE_WND_CLASS

Yeni bir pencere sınıfının adını belirtmenize izin verir. Bu makroyu ATL ActiveX denetiminin denetim sınıfına yerleştirin.

```
DECLARE_WND_CLASS( WndClassName )
```

### <a name="parameters"></a>Parametreler

*WndClassName*<br/>
'ndaki Yeni pencere sınıfının adı. NULL ise, ATL bir pencere sınıfı adı oluşturacaktır.

### <a name="remarks"></a>Açıklamalar

/Permissive-derleyici seçeneğini kullanıyorsanız, DECLARE_WND_CLASS derleyici hatasına neden olur; Bunun yerine DECLARE_WND_CLASS2 kullanın.

DECLARE_WND_CLASS, bilgileri [CWndClassInfo](cwndclassinfo-class.md)tarafından yönetilecek yeni bir pencere sınıfının adını belirtmenize olanak tanır. DECLARE_WND_CLASS, aşağıdaki statik işlevi uygulayarak yeni pencere sınıfını tanımlar:

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

DECLARE_WND_CLASS yeni pencere için aşağıdaki stilleri belirtir:

- CS_HREDRAW

- CS_VREDRAW

- CS_DBLCLKS

DECLARE_WND_CLASS Ayrıca varsayılan pencerenin arka plan rengini belirtir. Kendi stillerinizi ve arka plan renginizi sağlamak için [declare_wnd_class_ex](#declare_wnd_class_ex) makrosunu kullanın.

[CWindowImpl](cwindowimpl-class.md) , yeni bir pencere sınıfını temel alan bir pencere oluşturmak için DECLARE_WND_CLASS makrosunu kullanır. Bu davranışı geçersiz kılmak için [declare_wnd_superclass](#declare_wnd_superclass) makrosunu kullanın ya da [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) işlevinin kendi uygulamanızı sağlayın.

ATL 'de Windows kullanımı hakkında daha fazla bilgi için bkz. [atl pencere sınıfları](../../atl/atl-window-classes.md)makalesi.

##  <a name="declare_wnd_class2"></a>DECLARE_WND_CLASS2

(Visual Studio 2017) DECLARE_WND_CLASS benzer, ancak/Permissive-seçeneğiyle derlerken bağımlı bir ad hatasını önleyen ek bir parametre ile.

```
DECLARE_WND_CLASS2( WndClassName, EnclosingClass )
```

### <a name="parameters"></a>Parametreler

*WndClassName*<br/>
'ndaki Yeni pencere sınıfının adı. NULL ise, ATL bir pencere sınıfı adı oluşturacaktır.

*EnclosingClass*<br/>
'ndaki Yeni pencere sınıfını kapsayan pencere sınıfının adı. NULL olamaz.

### <a name="remarks"></a>Açıklamalar

/Permissive-seçeneğini kullanıyorsanız, DECLARE_WND_CLASS bağımlı bir ad içerdiğinden derleme hatasına neden olur. DECLARE_WND_CLASS2, bu makronun kullanıldığı sınıfı açıkça yazmanız gerekir ve/Permissive-bayrağı altında hataya neden olmaz.
Aksi takdirde, bu makro [DECLARE_WND_CLASS](#declare_wnd_class)benzerdir.

##  <a name="declare_wnd_superclass"></a>DECLARE_WND_SUPERCLASS

Bir sınıfın parametrelerini belirtmenize izin verir. Bu makroyu ATL ActiveX denetiminin denetim sınıfına yerleştirin.

```
DECLARE_WND_SUPERCLASS( WndClassName, OrigWndClassName )
```

### <a name="parameters"></a>Parametreler

*WndClassName*<br/>
'ndaki Üst sınıf *OrigWndClassName*olacak pencere sınıfının adı. NULL ise, ATL bir pencere sınıfı adı oluşturacaktır.

*OrigWndClassName*<br/>
'ndaki Varolan bir pencere sınıfının adı.

### <a name="remarks"></a>Açıklamalar

Bu makro, varolan bir pencere sınıfının üst sınıfını oluşturacak bir pencere sınıfının adını belirtmenize olanak tanır. [CWndClassInfo](cwndclassinfo-class.md) , üst sınıftan bilgileri yönetir.

DECLARE_WND_SUPERCLASS aşağıdaki statik işlevi uygular:

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

Varsayılan olarak, [CWindowImpl](cwindowimpl-class.md) yeni bir pencere sınıfını temel alan bir pencere oluşturmak için [DECLARE_WND_CLASS](#declare_wnd_class) makrosunu kullanır. `CWindowImpl`türetilmiş bir sınıfta DECLARE_WND_SUPERCLASS makrosunu belirterek, pencere sınıfı mevcut bir sınıfı temel alır ancak pencere yordamınız kullanılır. Bu teknik, superclassing olarak adlandırılır.

DECLARE_WND_CLASS ve DECLARE_WND_SUPERCLASS makrolarını kullanmanın yanı sıra, [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) işlevini kendi uygulamanız ile geçersiz kılabilirsiniz.

ATL 'de Windows kullanımı hakkında daha fazla bilgi için bkz. [atl pencere sınıfları](../../atl/atl-window-classes.md)makalesi.

##  <a name="declare_wnd_class_ex"></a>DECLARE_WND_CLASS_EX

Yeni bir pencere sınıfının temel alınacağı varolan bir pencere sınıfının adını belirtmenize olanak tanır. Bu makroyu ATL ActiveX denetiminin denetim sınıfına yerleştirin.

```
DECLARE_WND_CLASS_EX( WndClassName, style, bkgnd )
```

### <a name="parameters"></a>Parametreler

*WndClassName*<br/>
'ndaki Yeni pencere sınıfının adı. NULL ise, ATL bir pencere sınıfı adı oluşturacaktır.

*biçim*<br/>
'ndaki Pencerenin stili.

*arka plan*<br/>
'ndaki Pencerenin arka plan rengi.

### <a name="remarks"></a>Açıklamalar

Bu makro, bilgileri [CWndClassInfo](cwndclassinfo-class.md)tarafından yönetilecek yeni bir pencere sınıfının sınıf parametrelerini belirtmenize olanak tanır. DECLARE_WND_CLASS_EX, aşağıdaki statik işlevi uygulayarak yeni pencere sınıfını tanımlar:

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

Varsayılan stilleri ve arka plan rengini kullanmak istiyorsanız [DECLARE_WND_CLASS](#declare_wnd_class) makrosunu kullanın. ATL 'de Windows kullanımı hakkında daha fazla bilgi için bkz. [atl pencere sınıfları](../../atl/atl-window-classes.md)makalesi.

## <a name="see-also"></a>Ayrıca bkz.

[Larının](atl-macros.md)
