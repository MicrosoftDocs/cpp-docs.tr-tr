---
title: Pencere sınıfı makroları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlwin/ATL::DECLARE_WND_CLASS
- atlwin/ATL::DECLARE_WND_SUPERCLASS
- atlwin/ATL::DECLARE_WND_CLASS_EX
dev_langs:
- C++
ms.assetid: ce18681a-2bab-4453-9895-0f3ea47c2b24
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0e151ba4fc2adbe6dab2397d68658b0cb1eb5ef1
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059083"
---
# <a name="window-class-macros"></a>Pencere sınıfı makroları

Bu makrolar pencere sınıfı yardımcı programları tanımlayın.

|||
|-|-|
|[DECLARE_WND_CLASS](#declare_wnd_class)|Yeni bir pencere sınıfının adını belirtmenizi sağlar.|
|[DECLARE_WND_CLASS2](#declare_wnd_class2)|(Visual Studio 2017) Yeni bir pencere sınıf ve pencere yordamını yeni bir sınıf kullanacağı kapsayan sınıf adını belirtmenizi sağlar.|
|[DECLARE_WND_SUPERCLASS](#declare_wnd_superclass)|Yeni bir pencere sınıf dayanacak var olan bir pencere sınıfı adını belirtmenizi sağlar.|
|[DECLARE_WND_CLASS_EX](#declare_wnd_class_ex)|Bir sınıfın parametreleri belirtmenizi sağlar.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlwin.h

##  <a name="declare_wnd_class"></a>  DECLARE_WND_CLASS

Yeni bir pencere sınıfının adını belirtmenizi sağlar. Bu makro, ATL ActiveX denetiminin denetimi sınıfta yerleştirin.

```
DECLARE_WND_CLASS( WndClassName )
```

### <a name="parameters"></a>Parametreler

*WndClassName*<br/>
[in] Yeni pencere sınıfı adı. NULL ise, ATL pencere sınıfı adı oluşturur.

### <a name="remarks"></a>Açıklamalar

/Permissive-compiler seçeneğini kullanıyorsanız, DECLARE_WND_CLASS bir derleyici hatasına neden olur; Bunun yerine DECLARE_WND_CLASS2 kullanın.

DECLARE_WND_CLASS bilgilerini tarafından yönetilecek yeni bir pencere sınıfının adını belirtmenize olanak verir [Cwndclassınfo](cwndclassinfo-class.md). DECLARE_WND_CLASS aşağıdaki statik işlevi uygulayarak yeni pencere sınıfını tanımlar:

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

DECLARE_WND_CLASS aşağıdaki yeni pencere stillerini belirtir:

- CS_HREDRAW

- CS_VREDRAW

- CS_DBLCLKS

DECLARE_WND_CLASS Ayrıca varsayılan pencerenin arka plan rengini belirtir. Kullanım [DECLARE_WND_CLASS_EX](#declare_wnd_class_ex) makrosu kendi stilleri sağlamak ve arka plan rengi.

[Cwindowımpl](cwindowimpl-class.md) DECLARE_WND_CLASS makrosu yeni bir pencere sınıfını esas bir pencere oluşturmak için kullanır. Bu davranışı geçersiz kılmak için kullanın [DECLARE_WND_SUPERCLASS](#declare_wnd_superclass) makro veya kendi uygulamasını sağlamak [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) işlevi.

ATL kullanarak hakkında daha fazla bilgi için bkz [ATL pencere sınıfları](../../atl/atl-window-classes.md).

##  <a name="declare_wnd_class2"></a>  DECLARE_WND_CLASS2

(Visual Studio 2017) Benzer DECLARE_WND_CLASS, ancak bir ekstra parametresiyle /permissive-option ile derleme yaparken bağımlı adı hatası önler.

```
DECLARE_WND_CLASS2( WndClassName, EnclosingClass )
```

### <a name="parameters"></a>Parametreler

*WndClassName*<br/>
[in] Yeni pencere sınıfı adı. NULL ise, ATL pencere sınıfı adı oluşturur.

*Bulunan EnclosingClass*<br/>
[in] Yeni pencere sınıfını barındırır pencere sınıfı adı. NULL olamaz.

### <a name="remarks"></a>Açıklamalar

/Permissive-option kullanıyorsanız, bağımlı bir ad içerdiğinden ardından DECLARE_WND_CLASS bir derleme hatasına neden olur. DECLARE_WND_CLASS2 açıkça bu makrosu kullanılır ve /permissive-flag altında hatasına neden olmayan bir sınıf adı gerektirir.
Aksi takdirde bu makroyu aynıdır [DECLARE_WND_CLASS](#declare_wnd_class).

##  <a name="declare_wnd_superclass"></a>  DECLARE_WND_SUPERCLASS

Bir sınıfın parametreleri belirtmenizi sağlar. Bu makro, ATL ActiveX denetiminin denetimi sınıfta yerleştirin.

```
DECLARE_WND_SUPERCLASS( WndClassName, OrigWndClassName )
```

### <a name="parameters"></a>Parametreler

*WndClassName*<br/>
[in] Pencerenin adını, sınıfın sınıf *OrigWndClassName*. NULL ise, ATL pencere sınıfı adı oluşturur.

*OrigWndClassName*<br/>
[in] Var olan bir pencere sınıfı adı.

### <a name="remarks"></a>Açıklamalar

Bu makro, sınıfın var olan bir pencere sınıfını bir pencere sınıf adını belirtmenizi sağlar. [Cwndclassınfo](cwndclassinfo-class.md) sınıfın bilgilerini yönetir.

DECLARE_WND_SUPERCLASS aşağıdaki statik işlev uygular:

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

Varsayılan olarak, [Cwindowımpl](cwindowimpl-class.md) kullanan [DECLARE_WND_CLASS](#declare_wnd_class) bir pencere oluşturmak için temel üzerinde yeni bir pencere sınıfı. DECLARE_WND_SUPERCLASS makroda belirterek bir `CWindowImpl`-türetilmiş sınıf, pencere sınıfını mevcut bir sınıfı temel alarak ancak, pencere yordamını kullanır. Bu teknik superclassing çağrılır.

DECLARE_WND_CLASS ve DECLARE_WND_SUPERCLASS makroları kullanmanın yanı sıra, geçersiz kılabilirsiniz [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) kendi uygulamanız ile işlevi.

ATL kullanarak hakkında daha fazla bilgi için bkz [ATL pencere sınıfları](../../atl/atl-window-classes.md).

##  <a name="declare_wnd_class_ex"></a>  DECLARE_WND_CLASS_EX

Yeni bir pencere sınıf dayanacak var olan bir pencere sınıfı adını belirtmenizi sağlar. Bu makro, ATL ActiveX denetiminin denetimi sınıfta yerleştirin.

```
DECLARE_WND_CLASS_EX( WndClassName, style, bkgnd )
```

### <a name="parameters"></a>Parametreler

*WndClassName*<br/>
[in] Yeni pencere sınıfı adı. NULL ise, ATL pencere sınıfı adı oluşturur.

*Stil*<br/>
[in] Pencere stili.

*arka plan*<br/>
[in] Pencerenin arka plan rengi.

### <a name="remarks"></a>Açıklamalar

Bu makro, bilgileri tarafından yönetilecek yeni bir pencere sınıf sınıf parametreleri belirtmenizi sağlar [Cwndclassınfo](cwndclassinfo-class.md). DECLARE_WND_CLASS_EX aşağıdaki statik işlevi uygulayarak yeni pencere sınıfını tanımlar:

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

Arka plan rengi ve varsayılan stilleri kullanmak istiyorsanız, kullanın [DECLARE_WND_CLASS](#declare_wnd_class) makrosu. ATL kullanarak hakkında daha fazla bilgi için bkz [ATL pencere sınıfları](../../atl/atl-window-classes.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları](atl-macros.md)

