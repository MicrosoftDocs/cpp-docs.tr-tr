---
title: 'TN014: Özel denetimler | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 54a7ef7f6fd9a9da92c208366ee401d55d07fd5a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384588"
---
# <a name="tn014-custom-controls"></a>TN014: Özel Denetimler
Bu Not özel ve kendi kendine çizim denetimleri için MFC desteği açıklar. Bu ayrıca dinamik sınıflara ve arasındaki ilişkiyi açıklar [CWnd](../mfc/reference/cwnd-class.md) nesneleri ve `HWND`s.  
  
 MFC örnek uygulama CTRLTEST birçok özel denetimlerinin nasıl kullanıldığını gösterir. MFC genel örnek için kaynak koduna bakın [CTRLTEST](../visual-cpp-samples.md) ve çevrimiçi Yardım.  
  
## <a name="owner-draw-controlsmenus"></a>Sahip çizim denetimleri/menüleri  
 Windows Windows iletileri kullanarak sahip çizim denetimleri ve menüleri için destek sağlar. Herhangi bir denetim veya menü üst pencere bu iletileri ve çağrıları işlevler yanıt olarak alır. Bu işlevler görsel görünümünü ve davranışını sahip çizim denetim veya menü özelleştirmek için geçersiz kılabilirsiniz.  
  
 MFC doğrudan sahip çizim destekleyen aşağıdaki işlevleri ile:  
  
- [CWnd::OnDrawItem](../mfc/reference/cwnd-class.md#ondrawitem)  
  
- [CWnd::OnMeasureItem](../mfc/reference/cwnd-class.md#onmeasureitem)  
  
- [CWnd::OnCompareItem](../mfc/reference/cwnd-class.md#oncompareitem)  
  
- [CWnd::OnDeleteItem](../mfc/reference/cwnd-class.md#ondeleteitem)  
  
 Bu işlevler kılabilirsiniz, `CWnd` türetilmiş özel çizim davranışı uygulamak için sınıf.  
  
 Bu yaklaşım, yeniden kullanılabilir koduna neden olmaz. İki benzer denetimleri farklı iki varsa `CWnd` sınıfları, iki konumda özel denetim davranışı uygulamalıdır. Kendi kendine çizim denetim MFC desteklenen mimarisi, bu sorunu çözer.  
  
## <a name="self-draw-controls-and-menus"></a>Denetimleri ve menüleri kendiliğinden çizme  
 MFC varsayılan uygulamasını sağlar (içinde `CWnd` ve [CMenu](../mfc/reference/cmenu-class.md) sınıfları) standart sahibi tarafından çizilen iletileri için. Bu varsayılan uygulama sahibi çizim parametreleri kod çözme ve denetimleri veya menü sahip çizim iletileri atayabilirsiniz. Çizim kodunu denetim veya sahibi penceresinde menü sınıfının olduğundan bu kendi kendine çizin çağrılır.  
  
 Kendi kendine çizin denetimlerini kullanarak denetim görüntülenecek sahip çizim semantiğini kullanmasına yeniden kullanılabilir denetim sınıfları oluşturabilirsiniz. Denetim çizim için denetim sınıfı, kendi üst kodudur. Özel denetim programlama nesne yönelimli bir yaklaşım budur. Aşağıdaki işlevlerin listesi, kendi kendine çizin sınıflarınızı ekleyin:  
  
-   Kendi kendine çizin düğmeleri için:  
  
 ```  
    CButton:DrawItem(LPDRAWITEMSTRUCT);
*// insert code to draw this button  
 ```  
  
-   Menüler Self çizmek için:  
  
 ```  
    CMenu:MeasureItem(LPMEASUREITEMSTRUCT);
*// insert code to measure the size of an item in this menu  
    CMenu:DrawItem(LPDRAWITEMSTRUCT);
*// insert code to draw an item in this menu  
 ```  
  
-   Kendi kendine çizin liste kutuları için:  
  
 ```  
    CListBox:MeasureItem(LPMEASUREITEMSTRUCT);
*// insert code to measure the size of an item in this list box  
    CListBox:DrawItem(LPDRAWITEMSTRUCT);
*// insert code to draw an item in this list box  
 
    CListBox:CompareItem(LPCOMPAREITEMSTRUCT);
*// insert code to compare two items in this list box if LBS_SORT  
    CListBox:DeleteItem(LPDELETEITEMSTRUCT);
*// insert code to delete an item from this list box  
 ```  
  
-   Kendi kendine çizin birleşik giriş kutuları için:  
  
 ```  
    CComboBox:MeasureItem(LPMEASUREITEMSTRUCT);
*// insert code to measure the size of an item in this combo box  
    CComboBox:DrawItem(LPDRAWITEMSTRUCT);
*// insert code to draw an item in this combo box  
 
    CComboBox:CompareItem(LPCOMPAREITEMSTRUCT);
*// insert code to compare two items in this combo box if CBS_SORT  
    CComboBox:DeleteItem(LPDELETEITEMSTRUCT);
*// insert code to delete an item from this combo box  
 ```  
  
 Sahip çizim yapılar hakkında ayrıntılı bilgi için ([DRAWITEMSTRUCT](../mfc/reference/drawitemstruct-structure.md), [MEASUREITEMSTRUCT](../mfc/reference/measureitemstruct-structure.md), [COMPAREITEMSTRUCT](../mfc/reference/compareitemstruct-structure.md), ve [DELETEITEMSTRUCT](../mfc/reference/deleteitemstruct-structure.md)) MFC belgelerine bakın `CWnd::OnDrawItem`, `CWnd::OnMeasureItem`, `CWnd::OnCompareItem`, ve `CWnd::OnDeleteItem` sırasıyla.  
  
## <a name="using-self-draw-controls-and-menus"></a>Kendi kendine çizin denetimleri ve menülerini kullanarak  
 Kendi kendine çizin menülerden, her ikisi de kılmalı `OnMeasureItem` ve `OnDrawItem` yöntemleri.  
  
 Kendi kendine çizin liste kutuları ve birleşik giriş kutuları için geçersiz kılmanız gerekir `OnMeasureItem` ve `OnDrawItem`. Belirtmeniz gerekir `LBS_OWNERDRAWVARIABLE` liste kutuları için stil veya `CBS_OWNERDRAWVARIABLE` stili için birleşik giriş kutuları iletişim şablonunda. `OWNERDRAWFIXED` Stili denetimleri Self çizmek için liste kutusu bağlı önce sabit öğe yüksekliği belirlediğinden Self çizin öğeleri ile çalışmaz. (Yöntemlerini kullanabilirsiniz [CListBox::SetItemHeight](../mfc/reference/clistbox-class.md#setitemheight) ve [CComboBox::SetItemHeight](../mfc/reference/ccombobox-class.md#setitemheight) bu sınırlamanın üstesinden gelmek için.)  
  
 Geçiş bir `OWNERDRAWVARIABLE` stili uygulanması için sistemi zorlayacak `NOINTEGRALHEIGHT` denetimine stili. Denetim sahip değişken boyutlu bir tam sayı yükseklik hesaplayamıyor çünkü öğelerini, varsayılan stilini `INTEGRALHEIGHT` göz ardı edilir ve her zaman denetimidir `NOINTEGRALHEIGHT`. Öğelerinizi yükseklik sabitse, bir tamsayı çarpanı öğesi boyutunun denetim boyutunu belirterek çizilen gelen kısmi öğeler engelleyebilir.  
  
 Kendi kendine çizim liste kutuları veya birleşik giriş kutuları ile için `LBS_SORT` veya `CBS_SORT` stili kılmanız gerekir `OnCompareItem` yöntemi.  
  
 Kendi kendine çizim liste kutuları veya birleşik giriş kutuları için `OnDeleteItem` genellikle geçersiz. Geçersiz kılabilirsiniz `OnDeleteItem` herhangi bir özel işlem gerçekleştirmek istiyorsanız. Ek bellek veya diğer kaynaklara her liste kutusu veya birleşik giriş kutusu öğesi ile depolandığında bunun geçerli olduğu bir durumdur.  
  
## <a name="examples-of-self-drawing-controls-and-menus"></a>Kendi kendine çizim denetimleri ve menüleri örnekleri  
 MFC genel örnek [CTRLTEST](../visual-cpp-samples.md) bir kendi kendine Çiz menüsünde ve kendi kendine çizin liste kutusu örnekleri sağlar.  
  
 Bir kendi kendine çizim düğmesini en tipik örneği bir bit eşlem düğme vardır. Bir bit eşlem düğmesi bir, iki veya üç bitmap görüntüler için farklı durumları gösteren bir düğme vardır. Buna örnek olarak MFC sınıf içinde sağlanan [CBitmapButton](../mfc/reference/cbitmapbutton-class.md).  
  
## <a name="dynamic-subclassing"></a>Dinamik sınıflara  
 Bazen zaten bir nesne işlevlerini değiştirmek isteyeceksiniz. Önceki örneklerde, oluşturuldukları önce denetimleri özelleştirmek gereklidir. Dinamik sınıflara zaten oluşturulmuş bir denetim özelleştirmenize olanak tanır.  
  
 Sınıflara olduğu değiştirmek için Windows terim [WndProc](http://msdn.microsoft.com/en-us/94ba8ffa-3c36-46d4-ac74-9bd10b1ffd26) özelleştirilmiş pencerenin `WndProc` ve eski çağırma `WndProc` varsayılan işlevsellik için.  
  
 Bu C++ sınıf türetme ile karıştırılmamalıdır. Açıklama, C++ koşulları için *temel sınıfı* ve *türetilmiş sınıf* için benzer *sınıfın* ve *alt* Windows nesne modeli. MFC ve Windows sınıflara sahip C++ türetme işlevsel olarak benzer C++ dinamik sınıflara desteklemiyor dışında.  
  
 `CWnd` Sınıfı bir C++ nesnesi arasında bağlantı sağlar (türetilmiş `CWnd`) ve bir Windows pencere nesnesi (olarak bilinen bir `HWND`).  
  
 Bu ilgili yaygın üç yolu vardır:  
  
- `CWnd` oluşturur `HWND`. Türetilmiş bir sınıf oluşturarak türetilmiş bir sınıf davranışı değiştirebilirsiniz `CWnd`. `HWND` Uygulamanız çağırdığında oluşturulan [CWnd::Create](../mfc/reference/cwnd-class.md#create).  
  
-   Uygulama ekler bir `CWnd` varolan bir `HWND`. Varolan pencere davranışını değiştirilmez. Bu temsilci bir durumdur ve çağırarak mümkün hale getirilir [CWnd::Attach](../mfc/reference/cwnd-class.md#attach) diğer adı varolan bir `HWND` için bir `CWnd` nesnesi.  
  
- `CWnd` Mevcut bir bağlı `HWND` ve türetilmiş bir sınıf davranışı değiştirebilirsiniz. Bu, biz davranışını ve bu nedenle, bir Windows nesne sınıfının çalışma zamanında değiştirme çünkü sınıflara dinamik çağrılır.  
  
 Yöntemleri kullanarak dinamik sınıflara elde edebilirsiniz [CWnd::SubclassWindow](../mfc/reference/cwnd-class.md#subclasswindow) ve[CWnd::SubclassDlgItem](../mfc/reference/cwnd-class.md#subclassdlgitem).  
  
 Her iki yordamları attach bir `CWnd` varolan bir nesne `HWND`. `SubclassWindow` alan `HWND` doğrudan. `SubclassDlgItem` Denetim kimliği ve ana pencereyi götüren bir yardımcı işlevdir. `SubclassDlgItem` iletişim kutusu şablondan oluşturulan iletişim kutusu denetimleri için C++ nesneleri eklemek için tasarlanmıştır.  
  
 Bkz: [CTRLTEST](../visual-cpp-samples.md) ne zaman kullanılacağı bazı örnekleri için örnek `SubclassWindow` ve `SubclassDlgItem`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

