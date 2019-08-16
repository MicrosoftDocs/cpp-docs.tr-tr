---
title: 'TN014: Özel denetimler'
ms.date: 06/28/2018
f1_keywords:
- vc.controls
helpviewer_keywords:
- TN014
- custom controls [MFC]
ms.assetid: 1917a498-f643-457c-b570-9a0af7dbf7bb
ms.openlocfilehash: 2960c5b8585519adb535e5611315ec4ececcf53e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511190"
---
# <a name="tn014-custom-controls"></a>TN014: Özel denetimler

Bu notta, özel ve kendi kendine çizim denetimleri için MFC desteği açıklanmaktadır. Ayrıca, dinamik altsınıflama açıklar ve [CWnd](../mfc/reference/cwnd-class.md) nesneleri ile `HWND`s arasındaki ilişkiyi açıklar.

MFC örnek uygulaması CTRLTEST birçok özel denetimi nasıl kullanacağınızı gösterir. MFC genel örnek [ctrltest](../overview/visual-cpp-samples.md) ve çevrimiçi yardım için kaynak koda bakın.

## <a name="owner-draw-controlsmenus"></a>Sahip-çizim denetimleri/menüler

Windows, Windows iletilerini kullanarak sahip çizim denetimleri ve menüleri için destek sağlar. Herhangi bir denetimin veya menünün üst penceresi bu iletileri alır ve yanıt olarak işlevleri çağırır. Sahip çizim denetiminizin veya menüsünün görsel görünümünü ve davranışını özelleştirmek için bu işlevleri geçersiz kılabilirsiniz.

MFC, aşağıdaki işlevlerle doğrudan sahip çizmeyi destekler:

- [CWnd:: OnDrawItem](../mfc/reference/cwnd-class.md#ondrawitem)

- [CWnd:: OnMeasureItem](../mfc/reference/cwnd-class.md#onmeasureitem)

- [CWnd:: OnCompareItem](../mfc/reference/cwnd-class.md#oncompareitem)

- [CWnd:: OnDeleteItem](../mfc/reference/cwnd-class.md#ondeleteitem)

Özel çizim davranışı uygulamak için, türetilmiş `CWnd` sınıfınıza bu işlevleri geçersiz kılabilirsiniz.

Bu yaklaşım, yeniden kullanılabilir koda neden olmaz. İki farklı `CWnd` sınıfta iki benzer denetiminiz varsa, özel denetim davranışını iki konumda uygulamanız gerekir. MFC tarafından desteklenen kendi kendine çizim denetim mimarisi bu sorunu çözer.

## <a name="self-draw-controls-and-menus"></a>Kendi kendine çizim denetimleri ve Menüleri

MFC, standart sahip çizim iletileri için varsayılan `CWnd` bir uygulama (ve [CMenu](../mfc/reference/cmenu-class.md) sınıflarında) sağlar. Bu varsayılan uygulama, sahip çizim parametrelerinin kodunu çözer ve denetim ya da menüye sahip çizim iletilerini devredebilir. Bu, çizim kodu sahip penceresinde değil denetimin veya menünün sınıfında olduğundan, kendi kendine çizim olarak adlandırılır.

Kendi kendine çizim denetimlerini kullanarak, denetimi göstermek için Owner çizim semantiğini kullanan yeniden kullanılabilir denetim sınıfları oluşturabilirsiniz. Denetimi çizme kodu, üst öğesinin değil Denetim sınıfıdır. Bu, özel denetim programlamaya nesne odaklı bir yaklaşımdır. Aşağıdaki işlev listesini kendi çizim sınıflarınıza ekleyin:

- Otomatik çizim düğmeleri için:

    ```cpp
    CButton:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw this button
    ```

- Otomatik çizim menüleri için:

    ```cpp
    CMenu:MeasureItem(LPMEASUREITEMSTRUCT);
    // insert code to measure the size of an item in this menu
    CMenu:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw an item in this menu
    ```

- Kendinden çizimli liste kutuları için:

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

- Kendinden çizimli Birleşik giriş kutuları için:

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

Sahip çizimi yapıları ([drawitemstruct](/windows/win32/api/winuser/ns-winuser-drawitemstruct), [MEASUREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-measureitemstruct), [COMPAREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-compareitemstruct)ve [DELETEITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-deleteitemstruct) `CWnd::OnDrawItem` `CWnd::OnMeasureItem`) hakkındaki ayrıntılar için `CWnd::OnCompareItem`bkz.,, ve içinMFCbelgeleri`CWnd::OnDeleteItem` sırasıyla.

## <a name="using-self-draw-controls-and-menus"></a>Otomatik çizim denetimlerini ve menülerini kullanma

Kendi kendine çizim menüleri için hem hem de `OnMeasureItem` `OnDrawItem` yöntemlerini geçersiz kılmanız gerekir.

Kendinden çizimli liste kutuları ve Birleşik giriş kutuları için, ve `OnMeasureItem` `OnDrawItem`geçersiz kılmanız gerekir. İletişim şablonundaki Birleşik giriş kutuları için liste kutuları veya CBS_OWNERDRAWVARIABLE stili için LBS_OWNERDRAWVARIABLE stilini belirtmeniz gerekir. Sabit öğe yüksekliği, otomatik çizim denetimleri liste kutusuna iliştirilmeden önce belirlendiği için, Owner DRAWFIXED stili, otomatik çizim öğeleri ile çalışmaz. (Bu kısıtlamayı aşmak için [CListBox:: SetItemHeight](../mfc/reference/clistbox-class.md#setitemheight) ve [CComboBox:: SetItemHeight](../mfc/reference/ccombobox-class.md#setitemheight) yöntemlerini kullanabilirsiniz.)

Bir OWNERDRAWVARIABLE stiline geçiş yapmak, sistemin denetime NOINTEGRALHEIGHT stilini uygulamasını zorlayacaktır. Denetim, değişken boyutlu öğelerle tamsayı yüksekliğini hesaplayamadığından, INTEGRALHEIGHT öğesinin varsayılan stili yok sayılır ve denetim her zaman NOINTEGRALHEIGHT olur. Öğeleriniz sabit boyarsa, denetim boyutunu öğe boyutunun tamsayı çarpanı olacak şekilde belirterek kısmi öğelerin çizilmesini engelleyebilirsiniz.

Lbs_sort veya cbs_sort stilinde kendi kendine çizim liste kutuları ve Birleşik giriş kutuları için, `OnCompareItem` yöntemini geçersiz kılmanız gerekir.

Kendi kendine çizim liste kutuları ve Birleşik giriş kutuları `OnDeleteItem` için genellikle geçersiz kılınmaz. Özel bir işlem `OnDeleteItem` gerçekleştirmek istiyorsanız, geçersiz kılabilirsiniz. Bunun geçerli olacağı bir durum, her liste kutusu veya Birleşik giriş kutusu öğesiyle ek bellek veya diğer kaynakların depolandığı durumdur.

## <a name="examples-of-self-drawing-controls-and-menus"></a>Kendi kendine çizim denetimleri ve menülerinin örnekleri

MFC genel örneği [ctrltest](../overview/visual-cpp-samples.md) , bir otomatik çizim menüsü ve kendi kendine çizim listesi kutusu örnekleri sunar.

Bir kendinden çizim düğmesinin en yaygın örneği bir bit eşlem düğmesidir. Bit eşlem düğmesi, farklı durumlar için bir, iki veya üç bit eşlem resmini gösteren bir düğmedir. Bu örnek, [CBitmapButton](../mfc/reference/cbitmapbutton-class.md)mfc sınıfında verilmiştir.

## <a name="dynamic-subclassing"></a>Dinamik Altsınıflama

Bazen zaten var olan bir nesnenin işlevlerini değiştirmek isteyeceksiniz. Önceki örneklerde, denetimleri oluşturulmadan önce özelleştirmeniz gerekir. Dinamik altsınıflama, zaten oluşturulmuş bir denetimi özelleştirmenize olanak sağlar.

Altsınıflama, bir pencerenin özelleştirilmiş <xref:System.Windows.Forms.Control.WndProc%2A> `WndProc` bir pencere ile değiştirilmesi ve varsayılan olarak eski `WndProc` işlevleri çağırmak için Windows terimidir.

Bu, C++ sınıf türetmede karıştırılmamalıdır. C++ Açıklama için, *temel sınıf* ve *türetilmiş sınıf* terimleri Windows nesne modelindeki *üst* sınıfa ve *alt* sınıfa benzerdir. C++MFC ve Windows altsınıflama ile türetme işlevsel olarak benzerdir, ancak C++ dinamik altsınıflama desteklemez.

Sınıfı bir C++ nesne (öğesinden `CWnd`türetilmiş) ve bir Windows pencere nesnesi (bir `HWND`olarak bilinir) arasındaki bağlantıyı sağlar. `CWnd`

Bunların birbirleriyle ilgili üç yaygın yöntemi vardır:

- `CWnd`öğesini oluşturur `HWND`. Öğesinden `CWnd`türetilmiş bir sınıf oluşturarak türetilmiş bir sınıftaki davranışı değiştirebilirsiniz. , `HWND` Uygulamanız [CWnd:: Create](../mfc/reference/cwnd-class.md#create)yöntemini çağırdığında oluşturulur.

- Uygulama, var olan `CWnd` `HWND`bir öğesine iliştirir. Mevcut pencerenin davranışı değiştirilmez. Bu bir temsilcilidir ve [CWnd:: Attach](../mfc/reference/cwnd-class.md#attach) ' i çağırarak bir `HWND` `CWnd` nesne için var olan diğer ada ekleyin.

- `CWnd`Mevcut `HWND` bir öğesine iliştirilir ve türetilmiş bir sınıftaki davranışı değiştirebilirsiniz. Bu, çalışma zamanında bir Windows nesnesinin davranışını ve bu nedenle sınıfını değiştirdiğimiz için dinamik altsınıflama olarak adlandırılır.

[CWnd:: SubclassWindow](../mfc/reference/cwnd-class.md#subclasswindow) ve[CWnd:: SubclassDlgItem](../mfc/reference/cwnd-class.md#subclassdlgitem)yöntemlerini kullanarak dinamik altsınıflama elde edebilirsiniz.

Her iki yordam de `CWnd` varolan `HWND`bir nesne ekler. `SubclassWindow``HWND` doğrudan alır. `SubclassDlgItem`, bir denetim KIMLIĞI ve üst pencereyi alan bir yardımcı işlevdir. `SubclassDlgItem`iletişim kutusu şablonundan oluşturulan C++ iletişim kutusu denetimlerine nesne iliştirmek için tasarlanmıştır.

Ve ' [](../overview/visual-cpp-samples.md) `SubclassWindow` ninnezamankullanılacağıhakkındadahafazlaörnekiçinctrltestörneğine`SubclassDlgItem`bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
