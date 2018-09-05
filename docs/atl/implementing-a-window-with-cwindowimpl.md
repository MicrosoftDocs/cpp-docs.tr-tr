---
title: Cwindowımpl ile pencere uygulama | Microsoft Docs
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
ms.openlocfilehash: 2333c56586d20bc5ec114b8ea8a8811e72fcd755
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43763425"
---
# <a name="implementing-a-window-with-cwindowimpl"></a>Cwindowımpl ile pencere uygulama

Bir pencere uygulamak için öğesinden bir sınıf türetin `CWindowImpl`. Türetilmiş sınıfınızın ileti eşlemesi ve ileti işleyici işlevlerini bildirme. Artık üç farklı yolla sınıfınıza kullanabilirsiniz:

- [Yeni bir Windows sınıfını esas bir pencere oluşturma](#_atl_creating_a_window_based_on_a_new_windows_class)

- [Sınıfın var olan bir Windows sınıfı](#_atl_superclassing_an_existing_windows_class)

- [Var olan bir pencere öğesinin alt sınıfı](#_atl_subclassing_an_existing_window)

##  <a name="_atl_creating_a_window_based_on_a_new_windows_class"></a> Yeni bir Windows sınıfını esas bir pencere oluşturma

`CWindowImpl` içeren [DECLARE_WND_CLASS](reference/window-class-macros.md#declare_wnd_class) Windows sınıf bilgilerini bildirmek için makrosu. Bu makro uygulayan `GetWndClassInfo` kullanan işlevi [Cwndclassınfo](../atl/reference/cwndclassinfo-class.md) yeni bir Windows sınıf bilgilerini tanımlamak için. Zaman `CWindowImpl::Create` çağrılır, bu Windows sınıfı kaydedilir ve yeni bir pencere oluşturulur.

> [!NOTE]
>  `CWindowImpl` NULL geçirir `DECLARE_WND_CLASS` makrosu, ATL, Windows sınıf adı oluşturacağını anlamına gelir. Kendi adınızı belirtmek için DECLARE_WND_CLASS bir dizeyi geçirmek, `CWindowImpl`-türetilmiş sınıf.

## <a name="example"></a>Örnek

Yeni bir Windows sınıfını esas pencere uygulayan bir sınıfın bir örneği verilmiştir:

[!code-cpp[NVC_ATL_Windowing#64](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_1.h)]

Bir pencere oluşturmak için bir örneğini oluşturmak `CMyWindow` ve sonra çağrı `Create` yöntemi.

> [!NOTE]
>  Varsayılan Windows sınıf bilgilerini geçersiz kılmak için uygulama `GetWndClassInfo` ayarlayarak türetilmiş sınıfınızın yönteminde `CWndClassInfo` üyeleri için uygun değerleri.

##  <a name="_atl_superclassing_an_existing_windows_class"></a> Superclassing varolan bir Windows sınıfı

[DECLARE_WND_SUPERCLASS](reference/window-class-macros.md#declare_wnd_superclass) makrosu, mevcut bir Windows aktarılabileceği bir pencere oluşturmanıza imkan tanır sınıfı. Bu makro belirtin, `CWindowImpl`-türetilmiş sınıf. Diğer ATL pencere gibi iletileri ileti eşlemesi tarafından işlenir.

DECLARE_WND_SUPERCLASS kullandığınızda, yeni bir Windows sınıf kaydedilir. Bu yeni bir sınıf belirtin, ancak pencere yordamını yerini alacak varolan sınıf ile aynı olacaktır `CWindowImpl::WindowProc` (veya bu metodu geçersiz kılar, işlevinizi ile).

## <a name="example"></a>Örnek

Aşağıdaki bir sınıf, o aktarılabileceği standart düzenleme örneğidir sınıfı:

[!code-cpp[NVC_ATL_Windowing#65](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_2.h)]

Üst düzen pencere oluşturmak için bir örneğini oluşturmak `CMyEdit` ve sonra çağrı `Create` yöntemi.

##  <a name="_atl_subclassing_an_existing_window"></a> Var olan bir pencereyi alt sınıf yapma

Varolan pencereye alt sınıfı için öğesinden bir sınıf türetin `CWindowImpl` ve iki önceki durumda olduğu gibi bir ileti eşlemesi bildirin. Ancak, alt sınıf zaten var olan bir pencere olacak bu yana herhangi bir Windows sınıfını bilgi belirtmeyin unutmayın.

Çağırmak yerine `Create`, çağrı `SubclassWindow` ve alt sınıfı için istediğiniz varolan pencere tanıtıcısı geçirin. Pencerenin alt sınıflanmış sonra kullanacağınız `CWindowImpl::WindowProc` (veya bu metodu geçersiz kılar, işlevinizi) ileti haritasına iletileri yönlendirmek için. Bir alt sınıflanan nesnenizin penceresinden ayırmak için çağrı `UnsubclassWindow`. Pencerenin özgün pencere yordamını sonra yeniden kurulacaktır.

## <a name="see-also"></a>Ayrıca Bkz.

[Pencere Uygulama](../atl/implementing-a-window.md)

