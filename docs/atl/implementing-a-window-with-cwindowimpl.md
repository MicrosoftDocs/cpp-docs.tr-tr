---
title: CWindowImpl ile pencere uygulama
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- windows [C++], subclassing
- windows [C++], superclassing
- windows [C++], ATL
- subclassing ATL window classes
- superclassing, ATL
ms.assetid: 3fc40550-f1d6-4702-8b7c-4cf682b6a855
ms.openlocfilehash: 7ce1a2ec08e49e047aee5248bda0094d9e392614
ms.sourcegitcommit: ced5ff1431ffbd25b20d106901955532723bd188
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2020
ms.locfileid: "92135521"
---
# <a name="implementing-a-window-with-cwindowimpl"></a>CWindowImpl ile pencere uygulama

Bir pencere uygulamak için, öğesinden bir sınıf türetebilirsiniz `CWindowImpl` . Türetilmiş sınıfınıza bir ileti Haritası ve ileti işleyicisi işlevleri bildirin. Şimdi de sınıfınızı üç farklı şekilde kullanabilirsiniz:

- [Yeni bir Windows sınıfına dayalı bir pencere oluştur](#_atl_creating_a_window_based_on_a_new_windows_class)

- [Varolan bir Windows sınıfının üst sınıfı](#_atl_superclassing_an_existing_windows_class)

- [Varolan bir pencerenin alt sınıfı](#_atl_subclassing_an_existing_window)

## <a name="creating-a-window-based-on-a-new-windows-class"></a><a name="_atl_creating_a_window_based_on_a_new_windows_class"></a> Yeni bir Windows sınıfına dayalı pencere oluşturma

`CWindowImpl` Windows sınıf bilgilerini bildirmek için [DECLARE_WND_CLASS](reference/window-class-macros.md#declare_wnd_class) makrosunu içerir. Bu makro `GetWndClassInfo` , yeni bir Windows sınıfının bilgilerini tanımlamak Için [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) kullanan işlevini uygular. `CWindowImpl::Create`Çağrıldığında, bu Windows sınıfı kaydedilir ve yeni bir pencere oluşturulur.

> [!NOTE]
> `CWindowImpl` Makroya NULL geçirir `DECLARE_WND_CLASS` , bu, ATL 'nin bir Windows sınıf adı üretebileceği anlamına gelir. Kendi adınızı belirtmek için, türetilmiş sınıfınıza bir dize geçirin DECLARE_WND_CLASS `CWindowImpl` .

## <a name="example-implement-a-window"></a>Örnek: pencere uygulama

Aşağıda, yeni bir Windows sınıfına dayalı bir pencere uygulayan bir sınıf örneği verilmiştir:

[!code-cpp[NVC_ATL_Windowing#64](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_1.h)]

Bir pencere oluşturmak için bir örneği oluşturun `CMyWindow` ve sonra `Create` yöntemi çağırın.

> [!NOTE]
> Varsayılan Windows sınıfı bilgilerini geçersiz kılmak için, `GetWndClassInfo` üyeleri uygun değerlere ayarlayarak türetilmiş sınıfınıza yöntemi uygulayın `CWndClassInfo` .

## <a name="superclassing-an-existing-windows-class"></a><a name="_atl_superclassing_an_existing_windows_class"></a> Var olan bir Windows sınıfının üst sınıfı

[Declare_wnd_superclass](reference/window-class-macros.md#declare_wnd_superclass) makrosu, var olan bir Windows sınıfını üst sınıflara uygulayan bir pencere oluşturmanıza olanak sağlar. Bu makroyu `CWindowImpl` türetilmiş sınıfınde belirtin. Diğer tüm ATL pencereleri gibi iletiler de ileti eşlemesi tarafından işlenir.

DECLARE_WND_SUPERCLASS kullandığınızda yeni bir Windows sınıfı kaydedilir. Bu yeni sınıf, belirttiğiniz varolan sınıfla aynı olacaktır, ancak pencere yordamını `CWindowImpl::WindowProc` (veya bu yöntemi geçersiz kılan işleviniz ile) değiştirir.

## <a name="example-superclass-the-edit-class"></a>Örnek: Edit sınıfının üst sınıfı

Aşağıda, standart düzenleme sınıfını üst sınıflara uygulayan bir sınıf örneği verilmiştir:

[!code-cpp[NVC_ATL_Windowing#65](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_2.h)]

Üst sınıf düzenleme penceresini oluşturmak için bir örneği oluşturun `CMyEdit` ve sonra `Create` yöntemi çağırın.

## <a name="subclassing-an-existing-window"></a><a name="_atl_subclassing_an_existing_window"></a> Altsınıflama var olan bir pencere

Varolan bir pencerenin alt sınıfını almak için, ' dan bir sınıf türetebilir `CWindowImpl` ve bir ileti haritası bildirin ve bu iki durumda. Ancak, zaten varolan bir pencerenin alt sınıfını oluşturacak olduğundan, herhangi bir Windows sınıf bilgisi belirtmediğini unutmayın.

Çağırmak yerine `Create` , onu çağırın `SubclassWindow` ve alt sınıflara ayırmak istediğiniz mevcut pencereye geçirin. Pencere alt sınıflandırıldıktan sonra `CWindowImpl::WindowProc` iletileri ileti eşlemesine yönlendirmek için (veya bu yöntemi geçersiz kılan işlevinizi) kullanır. Alt sınıflı bir pencereyi nesnenizin dışında bırakmak için çağırın `UnsubclassWindow` . Pencerenin özgün pencere yordamı geri yüklenecektir.

## <a name="see-also"></a>Ayrıca bkz.

[Pencere uygulama](../atl/implementing-a-window.md)
