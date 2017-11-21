---
title: "Pencere sınıfı makroları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlwin/ATL::DECLARE_WND_CLASS
- atlwin/ATL::DECLARE_WND_SUPERCLASS
- atlwin/ATL::DECLARE_WND_CLASS_EX
dev_langs: C++
ms.assetid: ce18681a-2bab-4453-9895-0f3ea47c2b24
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e952c19d5cb52be1f2d2ab727049e92cf3625f5f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="window-class-macros"></a>Pencere sınıfı makroları
Bu makroları pencere sınıfı yardımcı programları tanımlayın.  
  
|||  
|-|-|  
|[DECLARE_WND_CLASS](#declare_wnd_class)|Yeni bir pencere sınıfı adını belirtmenize olanak tanır.| 
|[DECLARE_WND_CLASS2](#declare_wnd_class2)|(Visual Studio 2017) Yeni bir pencere sınıfı ve pencere yordamı yeni sınıf kullanacağı kapsayan sınıfın adını belirtmenize olanak tanır.| 
|[DECLARE_WND_SUPERCLASS](#declare_wnd_superclass)|Yeni bir pencere sınıfı dayanacak varolan bir pencere sınıfı adını belirtmenize olanak tanır.|  
|[DECLARE_WND_CLASS_EX](#declare_wnd_class_ex)|Bir sınıf parametrelerinin belirtmenize olanak tanır.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
   
##  <a name="declare_wnd_class"></a>DECLARE_WND_CLASS  
 Yeni bir pencere sınıfı adını belirtmenize olanak tanır. Bu makrosu bir ATL ActiveX denetiminin denetimi sınıfta yerleştirin.  
  
```
DECLARE_WND_CLASS( WndClassName )
```  
  
### <a name="parameters"></a>Parametreler  
 `WndClassName`  
 [in] Yeni pencere sınıfı adı. Varsa **NULL**, ATL pencere sınıfı adı üretir.  
  
### <a name="remarks"></a>Açıklamalar  
 /Permissive-compiler seçeneğini kullanıyorsanız, DECLARE_WND_CLASS derleyici hatası neden olur; Bunun yerine DECLARE_WND_CLASS2 kullanın.
 
 DECLARE_WND_CLASS, bilgileri tarafından yönetilecek yeni bir pencere sınıfı adını belirtmenize olanak verir [CWndClassInfo](cwndclassinfo-class.md). `DECLARE_WND_CLASS`aşağıdaki statik işlevi uygulayarak yeni pencere sınıfı tanımlar:  
  
 [!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 `DECLARE_WND_CLASS`Yeni pencerede aşağıdaki stillerini belirtir:  
  
-   CS_HREDRAW  
  
-   CS_VREDRAW  
  
-   CS_DBLCLKS  
  
 `DECLARE_WND_CLASS`Ayrıca varsayılan pencerenin arka plan rengini belirtir. Kullanım [DECLARE_WND_CLASS_EX](#declare_wnd_class_ex) makrosu kendi stil sağlamak ve arka plan rengi.  
  
 [CWindowImpl](cwindowimpl-class.md) kullanan `DECLARE_WND_CLASS` makrosu bir pencere oluşturmak için temel üzerinde yeni bir pencere sınıfı. Bu davranışı geçersiz kılmak için kullanın [DECLARE_WND_SUPERCLASS](#declare_wnd_superclass) makro veya kendi belirtin [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) işlevi.  

  
 ATL Windows'da kullanma hakkında daha fazla bilgi için bkz: [ATL pencere sınıfları](../../atl/atl-window-classes.md).  

##  <a name="declare_wnd_class2"></a>DECLARE_WND_CLASS2  
 (Visual Studio 2017) Benzer DECLARE_WND_CLASS, ancak bir ek parametresiyle bağımlı adı hatası ile /permissive-option derlerken önler.
  
```
DECLARE_WND_CLASS2( WndClassName, EnclosingClass )
```  
  
### <a name="parameters"></a>Parametreler  
 `WndClassName`  
 [in] Yeni pencere sınıfı adı. Varsa **NULL**, ATL pencere sınıfı adı üretir. 

 `EnclosingClass`  
 [in] Yeni pencere sınıfı barındırır pencere sınıfı adı. Olamaz **NULL**.  
  
### <a name="remarks"></a>Açıklamalar 
/Permissive-option kullanıyorsanız, bağımlı adı içerdiğinden sonra DECLARE_WND_CLASS derleme hatası neden olur. DECLARE_WND_CLASS2 açıkça bu makrosu kullanılır ve /permissive-flag altında hata neden olmaz ve sınıf adını gerektirir.
Aksi takdirde bu makrosu aynıdır [DECLARE_WND_CLASS](#declare_wnd_class).
   
##  <a name="declare_wnd_superclass"></a>DECLARE_WND_SUPERCLASS  
 Bir sınıf parametrelerinin belirtmenize olanak tanır. Bu makrosu bir ATL ActiveX denetiminin denetimi sınıfta yerleştirin.  
  
```
DECLARE_WND_SUPERCLASS( WndClassName, OrigWndClassName )
```  
  
### <a name="parameters"></a>Parametreler  
 `WndClassName`  
 [in] Pencerenin adını sınıfı bu sınıfın `OrigWndClassName`. Varsa **NULL**, ATL pencere sınıfı adı üretir.  
  
 `OrigWndClassName`  
 [in] Varolan bir pencere sınıfı adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makrosu sınıfın var olan bir pencere sınıfı olacak bir pencere sınıfı adını belirtmenize olanak tanır. [CWndClassInfo](cwndclassinfo-class.md) sınıfın bilgilerini yönetir.  
  
 `DECLARE_WND_SUPERCLASS`aşağıdaki statik işlev uygular:  
  
 [!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 Varsayılan olarak, [CWindowImpl](cwindowimpl-class.md) kullanan [DECLARE_WND_CLASS](#declare_wnd_class) makrosu bir pencere oluşturmak için temel üzerinde yeni bir pencere sınıfı. Belirterek `DECLARE_WND_SUPERCLASS` makro bir `CWindowImpl`-türetilmiş sınıf, pencere sınıfı üzerinde varolan bir sınıfa bağlı, ancak pencere yordamı kullanın. Bu teknik üst Sınıflama adı verilir.  
  
 Kullanarak yanı sıra `DECLARE_WND_CLASS` ve `DECLARE_WND_SUPERCLASS` makroları kılabilirsiniz [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) kendi uygulama işlevi.  

  
 ATL Windows'da kullanma hakkında daha fazla bilgi için bkz: [ATL pencere sınıfları](../../atl/atl-window-classes.md).  
  
##  <a name="declare_wnd_class_ex"></a>DECLARE_WND_CLASS_EX  
 Yeni bir pencere sınıfı dayanacak varolan bir pencere sınıfı adını belirtmenize olanak tanır. Bu makrosu bir ATL ActiveX denetiminin denetimi sınıfta yerleştirin.  
  
```
DECLARE_WND_CLASS_EX( WndClassName, style, bkgnd )
```  
  
### <a name="parameters"></a>Parametreler  
 `WndClassName`  
 [in] Yeni pencere sınıfı adı. Varsa **NULL**, ATL pencere sınıfı adı üretir.  
  
 `style`  
 [in] Pencere stili.  
  
 *arka plan*  
 [in] Pencerenin arka plan rengi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makrosu bilgilerini tarafından yönetilecek yeni bir pencere sınıfı sınıfı parametrelerinin belirtmenize olanak tanır [CWndClassInfo](cwndclassinfo-class.md). `DECLARE_WND_CLASS_EX`aşağıdaki statik işlevi uygulayarak yeni pencere sınıfı tanımlar:  
  
 [!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 Varsayılan stillerini ve arka plan rengini kullanmak istiyorsanız, kullanmak [DECLARE_WND_CLASS](#declare_wnd_class) makrosu. ATL Windows'da kullanma hakkında daha fazla bilgi için bkz: [ATL pencere sınıfları](../../atl/atl-window-classes.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları](atl-macros.md)









