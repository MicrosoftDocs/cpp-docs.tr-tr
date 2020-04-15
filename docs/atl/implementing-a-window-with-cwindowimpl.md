---
title: CWindowImpl ile Pencere Uygulama
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- windows [C++], subclassing
- windows [C++], superclassing
- windows [C++], ATL
- subclassing ATL window classes
- superclassing, ATL
ms.assetid: 3fc40550-f1d6-4702-8b7c-4cf682b6a855
ms.openlocfilehash: e5fdbf15ddd7edc69f0667a9b7e08c7c5e531a5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319458"
---
# <a name="implementing-a-window-with-cwindowimpl"></a>CWindowImpl ile Pencere Uygulama

Bir pencere uygulamak için, bir `CWindowImpl`sınıf türetmek. Türetilen sınıfınızda, bir ileti eşlemi ve ileti işleyicisi işlevlerini bildirin. Artık sınıfınızı üç farklı şekilde kullanabilirsiniz:

- [Yeni bir Windows sınıfına dayalı pencere oluşturma](#_atl_creating_a_window_based_on_a_new_windows_class)

- [Varolan bir Windows sınıfÜst Sınıf](#_atl_superclassing_an_existing_windows_class)

- [Varolan bir pencereyi alt sınıfla](#_atl_subclassing_an_existing_window)

## <a name="creating-a-window-based-on-a-new-windows-class"></a><a name="_atl_creating_a_window_based_on_a_new_windows_class"></a>Yeni Bir Windows Sınıfına Dayalı Pencere Oluşturma

`CWindowImpl`Windows sınıf bilgilerini bildirmek için [DECLARE_WND_CLASS](reference/window-class-macros.md#declare_wnd_class) makroiçerir. Bu makro, `GetWndClassInfo` yeni bir Windows sınıfının bilgilerini tanımlamak için [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) kullanan işlevi uygular. Çağrıldığında, `CWindowImpl::Create` bu Windows sınıfı kaydedilir ve yeni bir pencere oluşturulur.

> [!NOTE]
> `CWindowImpl``DECLARE_WND_CLASS` NULL'u makroya geçirir, bu da ATL'nin bir Windows sınıf adı oluşturacağı anlamına gelir. Kendi adınızı belirtmek için, türemiş `CWindowImpl`sınıfınızda DECLARE_WND_CLASS için bir dize geçirin.

## <a name="example"></a>Örnek

Aşağıda, yeni bir Windows sınıfına dayalı bir pencere uygulayan bir sınıf örneği verilmiştir:

[!code-cpp[NVC_ATL_Windowing#64](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_1.h)]

Bir pencere oluşturmak için, `CMyWindow` bir örnek `Create` oluşturun ve sonra yöntemi arayın.

> [!NOTE]
> Varsayılan Windows sınıfı bilgilerini geçersiz kılmak `GetWndClassInfo` için, üyeleri uygun `CWndClassInfo` değerlere ayarlayarak türetilmiş sınıfınızdaki yöntemi uygulayın.

## <a name="superclassing-an-existing-windows-class"></a><a name="_atl_superclassing_an_existing_windows_class"></a>Varolan Bir Windows Sınıfının Üst Sınıflanması

[DECLARE_WND_SUPERCLASS](reference/window-class-macros.md#declare_wnd_superclass) makrosu, varolan bir Windows sınıfının üst sınıflarını üst sınıflayan bir pencere oluşturmanıza olanak tanır. Bu makroyu `CWindowImpl`türetilmiş sınıfınızda belirtin. Diğer ATL pencerelerinde olduğu gibi, iletiler de bir ileti haritası yla işlenir.

DECLARE_WND_SUPERCLASS kullandığınızda, yeni bir Windows sınıfı kaydedilir. Bu yeni sınıf belirttiğiniz varolan sınıfla aynı olacaktır, ancak `CWindowImpl::WindowProc` pencere yordamını (veya bu yöntemi geçersiz kılan işlevinizle) değiştirir.

## <a name="example"></a>Örnek

Aşağıda, standart Edit sınıfını üst sınıfa alan bir sınıf örneği verilmiştir:

[!code-cpp[NVC_ATL_Windowing#65](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_2.h)]

Üst sınıfed edit penceresi oluşturmak için, `CMyEdit` bir örnek `Create` oluşturun ve sonra yöntemi arayın.

## <a name="subclassing-an-existing-window"></a><a name="_atl_subclassing_an_existing_window"></a>Varolan Pencereyi Alt Sınıflandırma

Varolan bir pencereyi alt sınıfa `CWindowImpl` almak için, önceki iki durumda olduğu gibi bir sınıf türetin ve bir ileti eşlemi bildirin. Ancak, varolan bir pencereyi alt sınıfa çıkaracağınız için windows sınıfı bilgisi belirtmediğinizi unutmayın.

Aramak `Create`yerine, `SubclassWindow` çağırın ve alt sınıflamak istediğiniz varolan pencereye tutamacı geçirin. Pencere alt sınıflandıktan sonra, `CWindowImpl::WindowProc` iletileri ileti eşlemi'ne yönlendirmek için (veya bu yöntemi geçersiz kılan işlevinizi) kullanır. Alt sınıflanmış bir pencereyi nesnenizden ayırmak `UnsubclassWindow`için . Pencerenin özgün pencere yordamı daha sonra geri yüklenir.

## <a name="see-also"></a>Ayrıca bkz.

[Pencere Uygulama](../atl/implementing-a-window.md)
