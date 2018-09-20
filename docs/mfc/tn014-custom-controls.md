---
title: 'TN014: Özel denetimler | Microsoft Docs'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.controls
dev_langs:
- C++
helpviewer_keywords:
- TN014
- custom controls [MFC]
ms.assetid: 1917a498-f643-457c-b570-9a0af7dbf7bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bacba9ea15598e4c722682a081b64b80db34e00b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430572"
---
# <a name="tn014-custom-controls"></a>TN014: Özel Denetimler

Bu Not, özel ve kendi kendine çizim denetimleri için MFC desteğini açıklar. Ayrıca Dinamik sınıflara açıklar ve arasındaki ilişkiyi açıklar [CWnd](../mfc/reference/cwnd-class.md) nesneleri ve `HWND`s.

MFC örnek uygulamayı CTRLTEST birçok özel denetimler kullanılması gösterilmektedir. MFC genel örnek için kaynak koduna bakın [CTRLTEST](../visual-cpp-samples.md) ve çevrimiçi Yardım.

## <a name="owner-draw-controlsmenus"></a>Özelleştirilmiş Çizimli denetimler/menüleri

Windows Windows iletileri kullanarak özelleştirilmiş çizimli denetimler ve menüler için destek sağlar. Herhangi bir denetim veya menü üst pencere yanıt olarak bu iletiler ve çağırır işlevler alır. Sahip çizim denetimi ya da menü davranışını ve görünümünü özelleştirmek için bu işlevler geçersiz kılabilirsiniz.

MFC, sahip çizim doğrudan destekler aşağıdaki işlevleri ile:

- [CWnd::OnDrawItem](../mfc/reference/cwnd-class.md#ondrawitem)

- [CWnd::OnMeasureItem](../mfc/reference/cwnd-class.md#onmeasureitem)

- [CWnd::OnCompareItem](../mfc/reference/cwnd-class.md#oncompareitem)

- [CWnd::OnDeleteItem](../mfc/reference/cwnd-class.md#ondeleteitem)

Bu işlevleri geçersiz kılma, `CWnd` türetilmiş sınıf özel çizim davranışı uygulamak.

Bu yaklaşım, yeniden kullanılabilir bir kod neden olmaz. İki farklı iki benzer denetimi varsa `CWnd` sınıfları, iki konumda özel denetimi davranışı uygulamalıdır. MFC tarafından desteklenen Self çizim denetimi mimarisi bu sorunu çözer.

## <a name="self-draw-controls-and-menus"></a>Denetimleri ve menüler Self çizme

MFC varsayılan uygulamasını sağlar (içinde `CWnd` ve [CMenu](../mfc/reference/cmenu-class.md) sınıflar) için standart özelleştirilmiş çizimli iletileri. Bu varsayılan uygulama, sahip çizim parametrelerini'kodunu çözme ve denetimleri veya menüye sahip çizim iletileri temsilci. Çizim kodu denetimi ya da menü, sahibi penceresinde sınıfına olduğundan bu kendi kendine çizmek çağrılır.

Kendi kendine çizmek denetimlerini kullanarak denetim görüntülemek için özelleştirilmiş çizimli semantiklerini kullanan yeniden kullanılabilir denetim sınıfları oluşturabilirsiniz. Bir denetim çizmek için denetim sınıfı, kendi üst kodudur. Özel denetim programlama nesne odaklı bir yaklaşım budur. Aşağıdaki listede yer alan İşlevler, kendi kendine çizmek sınıflarınızı ekleyin:

- Düğmeler Self çizmek için:

    ```cpp
    CButton:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw this button
    ```

- Menüler Self çizmek için:

    ```cpp
    CMenu:MeasureItem(LPMEASUREITEMSTRUCT);
    // insert code to measure the size of an item in this menu
    CMenu:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw an item in this menu
    ```

- Kendi kendine çizim liste kutuları için:

    ```cpp
    CListBox:MeasureItem(LPMEASUREITEMSTRUCT);
    // insert code to measure the size of an item in this list box
    CListBox:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw an item in this list box

    CListBox:CompareItem(LPCOMPAREITEMSTRUCT);
    // insert code to compare two items in this list box if LBS_SORT
    CListBox:DeleteItem(LPDELETEITEMSTRUCT);
    // insert code to delete an item from this list box
    ```

- Kendi kendine çizmek birleşik giriş kutuları için:

    ```cpp
    CComboBox:MeasureItem(LPMEASUREITEMSTRUCT);
    // insert code to measure the size of an item in this combo box
    CComboBox:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw an item in this combo box

    CComboBox:CompareItem(LPCOMPAREITEMSTRUCT);
    // insert code to compare two items in this combo box if CBS_SORT
    CComboBox:DeleteItem(LPDELETEITEMSTRUCT);
    // insert code to delete an item from this combo box
    ```

Sahip çizim yapıları hakkında ayrıntılı bilgi için ([DRAWITEMSTRUCT](../mfc/reference/drawitemstruct-structure.md), [MEASUREITEMSTRUCT](../mfc/reference/measureitemstruct-structure.md), [COMPAREITEMSTRUCT](../mfc/reference/compareitemstruct-structure.md), ve [DELETEITEMSTRUCT](../mfc/reference/deleteitemstruct-structure.md)) MFC belgelerine bakın `CWnd::OnDrawItem`, `CWnd::OnMeasureItem`, `CWnd::OnCompareItem`, ve `CWnd::OnDeleteItem` sırasıyla.

## <a name="using-self-draw-controls-and-menus"></a>Kendi kendine çizmek denetimlerini ve menüler kullanma

İçin kendi kendine çizmek menüler, her ikisi de tanımlamalısınız `OnMeasureItem` ve `OnDrawItem` yöntemleri.

Kendi kendine çizim liste kutuları ve birleşik giriş kutuları için geçersiz kılmanız gerekir `OnMeasureItem` ve `OnDrawItem`. Lbs_ownerdrawvarıable stili için liste kutuları veya birleşik giriş kutuları için cbs_ownerdrawvarıable style iletişim şablonda belirtmeniz gerekir. Sabit öğe yüksekliğini Self çizmek denetimleri liste kutusuna eklenen önce belirlediğinden OWNERDRAWFIXED stili Self çizmek öğeleriyle çalışmaz. (Yöntemlerini kullanabilirsiniz [CListBox::SetItemHeight](../mfc/reference/clistbox-class.md#setitemheight) ve [CComboBox::SetItemHeight](../mfc/reference/ccombobox-class.md#setitemheight) bu sınırlamanın üstesinden gelmek için.)

Bir OWNERDRAWVARIABLE stilini değiştirme NOINTEGRALHEIGHT stili denetime uygulamak için sistem zorlar. Denetimin değişken boyutlu öğeleri içeren bir tamsayı yükseklik hesaplanamıyor çünkü INTEGRALHEIGHT varsayılan stilini göz ardı edilir ve her zaman NOINTEGRALHEIGHT denetimidir. Öğelerinizi yükseklik sabitse, bir tamsayı çarpan öğe boyutunun denetimin boyutunu belirterek çizilen gelen kısmi öğe engelleyebilirsiniz.

Liste kutuları ve birleşik giriş kutuları LBS_SORT veya CBS_SORT stiliyle Self çizim için geçersiz kılmanız gerekir `OnCompareItem` yöntemi.

Liste kutuları ve birleşik giriş kutuları, kendi kendine çizmek için `OnDeleteItem` genellikle geçersiz. Geçersiz kılabilirsiniz `OnDeleteItem` herhangi bir özel işlem gerçekleştirmek istiyorsanız. Ek bellek veya diğer kaynaklara her liste kutusu veya birleşik giriş kutusu öğesi ile depolandığında ise bunun geçerli olacağı bir durumdur.

## <a name="examples-of-self-drawing-controls-and-menus"></a>Kendi kendine çizim denetimleri ve menüler örnekleri

MFC genel örnek [CTRLTEST](../visual-cpp-samples.md) bir kendi kendine çizim menüsü ve kendi kendine çizim liste kutusu örnekleri sağlar.

En sık karşılaşılan bir kendi kendine çizim düğmesini bir bit eşlem düğmesi örneğidir. Bir bit eşlem düğmesi, bir, iki veya üç farklı durumlar için bit eşlem resimleri gösteren bir düğme vardır. Buna örnek olarak, MFC sınıfı sağlanan [CBitmapButton](../mfc/reference/cbitmapbutton-class.md).

## <a name="dynamic-subclassing"></a>Dinamik sınıflara

Bazen, zaten var olan bir nesne işlevlerini değiştirmek isteyebilirsiniz. Önceki örneklerde, oluşturuldukları önce denetimleri özelleştirmek gereklidir. Dinamik sınıflara zaten oluşturulmuş bir denetimi özelleştirmenize olanak sağlar.

Sınıflara olan değiştirmek için Windows terimi <xref:System.Windows.Forms.Control.WndProc%2A> özelleştirilmiş pencerenin `WndProc` ve eski çağırma `WndProc` varsayılan işlevler için.

Bu C++ sınıf türetme ile karıştırılmamalıdır. Açıklama, C++ koşulları için *temel sınıfı* ve *türetilmiş sınıf* için benzer *sınıfın* ve *alt* Windows içinde nesne modeli. MFC ve Windows sınıflara sahip C++ türetme işlevsel olarak benzer dışında C++ dinamik sınıflara desteklemez.

`CWnd` Sınıfı, bir C++ nesnesi arasında bağlantı sağlar (türetilen `CWnd`) ve Windows pencere nesnesi (olarak bilinen bir `HWND`).

Bu ilgili üç yaygın yol vardır:

- `CWnd` oluşturur `HWND`. Türetilen bir sınıf oluşturarak türetilmiş bir sınıf içinde davranışını değiştirebilirsiniz `CWnd`. `HWND` Uygulamanız çağırdığında oluşturulan [CWnd::Create](../mfc/reference/cwnd-class.md#create).

- Uygulama ekler bir `CWnd` varolan `HWND`. Var olan pencereyi davranışı değiştirilmez. Bu temsilci bir durumunun ve çağrılarak gerçekleştirilir [CWnd::Attach](../mfc/reference/cwnd-class.md#attach) diğer adı varolan `HWND` için bir `CWnd` nesne.

- `CWnd` Mevcut bir bağlı `HWND` ve türetilen bir sınıfta davranışını değiştirebilirsiniz. Bu, çünkü biz davranışı ve bu nedenle, çalışma zamanında bir Windows nesnenin sınıfını değiştirme sınıflara dinamik çağrılır.

Yöntemleri kullanarak dinamik sınıflara elde edebileceğiniz [CWnd::SubclassWindow](../mfc/reference/cwnd-class.md#subclasswindow) ve[CWnd::SubclassDlgItem](../mfc/reference/cwnd-class.md#subclassdlgitem).

Her iki yordam ekleme bir `CWnd` varolan nesne `HWND`. `SubclassWindow` alan `HWND` doğrudan. `SubclassDlgItem` Denetim kimliği ve ana pencereyi bir yardımcı işlevdir. `SubclassDlgItem` bir iletişim kutusu şablondan oluşturulan iletişim kutusu denetimleri için C++ nesneleri eklemek için tasarlanmıştır.

Bkz: [CTRLTEST](../visual-cpp-samples.md) ne zaman kullanılacağı çeşitli örneklerini örneğin `SubclassWindow` ve `SubclassDlgItem`.

## <a name="see-also"></a>Ayrıca Bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
