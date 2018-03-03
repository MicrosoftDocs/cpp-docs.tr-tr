---
title: Liste kutusu stilleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LBS_STANDARD
- LBS_NODATA
- LBS_OWNERDRAWVARIABLE
- LBS_EXTENDEDSEL
- LBS_USETABSTOPS
- LBS_WANTKEYBOARDINPUT
- LBS_NOTIFY
- LBS_DISABLENOSCROLL
- LBS_HASSTRINGS
- LBS_NOREDRAW
- LBS_NOSEL
- LBS_NOINTEGRALHEIGHT
- LBS_MULTICOLUMN
- LBS_SORT
- LBS_MULTIPLESEL
- LBS_OWNERDRAWFIXED
dev_langs:
- C++
helpviewer_keywords:
- LBS_NOSEL constant [MFC]
- LBS_NOREDRAW constant [MFC]
- LBS_HASSTRINGS constant [MFC]
- LBS_OWNERDRAWFIXED constant [MFC]
- LBS_WANTKEYBOARDINPUT constant [MFC]
- LBS_STANDARD constant [MFC]
- LBS_MULTIPLESEL constant [MFC]
- LBS_OWNERDRAWVARIABLE constant [MFC]
- LBS_DISABLENOSCROLL constant [MFC]
- LBS_NODATA constant [MFC]
- list boxes [MFC], styles
- LBS_EXTENDEDSEL constant [MFC]
- LBS_MULTICOLUMN constant [MFC]
- LBS_NOTIFY constant [MFC]
- LBS_USETABSTOPS constant [MFC]
- LBS_NOINTEGRALHEIGHT constant [MFC]
- LBS_SORT constant
ms.assetid: 3f357b8d-9118-4f41-9e28-02ed92d1e88f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8f52734e26d1965811aded67bc1e1dde6a2c28bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="list-box-styles"></a>Liste Kutusu Stilleri
-   **Lbs_dısablenoscroll** zaman liste kutusunda kaydırma için yeterli öğeleri içermiyor çubuğu devre dışı bırakılmış bir dikey kaydırma liste kutusu gösterir. Liste kutusu yeterli öğeleri içermediğinde, bu stili kaydırma çubuğu gizlenir.  
  
-   **LBS_EXTENDEDSEL** kullanıcı SHIFT tuşunu ve fare veya özel tuş birleşimlerini kullanarak birden çok öğe seçebilirsiniz.  
  
-   **Lbs_hasstrıngs** dizeleri oluşan öğelerini içeren bir sahibi tarafından çizilen liste kutusu belirtir. Uygulamayı kullanabilmeniz için bellek ve dizeleri işaretçileri liste kutusu tutar `GetText` belirli bir öğenin metni almak için üye işlevi.  
  
-   **Lbs_multıcolumn** yatay kaydırılan bir sütunlu liste kutusu belirtir. `SetColumnWidth` Üye işlevi sütunların genişliğini ayarlar.  
  
-   **Lbs_multıplesel** dize seçimi kullanıcı tıklattığında veya dize çift tıklamalar her zaman yükseğe. Dizeleri herhangi bir sayıda seçilebilir.  
  
-   **LBS_NODATA** veri yok liste kutusu belirtir. Liste kutusunda öğelerin sayısını bin aşacak olduğunda bu stilini belirtin. Veri yok liste kutusu ayrıca olmalıdır **lbs_ownerdrawfıxed** stil ancak değil olmalıdır **LBS_SORT** veya **lbs_hasstrıngs** stili.  
  
     Veri yok liste kutusu sahip tarafından çizilmiş liste kutusu benzer bir öğe için hiçbir dize veya bit eşlem verileri içerir. Komutları eklemek için Ekle ya da bir öğeyi silmek öğesi belirtilen veri; her zaman yoksay Liste kutusu içinde her zaman bir dizeyi bulmak için istekleri başarısız olur. Sistem gönderir `WM_DRAWITEM` ileti bir öğe çizilmesi gerektiğinde sahibi penceresine. Öğe kimliği üyesi `DRAWITEMSTRUCT` yapısı geçirilen ile `WM_DRAWITEM` ileti çizilecek öğesi satır sayısını belirtir. Veri yok liste kutusu göndermemek bir `WM_DELETEITEM` ileti.  
  
-   **Lbs_noıntegralheıght** boyutu liste kutusunun liste kutusu oluşturduğunuzda uygulama tarafından belirtilen tam olarak eşittir. Genellikle, böylece liste kutusu kısmi öğeleri görüntülemez Windows bir liste kutusu boyutları.  
  
-   **LBS_NOREDRAW** liste kutusu görüntü değişiklik yapıldığında güncelleştirilmez. Bu stili göndererek herhangi bir zamanda değiştirilebilir bir **WM_SETREDRAW** ileti.  
  
-   **LBS_NOSEL** liste kutusu görüntülenebilir ancak seçili öğeleri içerdiğini belirtir.  
  
-   **Lbs_notıfy** üst pencere kullanıcı tıklattığında veya bir dize çift tıklamalar her bir giriş iletisi alır.  
  
-   **Lbs_ownerdrawfıxed** liste kutusu sahibi içeriğini çizmek için sorumlu; liste kutusunda öğeleri aynı yüksekliği olur.  
  
-   **Lbs_ownerdrawvarıable** liste kutusu sahibi içeriğini çizmek için sorumlu; liste kutusunda öğeleri yükseklik değişkeninde olur.  
  
-   **LBS_SORT** liste kutusunda dizeleri alfabetik olarak sıralanır.  
  
-   **LBS_STANDARD** liste kutusunda dizeleri alfabetik olarak sıralanır ve her kullanıcının tıklattığında veya bir dize çift tıklamalar üst pencere bir giriş iletisi alır. Liste kutusu tüm yüze Kenarlıklar içerir.  
  
-   **LBS_USETABSTOPS** algılar ve kendi dizeleri çizerken sekme karakterleri genişletmek bir liste kutusu sağlar. Varsayılan sekme konumlar 32 iletişim birimleridir. (Bir iletişim yatay ve dikey uzaklık birimdir. Bir yatay iletişim biriminin geçerli iletişim temel genişliği biriminin bir-dördüncü için eşittir. İletişim kutusu temel birimleri geçerli sistem yazı tipi genişliği ve yüksekliği göre hesaplanır. **GetDialogBaseUnits** Windows işlevi temel birimleri geçerli iletişim piksel cinsinden döndürür.) Bu stili ile kullanılmamalıdır **lbs_ownerdrawfıxed**.  
  
-   **Lbs_wantkeyboardınput** liste kutusu sahibi alır `WM_VKEYTOITEM` veya `WM_CHARTOITEM` her liste kutusu odak giriş sırada kullanıcının bir anahtar bastığında iletileri. Bu klavye girdisi özel işlem gerçekleştirmek bir uygulama sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC tarafından kullanılan stiller](../../mfc/reference/styles-used-by-mfc.md)   
 [CListBox::Create](../../mfc/reference/clistbox-class.md#create)   
 [Liste kutusu stilleri](http://msdn.microsoft.com/library/windows/desktop/bb775149)

