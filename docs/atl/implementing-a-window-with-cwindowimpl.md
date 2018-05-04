---
title: CWindowImpl penceresiyle uygulama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CWindowImpl
dev_langs:
- C++
helpviewer_keywords:
- ATL, windows
- windows [C++], subclassing
- windows [C++], superclassing
- windows [C++], ATL
- subclassing ATL window classes
- superclassing, ATL
ms.assetid: 3fc40550-f1d6-4702-8b7c-4cf682b6a855
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9c1fc32d2265f6853c4dd34a3eb463609fca52b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="implementing-a-window-with-cwindowimpl"></a>Bir pencere CWindowImpl ile uygulama
Bir pencere uygulamak için öğesinden bir sınıf türetin `CWindowImpl`. Türetilen sınıfta ileti eşlemesi ve ileti işleyici işlevlerini bildirme. Artık üç farklı yolla sınıfınız kullanabilirsiniz:  
  
-   [Yeni bir Windows sınıfına dayalı bir pencere oluşturma](#_atl_creating_a_window_based_on_a_new_windows_class)  
  
-   [Üst sınıf varolan bir Windows sınıfı](#_atl_superclassing_an_existing_windows_class)  
  
-   [Varolan bir pencereyi alt sınıf](#_atl_subclassing_an_existing_window)  
  
##  <a name="_atl_creating_a_window_based_on_a_new_windows_class"></a> Yeni bir Windows sınıfına dayalı bir pencere oluşturma  
 `CWindowImpl` içeren [DECLARE_WND_CLASS](reference/window-class-macros.md#declare_wnd_class) makrosu Windows sınıf bilgileri bildirin. Bu makrosu uygulayan `GetWndClassInfo` kullanan işlevi [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) yeni bir Windows sınıf bilgileri tanımlamak için. Zaman `CWindowImpl::Create` çağrılır, bu Windows sınıfı kaydedilir ve yeni bir pencere oluşturulur.  
  
> [!NOTE]
>  `CWindowImpl` geçirir **NULL** için `DECLARE_WND_CLASS` makro ATL Windows sınıf adı oluşturacağını anlamına gelir. Kendi adını belirtmek için bir dizeyi geçirmek `DECLARE_WND_CLASS` içinde `CWindowImpl`-türetilmiş sınıf.  
  
## <a name="example"></a>Örnek  
 Yeni bir Windows sınıfına dayalı bir pencere uygulayan bir sınıf örneği aşağıdadır:  
  
 [!code-cpp[NVC_ATL_Windowing#64](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_1.h)]  
  
 Bir pencere oluşturmak için bir örneğini oluşturmak `CMyWindow` ve ardından arama **oluşturma** yöntemi.  
  
> [!NOTE]
>  Varsayılan Windows sınıfı bilgilerini geçersiz kılmak için uygulama `GetWndClassInfo` ayarlayarak, türetilmiş sınıf yönteminde `CWndClassInfo` uygun değerleri üyelerine.  
  
##  <a name="_atl_superclassing_an_existing_windows_class"></a> Üst Sınıflama varolan bir Windows sınıfı  
 [DECLARE_WND_SUPERCLASS](reference/window-class-macros.md#declare_wnd_superclass) makrosu bir pencere bu aktarılabileceği bir mevcut Windows oluşturmanıza imkan tanır sınıfı. Bu makrosu belirtin, `CWindowImpl`-türetilmiş sınıf. Diğer ATL pencere gibi iletileri ileti eşlemesi tarafından işlenir.  
  
 Kullandığınızda `DECLARE_WND_SUPERCLASS`, yeni bir Windows sınıf kaydedilir. Bu yeni sınıf belirtin, ancak pencere yordamını değiştirecek varolan sınıf ile aynı olacak `CWindowImpl::WindowProc` (ya da bu yöntemi geçersiz kılar, işlevi).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki sınıf, o aktarılabileceği standart düzenleme örneğidir sınıfı:  
  
 [!code-cpp[NVC_ATL_Windowing#65](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_2.h)]  
  
 Superclassed düzenleme penceresini oluşturmak için bir örneğini oluşturmak `CMyEdit` ve ardından arama **oluşturma** yöntemi.  
  
##  <a name="_atl_subclassing_an_existing_window"></a> Varolan bir pencereyi alt sınıf yapma  
 Varolan bir pencereyi alt sınıf için öğesinden bir sınıf türetin `CWindowImpl` ve iki önceki durumda olduğu gibi bir ileti eşlemesi bildirin. Ancak, zaten varolan bir pencereyi alt sınıf olur beri herhangi bir Windows sınıfı bilgisi belirtmeyin unutmayın.  
  
 Çağırmak yerine **oluşturma**, çağrı `SubclassWindow` ve bir alt kümesi için istediğiniz varolan penceresine tanıtıcı geçirin. Pencerenin sınıflandırma sonra kullanacaktır `CWindowImpl::WindowProc` (veya bu yöntemi geçersiz kılar, işlevi) ileti eşlemesi iletilerini yönlendirmek için. Nesnenizin altsınıflanmış penceresinden ayırmak için çağrı `UnsubclassWindow`. Pencerenin özgün pencere yordamı sonra geri yüklenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere Uygulama](../atl/implementing-a-window.md)

